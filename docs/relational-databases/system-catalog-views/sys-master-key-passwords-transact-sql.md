---
title: "sys.master_key_passwords (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.master_key_passwords_TSQL
- master_key_passwords_TSQL
- sys.master_key_passwords
- master_key_passwords
dev_langs:
- TSQL
helpviewer_keywords:
- sys.master_key_passwords catalog view
ms.assetid: b8e18cff-a9e6-4386-98ce-1cd855506e03
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6bb1977fb034f2fd2c682b12b4466bd7914009dd
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2017
---
# <a name="sysmasterkeypasswords-transact-sql"></a>sys.master_key_passwords (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  傳回一個資料列加入每個資料庫主要金鑰密碼使用**sp_control_dbmasterkey_password**預存程序。 保護主要金鑰所用的密碼，是儲存在認證存放區中。 認證名稱遵照的格式如下：##DBMKEY_<database_family_guid>_<random_password_guid>##。 密碼會儲存為認證秘密。 使用新增的每個密碼**sp_control_dbmasterkey_password**中的資料列**sys.credentials**。  
  
 在此檢視中的每個資料列會顯示**credential_id**和**family_guid**的資料庫主要金鑰受到該認證相關聯的密碼。 與聯結**sys.credentials**上**credential_id**會傳回有用的欄位，例如**create_date**和認證名稱。  
  
|資料行名稱|資料類型|Description|  
|-----------------|---------------|-----------------|  
|**credential_id**|**int**|密碼所屬的認證識別碼。 這個識別碼在伺服器執行個體中是唯一的。|  
|**family_guid**|**uniqueidentifier**|建立時原始資料庫的唯一識別碼。 當資料庫還原或附加之後，這個 GUID 仍然不變，即使資料庫名稱改變了也是如此。<br /><br /> 如果由服務主要金鑰的自動解密失敗，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]使用**family_guid**來識別可能會包含用來保護資料庫主要金鑰密碼的認證。|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 如需相關資訊，請參閱 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>請參閱  
 [目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql.md)   
 [安全性目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [加密階層](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
