---
title: "將新項目加入專案 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-solutions
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 76af8692-324f-4f5e-b1a0-d72ca8a107e3
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 7c8d4906eb124daff7a754522d4ecb46eb3933bd
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2018
---
# <a name="add-new-items-to-a-project"></a>將新項目加入專案
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] 請將新的項目新增至專案，來延伸應用程式功能。 新項目可以是查詢或連接。 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] 有兩種專案類型： [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 指令碼專案和 Analysis Services 指令碼專案。 專案類型決定了可以加入專案中的項目。 例如，您可以將 [!INCLUDE[tsql](../../includes/tsql_md.md)] 查詢 (副檔名是 .sql 的檔案) 加入 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 指令碼專案中，但您不能將它加入 Analysis Services 指令碼專案中。  
  
[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] 不允許您在專案內建立資料夾。 若要組織您的工作，請在方案內建立多個專案。  
  
### <a name="to-add-a-new-query-to-an-existing-project"></a>將新查詢加入現有的專案中  
  
1.  在 [方案總管] 中，選取一個目標專案。  
  
2.  在 [專案] 功能表上，按一下 [加入新項目]。  
  
3.  在 [新增項目] 對話方塊的左窗格中，選取一個類別目錄。  
  
4.  在右窗格中，選取一個查詢範本，再按一下 [新增]。 此時會在專案的 [查詢] 資料夾中，加入新的查詢。  
  
5.  在 [連接到 Database Engine] 對話方塊中，指定新查詢的連接，再按一下 [連接]。 如果您不要將連接關聯於這項新查詢，您可以在連接對話中，按一下 [取消]。  
  
6.  如果想要的話，請在 [方案總管] 中重新命名查詢。  
  
### <a name="to-add-a-new-connection-to-an-existing-project"></a>將新連接加入現有的專案中  
  
1.  在 [方案總管] 中，選取一個目標專案。  
  
2.  在 [專案] 功能表上，按一下 [加入新項目]。  
  
3.  在左窗格中，選取 [連接]。  
  
4.  在右窗格中，選取 [新增連接]，再按一下 [新增]。  
  
5.  在 [連接到 Database Engine] 對話方塊中，指定新查詢的連接，再按一下 [連接]。 此時會在專案的 [連接] 資料夾中，新增連接。  
  
## <a name="see-also"></a>另請參閱  
[方案總管](../../ssms/solution/solution-explorer.md)  
[使副檔名與程式碼編輯器相關聯](http://msdn.microsoft.com/en-us/193630f4-93de-4950-8f36-68702531f925)  
[將現有的項目加入至專案](../../ssms/solution/add-existing-items-to-a-project.md)  
[移除或刪除項目或專案](../../ssms/solution/remove-or-delete-an-item-or-project.md)  
  
