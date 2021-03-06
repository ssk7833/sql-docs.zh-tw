---
title: CERTPROPERTY (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CERTPROPERTY
- CERTPROPERTY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- certificates [SQL Server], schema names
- schemas [SQL Server], names
- CERTPROPERTY function
ms.assetid: 966c09aa-bc4e-45b0-ba53-c8381871f638
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d63968d8b07a37ea49662bd0727632a1675b3913
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="certproperty-transact-sql"></a>CERTPROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

傳回指定憑證屬性的值。
  
![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>語法  
  
```sql
CertProperty ( Cert_ID , '<PropertyName>' )  
  
<PropertyName> ::=  
   Expiry_Date | Start_Date | Issuer_Name   
   | Cert_Serial_Number | Subject | SID | String_SID   
```  
  
## <a name="arguments"></a>引數  
*Cert_ID*  
這是憑證的識別碼。 *Cert_ID* 為 int。
  
*Expiry_Date*  
這是憑證的到期日。
  
*Start_Date*  
這是憑證生效的日期。
  
*Issuer_Name*  
這是憑證的簽發者名稱。
  
*Cert_Serial_Number*  
這是憑證序號。
  
*主旨*  
這是憑證的主旨。
  
 *SID*  
這是憑證的 SID。 這也是對應至這個憑證之任何登入或使用者的 SID。
  
*String_SID*  
這是字元字串格式的憑證 SID。 這也是對應至憑證之任何登入或使用者的 SID。
  
## <a name="return-types"></a>傳回型
屬性規格必須括在單引號中。
  
傳回類型會隨著函數呼叫中指定的屬性而不同。 所有傳回值都會以 **sql_variant** 的傳回型別包裝。
-   *Expiry_Date* 及 *Start_Date* 會傳回 **datetime**。  
-   *Cert_Serial_Number*、*Issuer_Name*、*Subject*，及 *String_SID* 會傳回 **nvarchar**。  
-   *SID* 會傳回 **varbinary**。  
  
## <a name="remarks"></a>Remarks  
您可以在 [sys.certificates](../../relational-databases/system-catalog-views/sys-certificates-transact-sql.md) 目錄檢視中，看到有關憑證的資訊。
  
## <a name="permissions"></a>Permissions  
需要憑證的部份權限，且呼叫端尚未拒絕憑證的 VIEW DEFINITION 權限。
  
## <a name="examples"></a>範例  
下列範例會傳回憑證主旨。
  
```sql
-- First create a certificate.  
CREATE CERTIFICATE Marketing19 WITH   
    START_DATE = '04/04/2004' ,  
    EXPIRY_DATE = '07/07/2007' ,  
    SUBJECT = 'Marketing Print Division';  
GO  
  
-- Now use CertProperty to examine certificate  
-- Marketing19's properties.  
DECLARE @CertSubject sql_variant;  
set @CertSubject = CertProperty( Cert_ID('Marketing19'), 'Subject');  
PRINT CONVERT(nvarchar, @CertSubject);  
GO  
```  
  
## <a name="see-also"></a>另請參閱
[CREATE CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)  
[ALTER CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-certificate-transact-sql.md)  
[CERT_ID &#40;Transact-SQL&#41;](../../t-sql/functions/cert-id-transact-sql.md)
[加密階層](../../relational-databases/security/encryption/encryption-hierarchy.md)
[sys.certificates &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-certificates-transact-sql.md)
[安全性目錄檢視 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)
  
  
