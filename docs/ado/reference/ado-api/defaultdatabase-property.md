---
title: "DefaultDatabase 屬性 |Microsoft 文件"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Connection15::DefaultDatabase
helpviewer_keywords:
- DefaultDatabase property
ms.assetid: 41e8a8dd-e69c-4a09-8736-93502e01961c
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2c4220d8551d7aa9d1bd37f0770474214bc14209
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="defaultdatabase-property"></a>DefaultDatabase 屬性
表示的預設資料庫[連接](../../../ado/reference/ado-api/connection-object-ado.md)物件。  
  
## <a name="settings-and-return-values"></a>設定和傳回值  
 設定或傳回**字串**評估為可用資料庫的名稱，從提供者的值。  
  
## <a name="remarks"></a>備註  
 使用**DefaultDatabase**屬性來設定或傳回的預設資料庫的名稱在特定**連接**物件。  
  
 如果沒有預設的資料庫，SQL 字串可能使用不合格的語法，來存取資料庫中的物件。 中所指定以外的資料庫中存取物件**DefaultDatabase**屬性，您必須以限定物件名稱所需的資料庫名稱。 提供者會將預設資料庫資訊寫入連接時， **DefaultDatabase**屬性。 某些提供者允許每個連線只有一個資料庫，請在此情況下，您無法變更**DefaultDatabase**屬性。  
  
 某些資料來源和提供者可能不支援這項功能，並可能會傳回錯誤或空字串。  
  
> [!NOTE]
>  **遠端資料服務使用量**這個屬性並不適用於用戶端**連接**物件。  
  
## <a name="applies-to"></a>適用於  
 [Connection 物件 (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)  
  
## <a name="see-also"></a>另請參閱  
 [提供者和 DefaultDatabase 屬性範例 (VB)](../../../ado/reference/ado-api/provider-and-defaultdatabase-properties-example-vb.md)   
 [Provider 和 DefaultDatabase 屬性範例 (VC++)](../../../ado/reference/ado-api/provider-and-defaultdatabase-properties-example-vc.md)   
