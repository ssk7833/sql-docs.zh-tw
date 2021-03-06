---
title: "追蹤 (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: mds
ms.service: 
ms.component: non-specific
ms.reviewer: 
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45823fc8-723a-49f2-9a11-94d241245cfd
caps.latest.revision: 
author: leolimsft
ms.author: lle
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 72a82c699ff117d2b9b87ffec8ea2b4c97cae66f
ms.sourcegitcommit: 6ac1956307d8255dc544e1063922493b30907b80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2018
---
# <a name="tracing-master-data-services"></a>追蹤 (Master Data Services)
  Web.config 檔案包含追蹤區段，如下所示。 這是 [!INCLUDE[ssSQL15](../includes/sssql15-md.md)][!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]  
  
```  
<sources>  
      <!-- Adjust the switch value to control the types of messages that should be logged.   
           http://msdn.microsoft.com/en-us/library/system.diagnostics.sourcelevels  
           Use the a switchValue of Verbose to generate a full log. Please be aware that   
           the trace file can get quite large very quickly -->  
      <source name="MDS" switchType="System.Diagnostics.SourceSwitch" switchValue="Warning, ActivityTracing">  
        <listeners>  
          <!-- Set a directory path where the service account you chose while setting up Master Data Services has read and write privileges.  
               Default path is Logs in WebApplication folder, for example C:\Program Files\Microsoft SQL Server\130\Master Data Services\WebApplication  
               New log file will be created every day or every 10 mb.  
               When directory size hits the 200mb limitation, the oldest file will be deleted.-->  
          <add name="FileTraceListener"  
               type="Microsoft.MasterDataServices.Core.Logging.FileTraceListener, Microsoft.MasterDataServices.Core"   
               initializeData="DirectoryPath = Logs; FileSizeInMb = 10; MaxDirectorySizeInMb = 200"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
  
```  
  
 以下是預設的追蹤行為。  
  
-   警告和 ActivityTracing 訊息會啟用追蹤。  
  
     如需詳細資訊，請參閱 [SourceLevels 列舉類型](https://msdn.microsoft.com/en-us/library/system.diagnostics.sourcelevels)。  
  
-   記錄會儲存在 WebApplication 資料夾下的 Logs 資料夾中。 預設位置是 C:\Program Files\Microsoft SQL Server\130\Master Data Services\WebApplication\Logs。  
  
-   每天或每 10 MB 建立檔案。  
  
-   當大小直接達到 200 MB 時，會刪除最舊的記錄檔。  
  
-   記錄格式是 CSV。 下表描述記錄格式。  
  
    |元素|描述|  
    |-------------|-----------------|  
    |Time|追蹤項目的發生時間。|  
    |CorrelationID|每個要求會指派一個相互關聯識別碼。 此要求觸發的所有追蹤會共用相同的相互關聯識別碼。<br /><br /> 當 UI 中發生錯誤時，相互關聯識別碼會出現在錯誤訊息中。|  
    |作業|要求作業名稱。 如果要求是 Web UI 要求，作業名稱會是 URL。 如果要求是 API 要求，作業名稱會是服務名稱。|  
    |層級|此追蹤項目的層級。|  
    |訊息|追蹤的訊息主體|  
  
## <a name="external-resources"></a>外部資源  
 msdn.com 上的部落格文章： [疑難排解記錄改進](http://go.microsoft.com/fwlink/p/?LinkId=615377)。  
  
  
