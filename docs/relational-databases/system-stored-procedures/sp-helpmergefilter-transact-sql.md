---
title: "sp_helpmergefilter (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_helpmergefilter
- sp_helpmergefilter_TSQL
helpviewer_keywords:
- sp_helpmergefilter
ms.assetid: f133a094-0009-4771-b93b-e86a5c01e40b
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6ec2500e3fc16c2f6c78473fb97a6b1bf757ef52
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="sphelpmergefilter-transact-sql"></a>sp_helpmergefilter (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  傳回合併篩選的相關資訊。 這個預存程序執行於任何資料庫的發行者端。  
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
  
sp_helpmergefilter [ @publication= ] 'publication'   
    [ , [ @article= ] 'article']  
    [ , [ @filtername= ] 'filtername']  
```  
  
## <a name="arguments"></a>引數  
 [  **@publication=**] **'***發行集***'**  
 這是發行集的名稱。 *發行集*是**sysname**，沒有預設值。  
  
 [  **@article=**] **'***文章***'**  
 這是發行項的名稱。 *發行項*是**sysname**，預設值是 **%** ，它會傳回所有發行項的名稱。  
  
 [  **@filtername=**] **'***filtername***'**  
 這是要傳回資訊的篩選名稱。 *filtername*是**sysname**，預設值是 **%** ，傳回所有發行集的發行項上定義的篩選條件的相關資訊。  
  
## <a name="result-sets"></a>結果集  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**join_filterid**|**int**|聯結篩選的識別碼。|  
|**filtername**|**sysname**|篩選的名稱。|  
|**聯結發行項名稱**|**sysname**|聯結發行項的名稱。|  
|**join_filterclause**|**nvarchar(2000)**|限定聯結的篩選子句。|  
|**join_unique_key**|**int**|聯結是否基於唯一索引鍵。|  
|**基底資料表的擁有者**|**sysname**|基底資料表的擁有者名稱。|  
|**基底資料表名稱**|**sysname**|基底資料表的名稱。|  
|**聯結資料表擁有者**|**sysname**|聯結到基底資料表中之資料表的擁有者名稱。|  
|**聯結資料表名稱**|**sysname**|聯結到基底資料表中的資料表名稱。|  
|**發行項名稱**|**sysname**|聯結到基底資料表中的資料表發行項名稱。|  
|**filter_type**|**tinyint**|合併篩選的類型，它可以是下列項目之一：<br /><br /> **1** = 僅聯結篩選<br /><br /> **2** = 邏輯記錄關聯性<br /><br /> **3** = 兩者|  
  
## <a name="return-code-values"></a>傳回碼值  
 **0** （成功） 或**1** （失敗）  
  
## <a name="remarks"></a>備註  
 **sp_helpmergefilter**用於合併式複寫中。  
  
## <a name="permissions"></a>Permissions  
 只有成員**sysadmin**固定的伺服器角色和**db_owner**固定的資料庫角色可以執行**sp_helpmergefilter**。  
  
## <a name="see-also"></a>請參閱＜  
 [sp_addmergefilter &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addmergefilter-transact-sql.md)   
 [sp_changemergefilter &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-changemergefilter-transact-sql.md)   
 [sp_dropmergefilter &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropmergefilter-transact-sql.md)   
 [系統預存程序 &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
