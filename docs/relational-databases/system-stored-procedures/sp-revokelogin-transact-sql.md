---
title: "sp_revokelogin (TRANSACT-SQL) |Microsoft 文件"
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
- sp_revokelogin_TSQL
- sp_revokelogin
dev_langs:
- TSQL
helpviewer_keywords:
- sp_revokelogin
ms.assetid: cb1ab102-1ae0-4811-9144-9a8121ef2d7e
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6869d96b5fb561328b9eed41c7b5af147b50db10
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2017
---
# <a name="sprevokelogin-transact-sql"></a>sp_revokelogin (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  移除登入項目從[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Windows 使用者或群組使用 CREATE LOGIN、 建立**sp_grantlogin**，或**sp_denylogin**。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]使用[DROP LOGIN](../../t-sql/statements/drop-login-transact-sql.md)改為。  
  
 ![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>語法  
  
```  
  
sp_revokelogin [ @loginame= ] 'login'  
```  
  
## <a name="arguments"></a>引數  
 [  **@loginame=**] **'***登入***'**  
 這是 Windows 使用者或群組的名稱。 *登入*是**sysname**，沒有預設值。 *登入*可以是任何現有的 Windows 使用者名稱或群組的形式*電腦名稱*\\*使用者或網域*\\*使用者*。  
  
## <a name="return-code-values"></a>傳回碼值  
 0 (成功) 或 1 (失敗)  
  
## <a name="remarks"></a>備註  
 **sp_revokelogin**停用使用所指定的帳戶連線*登入*參數。 但是在撤銷其個別存取權之後，透過 Windows 群組成員資格獲得 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 執行個體存取權的 Windows 使用者仍然可以用群組方式進行連接。 同樣地，如果*登入*參數指定 Windows 群組的名稱，該群組的成員，個別授與存取權的執行個體[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]仍然可以連接。  
  
 例如，如果 Windows 使用者**ADVWORKS\john**是 Windows 群組的成員**與**，和**sp_revokelogin**撤銷的存取權`ADVWORKS\john`:  
  
```  
sp_revokelogin [ADVWORKS\john]  
```  
  
 使用者**ADVWORKS\john**仍然可以連接，如果**與**已授與存取權的執行個體[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。 同樣地，如果 Windows 群組**與**已撤銷其存取權，但**ADVWORKS\john**授與存取權， **ADVWORKS\john**仍然可以進行連接。  
  
 使用**sp_denylogin**明確防止使用者連接到的執行個體[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，不管其 Windows 群組成員資格。  
  
 **sp_revokelogin**無法在使用者自訂交易內執行。  
  
## <a name="permissions"></a>Permissions  
 需要伺服器的 ALTER ANY LOGIN 權限。  
  
## <a name="examples"></a>範例  
 下列範例會移除 Windows 使用者的登入項目`Corporate\MollyA`。  
  
```  
EXEC sp_revokelogin 'Corporate\MollyA';  
```  
  
 或  
  
```  
EXEC sp_revokelogin [Corporate\MollyA];  
```  
  
## <a name="see-also"></a>請參閱  
 [安全性預存程序 &#40;TRANSACT-SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [卸除登入 &#40;TRANSACT-SQL &#41;](../../t-sql/statements/drop-login-transact-sql.md)   
 [sp_denylogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-denylogin-transact-sql.md)   
 [sp_droplogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-droplogin-transact-sql.md)   
 [sp_grantlogin &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-grantlogin-transact-sql.md)   
 [系統預存程序 &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
