---
title: "為 DQS 記錄檔設定嚴重性層級 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dqs.admin.config.log.f1"
helpviewer_keywords: 
  - "severity levels"
  - "log files,severity levels"
  - "dqs log files,severity levels"
  - "logging,severity levels"
  - "設定嚴重性層級"
ms.assetid: 66ffcdec-4bf7-4dd5-a221-fd9baefeeef4
caps.latest.revision: 11
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 11
---
# 為 DQS 記錄檔設定嚴重性層級
  此主題描述如何使用 [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] 來針對 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] (DQS) 中的各種不同活動和模組設定嚴重性層級。 嚴重性層級會定義 DQS 中發生之事件的強度。 DQS 事件具有以下的嚴重性層級 (依照嚴重性的遞減順序排列)：  
  
-   **嚴重**︰ 嚴重執行階段錯誤，可能會造成嚴重/非預期的結果。  
  
-   **錯誤**：其他執行階段錯誤。  
  
-   **警告**：可能會造成錯誤之事件的警告。  
  
-   **資訊**：非錯誤或警告之一般事件的相關資訊。 例如，DQS 處理序已啟動。  
  
-   **偵錯**︰ 詳細的事件 （詳細資訊） 的資訊。  
  
 藉由設定各種 DQS 活動和模組的嚴重性層級，您會針對各自 DQS 活動或模組來篩選想要記錄的資訊以及寫入 DQS 記錄檔的資訊。 比方說，如果您設定讓 DQS 活動的嚴重性層級 **警告**, 、 只警告和更高嚴重性 （錯誤和嚴重錯誤） 與 DQS 活動相關聯就會記錄訊息。  
  
##  <a name="BeforeYouBegin"></a> 開始之前  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> Permissions  
 您必須擁有 DQS_MAIN 資料庫的 dqs_administrator 角色，才能設定記錄嚴重性設定。  
  
##  <a name="ConfigureActivity"></a> 在活動層級設定嚴重性層級  
 您可以在 DQS 中設定以下活動的記錄嚴重性設定：定義域管理、知識探索、比對原則、資料清理、資料比對和參考資料服務。 若要這樣做：  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [執行資料品質用戶端應用程式](../data-quality-services/run-the-data-quality-client-application.md)。  
  
2.  在 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 首頁畫面中，按一下 **[組態]**。  
  
3.  接著，按一下 [ **記錄檔設定** ] 索引標籤。 下列 DQS 活動會列出您可以選取嚴重性層級︰ **定義域管理**, ，**知識探索**, ，**清理專案 （例如RDS)**, ，**比對原則和比對專案**, ，和 **RDS**。  
  
4.  如果是 DQS 活動，請選取您想要記錄的嚴重性層級。 您可以選取下列其中一項： **[嚴重錯誤]**、 **[錯誤]**、 **[警告]**、 **[資訊]**和 **[偵錯]**。 例如，如果您想要只將嚴重訊息寫入 DQS 記錄檔的知識探索活動，選取 **嚴重錯誤** 在下拉式清單中，針對 **知識探索** 活動。  
  
    > [!NOTE]  
    >  預設會針對每一個活動選取 **[錯誤]** 。 這表示，預設會針對每一個活動將錯誤和嚴重訊息寫入 DQS 記錄檔中。  
  
5.  按一下 [ **關閉**]。  
  
##  <a name="ConfigureModule"></a> 在模組層級設定嚴重性層級 (進階)  
 **[記錄檔設定]** 索引標籤中的 **[進階]** 區段可讓您在模組層級設定記錄嚴重性設定。 模組是 DQS 系統組件，可在 DQS 中實作某項功能內的各種不同功能。 例如，定義域管理活動包含類似以下的各種功能：定義定義域規則、定義規則條件、定義複合定義域的跨定義域規則等。  
  
 有時活動層級的資料粒度層級並不夠。 您可能會想要調查活動內的特定模組中是否發生問題。 它可幫助您選擇在模組層級設定記錄嚴重性，以便更精確地隔離和追蹤問題。  
  
 在活動層級指定的記錄嚴重性設定會決定組成活動之所有模組的記錄嚴重性設定。 但是，如果活動層級和模組層級的記錄嚴重性設定之間有任何衝突，則會考量模組層級的嚴重性設定。  
  
> [!NOTE]  
>  -   根據預設， **Microsoft.Ssdqs.Core.Startup** 模組會在 **[進階]** 區段中預先設定，且嚴重性層級設定為 **[資訊]**。 這樣做是為了記錄嚴重性為資訊或更高層級 (警告、錯誤和嚴重錯誤) 的事件，這些事件與啟動和停止 DQS 服務有關。  
> -   只有當您是熟悉 DQS 系統組件的資深 DQS 使用者時，才能在模組層級設定記錄嚴重性層級。  
  
 若要在模組層級設定記錄嚴重性層級：  
  
1.  在 **[記錄檔設定]** 索引標籤中，針對 **[進階]** 按一下向下箭號，以顯示區域。  
  
2.  在方格中出現，請從下拉式清單中選取模組名稱 **模組** 資料行。  
  
3.  接下來，從下拉式清單中選取模組的嚴重性層級 **嚴重性** 資料行。 您可以選取下列其中一項： **[嚴重錯誤]**、 **[錯誤]**、 **[警告]**、 **[資訊]**和 **[偵錯]**。  
  
     例如在定義域管理活動中，您可以為定義域規則定義功能設定與定義域管理活動不同的資料粒度層級，方法是選取 **Microsoft.Ssdqs.DomainRules.Define** 模組，並選取不同的記錄嚴重性層級。 同樣地，您可以設定不同的資料粒度層級的跨定義域規則功能，藉由選取 **Microsoft.Ssdqs.DomainRules.Condition.CrossDomain** 模組，並選取不同的記錄嚴重性層級。  
  
4.  必要時針對其他模組重複步驟 2 和 3。 您也可以在方格中加入或刪除資料列，方法是按一下 **[加入模組]** 和 **[移除模組]** 圖示。  
  
5.  按一下 [ **關閉**]。  
  
## 另請參閱  
 [為 DQS 記錄檔設定進階設定](../data-quality-services/configure-advanced-settings-for-dqs-log-files.md)  
  
  