---
title: "sp_droplinkedsrvlogin (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_droplinkedsrvlogin_TSQL
- sp_droplinkedsrvlogin
dev_langs:
- TSQL
helpviewer_keywords:
- sp_droplinkedsrvlogin
ms.assetid: 75a4a040-72d5-4d29-8304-de0aa481ad4b
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a0d9e2ed37bd70dda7d1cf47f78a7f1c28692a0f
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2017
---
# <a name="spdroplinkedsrvlogin-transact-sql"></a>sp_droplinkedsrvlogin (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  移除在執行 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 之本機伺服器的登入與連結伺服器的登入之間的現有對應。  
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
  
sp_droplinkedsrvlogin [ @rmtsrvname= ] 'rmtsrvname' ,   
   [ @locallogin= ] 'locallogin'  
```  
  
## <a name="arguments"></a>引數  
 [  **@rmtsrvname =** ] **'***v***'**  
 連結的伺服器名稱，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]登入對應所套用。 *v*是**sysname**，沒有預設值。 *v*必須已經存在。  
  
 [  **@locallogin =** ] **'***locallogin***'**  
 是[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]是對應至連結伺服器的本機伺服器上的登入*v*。 *locallogin*是**sysname**，沒有預設值。 對應*locallogin*至*v*必須已經存在。 如果是 NULL，預設建立的對應**sp_addlinkedserver**，會刪除其對應至登入連結的伺服器上的本機伺服器上的所有登入。  
  
## <a name="return-code-values"></a>傳回碼值  
 0 (成功) 或 1 (失敗)  
  
## <a name="remarks"></a>備註  
 本機伺服器時的現有對應的登入遭到刪除，使用預設對應建立**sp_addlinkedserver**當它連接至連結伺服器代表該登入。 若要變更預設對應，請使用**sp_addlinkedsrvlogin**。  
  
 如果預設對應也會一併刪除，只有已明確提供登入對應至連結伺服器，以使用的登入**sp_addlinkedsrvlogin**，連結的伺服器可以存取。  
  
 **sp_droplinkedsrvlogin**無法從使用者定義交易內執行。  
  
## <a name="permissions"></a>Permissions  
 需要伺服器的 ALTER ANY LOGIN 權限。  
  
## <a name="examples"></a>範例  
  
### <a name="a-removing-the-login-mapping-for-an-existing-user"></a>A. 移除現有使用者的登入對應  
 下列範例會移除從本機伺服器到連結伺服器 `Mary` 的登入 `Accounts` 對應。 因此，登入 `Mary` 會使用預設的登入對應。  
  
```  
EXEC sp_droplinkedsrvlogin 'Accounts', 'Mary';  
```  
  
### <a name="b-removing-the-default-login-mapping"></a>B. 移除預設的登入對應  
 下列範例會移除原先在連結伺服器 `sp_addlinkedserver` 執行 `Accounts` 而建立的預設登入對應。  
  
```  
EXEC sp_droplinkedsrvlogin 'Accounts', NULL;  
```  
  
## <a name="see-also"></a>請參閱  
 [sp_addlinkedserver &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql.md)   
 [sp_addlinkedsrvlogin &#40;TRANSACT-SQL &#41;](../../relational-databases/system-stored-procedures/sp-addlinkedsrvlogin-transact-sql.md)   
 [系統預存程序 &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
