---
title: "比較運算子 (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|language-elements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- expressions [SQL Server], testing
- operators [Transact-SQL], comparison
- testing expressions
- Boolean data type
- Boolean expressions
- comparing expressions
- comparison operators [SQL Server]
ms.assetid: b0cc68ef-3029-484c-a917-0c15dcbc230d
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Active
ms.openlocfilehash: cd8dcf23064d6caae62d10065c9aa3731823e99b
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2018
---
# <a name="comparison-operators-transact-sql"></a>比較運算子 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  比較運算子用來測試兩個運算式是否相同。 除了 **text**、**ntext** 或 **image** 資料類型的運算式，所有運算式都可使用比較運算子。 下表會列出 [!INCLUDE[tsql](../../includes/tsql-md.md)] 比較運算子。  
  
|運算子|意義|  
|--------------|-------------|  
|[= (等於)](../../t-sql/language-elements/equals-transact-sql.md)|等於|  
|[> (大於)](../../t-sql/language-elements/greater-than-transact-sql.md)|大於|  
|[< (小於)](../../t-sql/language-elements/less-than-transact-sql.md)|小於|  
|[>= (大於或等於)](../../t-sql/language-elements/greater-than-or-equal-to-transact-sql.md)|大於或等於|  
|[<= (小於或等於)](../../t-sql/language-elements/less-than-or-equal-to-transact-sql.md)|小於或等於|  
|[<> (不等於)](../../t-sql/language-elements/not-equal-to-transact-sql-traditional.md)|不等於|  
|[!= (不等於)](../../t-sql/language-elements/not-equal-to-transact-sql-exclamation.md)|不等於 (不是 ISO 標準)|  
|[!< (不小於)](../../t-sql/language-elements/not-less-than-transact-sql.md)|不小於 (不是 ISO 標準)|  
|[!> (不大於)](../../t-sql/language-elements/not-greater-than-transact-sql.md)|不大於 (不是 ISO 標準)|  
  
## <a name="boolean-data-type"></a>布林資料類型  
 比較運算子的結果具有 **Boolean** 資料類型。 它有三個值：TRUE、FALSE 和 UNKNOWN。 傳回 **Boolean** 資料類型的運算式稱為布林運算式。  
  
 **Boolean** 資料類型和其他 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 資料類型不同，不能將它指定為資料表資料行或變數的資料類型，且無法在結果集中傳回。  
  
 當 SET ANSI_NULLS 是 ON 時，有一或兩個 NULL 運算式的運算子會傳回 UNKNOWN。 當 SET ANSI_NULLS 是 OFF 時，如果兩個運算式都是 NULL，除了等於 (=) 運算子會傳回 TRUE，也適用相同的規則。 例如，當 SET ANSI_NULLS 是 OFF 時，NULL = NULL 會傳回 TRUE。  
  
 在 WHERE 子句中使用含 **Boolean** 資料類型的運算式，來篩選符合搜尋條件，且在 IF 和 WHILE 之類流程控制語言陳述式中的資料列，例如：  
  
```  
-- Uses AdventureWorks  
  
DECLARE @MyProduct int;  
SET @MyProduct = 750;  
IF (@MyProduct <> 0)  
   SELECT ProductID, Name, ProductNumber  
   FROM Production.Product  
   WHERE ProductID = @MyProduct;  
```  
  
## <a name="see-also"></a>另請參閱  
 [運算式 &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)  
 [運算子 &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)  
  
  
