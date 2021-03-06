---
title: "散發資料庫 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: replication
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.configuredistributionwizard.distributiondatabase.f1
ms.assetid: 5b42a083-7a11-41d8-9e3f-320c7c907237
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 18a787e7adac63323168c11fdc5595bba162b194
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2018
---
# <a name="distribution-database"></a>散發資料庫
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  散發資料庫會儲存所有複寫類型的中繼資料和記錄資料，以及異動複寫的交易。  
  
 在許多情況下，單一散發資料庫即已足夠。 不過，如果多個發行者使用單一散發者，請考慮為每個發行者建立一個散發資料庫。 這樣可以確保流經每個散發資料庫的資料都不同。 您可以為使用設定散發精靈的散發者指定一個散發資料庫。 如有需要，請在 **[散發者屬性]** 對話方塊中指定其他散發資料庫。  
  
## <a name="options"></a>選項。  
 **散發資料庫名稱**  
 輸入散發資料庫的名稱。 散發資料庫的預設名稱為「distribution」。 如果您指定名稱，則名稱最多為 128 個字元、必須在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]執行個體中是唯一的，而且必須符合識別碼的規則。 如需詳細資訊，請參閱＜ [Database Identifiers](../../relational-databases/databases/database-identifiers.md)＞。  
  
 **[散發資料庫檔案的資料夾]** 和 **[散發資料庫記錄檔的資料夾]**  
 輸入散發資料庫和記錄檔的路徑。 路徑必須參考對散發者而言是本機的磁碟機，而且以本機磁碟機代號開始，然後是冒號 (例如，C:)。 對應的磁碟機代號和網路路徑無效。  
  
> [!NOTE]  
>  您可以藉由將散發資料庫記錄放置在散發資料庫的個別磁碟機上，來減少寫入交易的時間和改進複寫的效能。  
  
## <a name="see-also"></a>另請參閱  
 [[設定散發]](../../relational-databases/replication/configure-distribution.md)   
 [設定發行和散發](../../relational-databases/replication/configure-publishing-and-distribution.md)   
 [檢視及修改散發者和發行者屬性](../../relational-databases/replication/view-and-modify-distributor-and-publisher-properties.md)  
  
  
