---
title: "log_shipping_primary_secondaries (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- log_shipping_primary_secondaries_TSQL
- log_shipping_primary_secondaries
dev_langs:
- TSQL
helpviewer_keywords:
- log_shipping_primary_secondaries system table
ms.assetid: 4b315c70-7265-4acd-b35b-a4dbb7881d98
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 325b38e3b2cdb8f3fab90d4350ecfd449b512b81
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2018
---
# <a name="logshippingprimarysecondaries-transact-sql"></a>log_shipping_primary_secondaries (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  將每個主要資料庫對應至它的次要資料庫。 這份資料表儲存在**msdb**資料庫。  

  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**primary_id**|**uniqueidentifier**|記錄傳送組態之主要資料庫的識別碼。|  
|**secondary_server**|**sysname**|第二個執行個體名稱[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]記錄傳送組態中。|  
|**secondary_database**|**sysname**|記錄傳送組態中之次要資料庫的名稱。|  
  
## <a name="see-also"></a>另請參閱  
 [關於記錄傳送 &#40;SQL Server &#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [sp_add_log_shipping_primary_secondary &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql.md)   
 [sp_delete_log_shipping_primary_secondary &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql.md)   
 [sp_help_log_shipping_primary_secondary &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-log-shipping-primary-secondary-transact-sql.md)   
 [系統資料表 &#40;TRANSACT-SQL &#41;](../../relational-databases/system-tables/system-tables-transact-sql.md)  
  
  
