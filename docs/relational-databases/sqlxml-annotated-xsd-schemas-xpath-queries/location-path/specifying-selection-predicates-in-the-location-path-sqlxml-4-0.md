---
title: "指定選取述詞中的位置路徑 (SQLXML 4.0) |Microsoft 文件"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: sqlxml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- predicates [SQLXML]
- position-based filtering [SQLXML]
- XPath queries [SQLXML], location paths
- filtering [SQLXML]
- location path for XPath query
ms.assetid: dbef4cf4-a89b-4d7e-b72b-4062f7b29a80
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 08a27de5e9c528d3e49156df804f19376ae5a6bd
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2018
---
# <a name="specifying-selection-predicates-in-the-location-path-sqlxml-40"></a>在位置路徑 (SQLXML 4.0) 中指定選取述詞
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
述詞會篩選與軸有關的節點集 (與 SELECT 陳述式中的 WHERE 子句相似)， 並指定在方括號之間。 對於節點集內要篩選的每一個節點，該節點會當做內容節點，而且節點集內的節點數目會當做內容大小，然後評估述詞運算式。 如果述詞運算式評估該節點為 TRUE，則產生的節點集會包含該節點。  
  
 XPath 也允許以位置為基礎的篩選。 評估為數字的述詞運算式會選取該序數節點。 例如，位置路徑 `Customer[3]` 會傳回第三客戶。 但是不支援這類數值述詞， 只支援傳回布林值的述詞運算式。  
  
> [!NOTE]  
>  這個 XPath 實作的限制相關資訊及它與 W3C 規格之間的差異，請參閱[簡介使用 XPath 查詢 &#40;SQLXML 4.0 &#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/introduction-to-using-xpath-queries-sqlxml-4-0.md).  
  
## <a name="selection-predicate-example-1"></a>選取述詞： 範例 1  
 下列的 XPath 運算式 （位置路徑） 從目前所有的內容節點選取**\<客戶 >**具有元素子系**CustomerID**值為 ALFKI 屬性：  
  
```  
/child::Customer[attribute::CustomerID="ALFKI"]  
```  
  
 在這個 XPath 查詢中，`child` 和 `attribute` 是軸的名稱。 `Customer` 是節點測試 (TRUE 如果`Customer`是**\<項目節點 >**，因為**\<項目 >**是主要節點類型`child`軸)。 `attribute::CustomerID="ALFKI"` 是述詞。 在述詞，`attribute`是軸和`CustomerID`是節點測試 (TRUE 如果**CustomerID**是內容節點的屬性，因為**\<屬性 >**是主體節點類型**屬性**軸)。  
  
 使用縮寫語法，XPath 查詢也可以指定為：  
  
```  
/Customer[@CustomerID="ALFKI"]  
```  
  
## <a name="selection-predicate-example-2"></a>選取述詞： 範例 2  
 下列的 XPath 運算式 （位置路徑） 從目前所有的內容節點選取**\<順序 >**孫系有**SalesOrderID**值 1 屬性：  
  
```  
/child::Customer/child::Order[attribute::SalesOrderID="1"]  
```  
  
 在這個 XPath 運算式中，`child` 和 `attribute` 是軸的名稱。 `Customer`、`Order` 和 `SalesOrderID` 是節點測試。 `attribute::OrderID="1"` 是述詞。  
  
 使用縮寫語法，XPath 查詢也可以指定為：  
  
```  
/Customer/Order[@SalesOrderID="1"]  
```  
  
## <a name="selection-predicate-example-3"></a>選取述詞： 範例 3  
 下列的 XPath 運算式 （位置路徑） 從目前所有的內容節點選取**\<客戶 >**有一個以上的子系 **\<ContactName >**子系：  
  
```  
child::Customer[child::ContactName]  
```  
  
 這個範例假設 **\<ContactName >**是子元素的**\<客戶 >**指的 XML 文件中的項目*元素中心的對應*註解式 XSD 結構描述中。  
  
 在這個 XPath 運算式中，`child` 是軸的名稱。 `Customer` 是節點測試 (TRUE 如果`Customer`是**\<項目 >**  節點，因為**\<項目 >**是主要節點類型`child`軸)。 `child::ContactName` 是述詞。 在述詞，`child`是軸和`ContactName`是節點測試 (TRUE 如果`ContactName`是**\<項目 >**節點)。  
  
 此運算式只會傳回**\<客戶 >**元素子系內容節點具有 **\<ContactName >**元素子系。  
  
 使用縮寫語法，XPath 查詢也可以指定為：  
  
```  
Customer[ContactName]  
```  
  
## <a name="selection-predicate-example-4"></a>選取述詞： 範例 4  
 下列 XPath 運算式選取**\<客戶 >**元素子系內容節點沒有 **\<ContactName >**元素子系：  
  
```  
child::Customer[not(child::ContactName)]  
```  
  
 這個範例假設 **\<ContactName >**是子元素的**\<客戶 >**中不需要在 XML 文件和 ContactName 欄位中的項目資料庫。  
  
 在此範例中，`child` 為軸。 `Customer` 是節點測試 (TRUE 如果`Customer`是\<元素 > 節點)。 `not(child::ContactName)` 是述詞。 在述詞，`child`是軸和`ContactName`是節點測試 (TRUE 如果`ContactName`是\<項目 > 節點)。  
  
 使用縮寫語法，XPath 查詢也可以指定為：  
  
```  
Customer[not(ContactName)]  
```  
  
## <a name="selection-predicate-example-5"></a>選取述詞： 範例 5  
 下列 XPath 運算式會選取從目前內容節點所有**\<客戶 >**具有子系**CustomerID**屬性：  
  
```  
child::Customer[attribute::CustomerID]  
```  
  
 在此範例中，`child`是軸和`Customer`是節點測試 (TRUE 如果`Customer`是\<元素 > 節點)。 `attribute::CustomerID` 是述詞。 在述詞，`attribute`是軸和`CustomerID`是述詞 (TRUE 如果`CustomerID`是**\<屬性 >**節點)。  
  
 使用縮寫語法，XPath 查詢也可以指定為：  
  
```  
Customer[@CustomerID]  
```  
  
## <a name="selection-predicate-example-6"></a>選取述詞：範例 6  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 包含支援 XPath 查詢包含交叉乘積中述詞，如下列範例所示：  
  
```  
Customer[Order/@OrderDate=Order/@ShipDate]  
```  
  
 這個查詢會選取所有客戶，其方式是使用任何 `Order`，其中 `OrderDate` 要等於任何 `ShipDate` 的 `Order`。  
  
## <a name="see-also"></a>另請參閱  
 [註解式的 XSD 結構描述 &#40; 簡介SQLXML 4.0 &#41;](../../../relational-databases/sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md)   
 [用戶端 XML 格式化 &#40;SQLXML 4.0 &#41;](../../../relational-databases/sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
