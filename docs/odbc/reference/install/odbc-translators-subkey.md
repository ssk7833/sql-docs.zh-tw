---
title: "ODBC 轉譯器的子機碼 |Microsoft 文件"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- translator subkey [ODBC]
- subkeys [ODBC], translator subkey
- registry entries for components [ODBC], translator subkey
ms.assetid: 6b170f1f-e263-4aac-9d49-8d0ca0470ca2
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e94cd3cd2313b98376e32c8775ec38c3c8ddb268
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-translators-subkey"></a>ODBC 轉譯器的子機碼
ODBC 轉譯子機碼下的值清單的已安裝的轉譯器。 下表顯示這些值的格式。  
  
|[屬性]|資料類型|data|  
|----------|---------------|----------|  
|*轉譯程式 desc*|REG_SZ|**安裝**|  
  
 *轉譯程式 desc*轉譯程式開發人員所定義名稱。  
  
 例如，假設使用者已安裝 Microsoft （） 程式碼頁面轉譯器和自訂 ASCII EBCDIC 轉譯程式。 ODBC 轉譯子機碼下的值可能如下所示：  
  
```  
MS Code Page Translator: REG_SZ : Installed  
ASCII to EBCDIC: REG_SZ : Installed.  
```
