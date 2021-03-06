---
title: "UPDATE、 DELETE 和 INSERT 陳述式 |Microsoft 文件"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- updating data [ODBC], about updating data
- DELETE [ODBC]
- UPDATE [ODBC]
- INSERT [ODBC]
- data updates [ODBC], about data updates
ms.assetid: 5004ea72-4c49-4064-9752-f7032ba7f133
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 592d135ccf66f8a9fde2cc064a51dc25617cf127
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2018
---
# <a name="update-delete-and-insert-statements"></a>UPDATE、 DELETE 和 INSERT 陳述式
以 SQL 為基礎的應用程式對資料表進行變更，藉由執行**更新**，**刪除**，和**插入**陳述式。 下列陳述式是 Minimum SQL 文法一致性層級的一部分，而且必須支援的所有驅動程式和資料來源。  
  
 這些陳述式的語法如下：  
  
 **UPDATE**  *table-name*  
  
 **SET** *column-identifier* **=** {*expression* &#124; **NULL**}  
  
 [**，** *資料行識別碼*  **=**  {*運算式*&#124;**NULL**}]...  
  
 [**WHERE** *search-condition*]  
  
 **DELETE FROM** *table-name*[**WHERE** *search-condition*]  
  
 **INSERT INTO** *table-name*[**(***column-identifier* [**,** *column-identifier*]...**)**]  
  
 {*查詢規格*&#124;**值 (* * * 插入值*[* *，** *插入值*]...**)**}  
  
 請注意，*查詢規格*項目是只適用於核心和 Extended SQL 文法中，而且*運算式*和*搜尋條件*項目變得更複雜的核心和 Extended SQL 文法中。  
  
 類似其他 SQL 陳述式，**更新**，**刪除**，和**插入**陳述式所需通常較有效率使用時，這些參數。 例如，下列陳述式可以備妥，並重複執行 「 訂單 」 資料表中插入多個資料列：  
  
```  
INSERT INTO Orders (PartID, Description, Price) VALUES (?, ?, ?)  
```  
  
 傳遞參數值的陣列，可以增加這種效率。 如需陳述式參數和參數值的陣列的詳細資訊，請參閱[陳述式參數](../../../odbc/reference/develop-app/statement-parameters.md)。
