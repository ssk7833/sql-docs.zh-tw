---
title: "設定商務規則來傳送通知 (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
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
helpviewer_keywords:
- business rules [Master Data Services], configuring notifications
- e-mail [Master Data Services], configuring business rules
- notifications [Master Data Services], configuring business rules
ms.assetid: b24f7b11-ab53-4642-999c-e17b543b3558
caps.latest.revision: 
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 407e57317e5b92ca529ce3fa4196b7d1ddafd6a7
ms.sourcegitcommit: 6ac1956307d8255dc544e1063922493b30907b80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2018
---
# <a name="configure-business-rules-to-send-notifications-master-data-services"></a>設定商務規則來傳送通知 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，當您想要通知使用者屬性值變更時，請設定商務規則來傳送通知。  
  
## <a name="prerequisites"></a>Prerequisites  
 若要執行此程序：  
  
-   您必須擁有存取 [系統管理] 和 [使用者及群組的權限] 功能區域的權限。 如果您沒有 [使用者及群組的權限] 功能區域的權限，就無法檢視傳送通知的目標使用者和群組清單。  
  
-   您必須是模型管理員。 如需詳細資訊，請參閱 [管理員 &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)，您就可以在群組中加入及移除使用者。  
  
-   使用驗證動作的商務規則必須已經存在。 如需詳細資訊，請參閱[建立及發行商務規則 &#40;Master Data Services&#41;](../master-data-services/create-and-publish-a-business-rule-master-data-services.md)。  
  
-   接收通知的使用者或群組至少必須針對驗證失敗的屬性擁有 [唯讀] 權限。 遭明確或隱含拒絕此屬性之權限的使用者或群組將會收到電子郵件，但是無法在 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 中存取此屬性。  
  
-   如果將郵件傳送給群組，只有可存取 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 的群組成員會收到電子郵件。  
  
### <a name="to-configure-business-rules-to-send-notifications"></a>若要設定商務規則來傳送通知  
  
1.  在 [ [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]] 中，按一下 **[系統管理]**。  
  
2.  從功能表列，指向 **[管理]** ，然後按一下 **[商務規則]**。  
  
3.  在 [商務規則] 頁面上，選取 [模型] 清單中的模型。  
  
4.  從 [實體]  下拉式清單選取實體。  
  
5.  從 [成員類型] 下拉式清單中，選取成員的類型。  
  
6.  在方格中，選取您想要編輯之商務規則的資料列，然後按一下 [編輯]。  
  
7.  選取 [傳送通知] 核取方塊，然後從下拉式清單選取要向其傳送電子郵件通知的使用者或群組。  
  
8.  按一下 **[儲存]**。  
  
9. 按一下 [全部發行] 。  
  
10. 在確認對話方塊中按一下 **[確定]**。 [商務規則狀態] 資料行中的值變更為 [作用中]，[通知] 資料行會顯示要向其傳送通知的選取使用者或群組。  
  
## <a name="next-steps"></a>Next Steps  
  
-   遵循下列其中一個程序，將商務規則套用至資料：  
  
    -   [根據商務規則驗證特定成員 &#40;Master Data Services&#41;](../master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [根據商務規則驗證版本 &#40;Master Data Services&#41;](../master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   依照下列方式設定電子郵件通訊協定：  
  
    -   [設定電子郵件通知 &#40;Master Data Services&#41;](../master-data-services/configure-email-notifications-master-data-services.md)  
  
## <a name="see-also"></a>另請參閱  
 [通知 &#40;Master Data Services&#41;](../master-data-services/notifications-master-data-services.md)   
 [設定電子郵件通知 &#40;Master Data Services&#41;](../master-data-services/configure-email-notifications-master-data-services.md)  
  
  
