---
title: "cdc.captured_columns (TRANSACT-SQL) |Microsoft 文件"
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
- cdc.captured_columns
- cdc.captured_columns_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- cdc.captured_columns
ms.assetid: 7bb4d408-d764-4ef6-802c-f271c8d39c2a
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e0f4ff663a64e2de3fa7a8247eee170907d1a624
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="cdccapturedcolumns-transact-sql"></a>cdc.captured_columns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  針對在擷取執行個體中追蹤的每個資料行，各傳回一個資料列。 根據預設，系統會擷取來源資料表的所有資料行。 不過，當來源資料表啟用異動資料擷取時，您可以透過指定資料行清單，加入或排除資料行。 如需詳細資訊，請參閱[sys.sp_cdc_enable_table &#40;TRANSACT-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-enable-table-transact-sql.md).  
  
 我們建議您**不直接查詢系統資料表**。 請改為執行[sys.sp_cdc_get_source_columns](../../relational-databases/system-stored-procedures/sys-sp-cdc-get-captured-columns-transact-sql.md)預存程序。  
   
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|擷取資料行所屬之來源資料表的識別碼。|  
|**column_name**|**sysname**|擷取資料行的名稱。|  
|**column_id**|**int**|來源資料表中擷取資料行的識別碼。|  
|**column_type**|**sysname**|擷取資料行的類型。|  
|**column_ordinal**|**int**|變更資料表中的資料行序數 (以 1 為基底)。 變更資料表中的中繼資料資料行排除在外。 序數 1 指派給第一個擷取資料行。|  
|**sys.computer_columns**|**bit**|指出擷取資料行是來源資料表中的計算資料行。|  
  
## <a name="see-also"></a>請參閱＜  
 [cdc.change_tables &#40;TRANSACT-SQL &#41;](../../relational-databases/system-tables/cdc-change-tables-transact-sql.md)  
  
  
