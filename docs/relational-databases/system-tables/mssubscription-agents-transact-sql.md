---
title: "M (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSsubscription_agents
- MSsubscription_agents_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSsubscription_agents system table
ms.assetid: 86ad5891-0bef-4963-9381-7d5b45245a0c
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 11ad8bb029c1a083a4490cfe62e2bacf54b37d01
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="mssubscriptionagents-transact-sql"></a>MSsubscription_agents (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSsubscription_agents**資料表由散發代理程式和可更新訂閱的觸發程序來追蹤訂閱屬性。 這份資料表儲存在訂閱資料庫中。  
  
|資料行名稱|資料類型|描述|  
|-----------------|---------------|-----------------|  
|**id**|**int**|資料列的識別碼。|  
|**發行者**|**sysname**|發行者的名稱。|  
|**publisher_db**|**sysname**|發行集資料庫的名稱。|  
|**發行集**|**sysname**|發行集的名稱。|  
|**subscription_type**|**int**|訂閱類型：<br /><br /> 0 = 發送。<br /><br /> 1 = 提取<br /><br /> 2 = 提取匿名。|  
|**queue_id**|**sysname**|識別碼[!INCLUDE[msCoName](../../includes/msconame-md.md)]訊息佇列在發行者端。 *queue_id*設**SQL**的 SQL 架構佇列更新。|  
|**update_mode**|**tinyint**|更新的類型：<br /><br /> **0** = 唯讀。<br /><br /> **1** = 立即更新。<br /><br /> **2** = 使用 Message Queuing 的佇列更新。<br /><br /> **3** = 立即更新與佇列更新作為容錯移轉使用訊息佇列。<br /><br /> **4** = 使用 SQL Server 佇列的佇列更新。<br /><br /> **5** = 立即更新與佇列的更新容錯移轉時，使用 SQL Server 佇列。|  
|**failover_mode**|**bit**|如果選取了更新的容錯移轉類型，這就是所選的容錯移轉類型：<br /><br /> **0** = 立即使用更新。 不啟用容錯移轉。<br /><br /> **1** = 排入佇列使用更新。 啟用容錯移轉。 容錯移轉所用的佇列中指定*update_mode*值。|  
|**spid**|**int**|目前在執行或剛執行的散發代理程式所用之連接的系統處理序識別碼。|  
|**login_time**|**datetime**|目前在執行或剛執行的散發代理程式連接的日期和時間。|  
|**allow_subscription_copy**|**bit**|指定是否允許複製訂閱資料庫的能力。|  
|**attach_state**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**attach_version**|**binary （16)**|代表附加訂閱版本的唯一識別碼。|  
|**last_sync_status**|**int**|目前在執行或剛執行的散發代理程式的最後執行狀態。 狀態可能是：<br /><br /> **1** = 啟動。<br /><br /> **2** = 成功。<br /><br /> **3** = 進行中。<br /><br /> **4** = 閒置。<br /><br /> **5** = 重試。<br /><br /> **6** = 失敗。|  
|**last_sync_summary**|**sysname**|目前在執行或剛執行的散發代理程式的最後訊息。 狀態可能是：<br /><br /> **已啟動。**<br /><br /> **已成功。**<br /><br /> **進行中。**<br /><br /> **閒置。**<br /><br /> **重試。**<br /><br /> **失敗。**|  
|**last_sync_time**|**datetime**|日期和時間*last_sync_summary*和*last_sync_status*資料行已更新。 作為 SQL Server Agent 服務作業來執行的提取或匿名散發代理程式不會更新這些資料行。 在這個狀況下，記錄資訊會記錄到作業記錄資料表中。|  
|**queue_server**|**sysname**|僅供內部使用。|  
  
## <a name="see-also"></a>請參閱＜  
 [複寫資料表 &#40;TRANSACT-SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [複寫檢視 &#40;TRANSACT-SQL &#41;](../../relational-databases/system-views/replication-views-transact-sql.md)   
 [sp_helppullsubscription &#40;TRANSACT-SQL &#41;](../../relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql.md)  
  
  
