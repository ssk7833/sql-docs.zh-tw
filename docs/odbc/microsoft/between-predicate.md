---
title: "述詞之間 |Microsoft 文件"
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
- BETWEEN predicate [ODBC]
- SQL grammar [ODBC], between predicate
ms.assetid: 0cc7464b-d788-4720-98d8-411e1169185f
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 1738aa33f371a2e64ea0362cefcf59a759fdfee7
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="between-predicate"></a>述詞之間
語法：  
  
```  
expression1 BETWEEN expression2 AND expression3  
```  
  
 傳回，則為 true 才*expression1*大於或等於*expression2*和*expression1*小於或等於*expression3*.  
  
 此語法的語意為桌面資料庫驅動程式和 Microsoft Jet 引擎不同。 在 Microsoft Jet SQL 中， *expression2*可能會大於*expression3*使陳述式會傳回 TRUE，只有當*expression1*大於或等於*expression3*，和*expression1*小於或等於*expression2*。
