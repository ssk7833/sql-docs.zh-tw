---
title: "在同步處理期間執行指令碼 (複寫 Transact-SQL 程式設計) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: replication
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- TSQL
helpviewer_keywords:
- synchronization [SQL Server replication], scripts
- scripts [SQL Server replication], synchronization and
- sp_addscriptexec
ms.assetid: b58a0877-4e43-4fab-a281-24e6022d3fb1
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2703dfb45f6a1cc2532b15d48becdef930cac3a3
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2018
---
# <a name="execute-scripts-during-synchronization-replication-transact-sql-programming"></a>在同步處理期間執行指令碼 (複寫 Transact-SQL 程式設計)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  複寫可支援視需要針對交易式與合併式發行集的訂閱者執行指令碼。 這項功能會將指令碼複製到複寫工作目錄，然後使用 **sqlcmd** 將指令碼套用到訂閱者。 依預設，如果針對交易式發行集的訂閱套用指令碼時發生失敗，則散發代理程式將會停止。 您可以使用複寫預存程序以程式設計的方式指定要執行的 [!INCLUDE[tsql](../../includes/tsql-md.md)] 指令碼。  
  
### <a name="to-specify-a-script-to-run-for-all-subscribers-to-a-snapshot-transactional-or-merge-publication"></a>針對快照式、交易式或合併式發行集的所有訂閱者指定要執行的指令碼  
  
1.  撰寫及測試將會視需要執行的 [!INCLUDE[tsql](../../includes/tsql-md.md)] 指令碼。  
  
2.  將指令碼檔案儲存到可由發行集之快照集代理程式存取的位置。  
  
3.  在發行集資料庫的發行者上，執行 [sp_addscriptexec &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql.md)。 指定 **@publication**，並針對 **@scriptfile**指定步驟 2 中建立之具有完整 UNC 路徑的指令碼檔案名稱及針對 **@skiperror**指定下列其中一個值：  
  
    -   **0** - 如果遇到錯誤，代理程式將會停止執行指令碼。  
  
    -   **1** - 如果遇到錯誤，代理程式將會記錄錯誤並繼續執行指令碼。  
  
4.  當下一次執行代理程式來同步處理訂閱時，指定的指令碼將會在每一個訂閱者上執行。  
  
## <a name="see-also"></a>另請參閱  
 [同步處理資料](../../relational-databases/replication/synchronize-data.md)  
  
  
