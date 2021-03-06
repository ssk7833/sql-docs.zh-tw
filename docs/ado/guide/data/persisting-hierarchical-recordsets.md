---
title: "保存的階層式資料錄集 |Microsoft 文件"
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
helpviewer_keywords:
- hierarchical Recordsets [ADO], persisting
- persisting hierarchical Recordsets [ADO]
- data shaping [ADO], hierarchical Recordsets
ms.assetid: 43798bb5-98a6-4ad6-9bf8-78154b3a1827
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3c1248c9691838bb7834748d6e243771b4bd0bba
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="persisting-hierarchical-recordsets"></a>保存的階層式資料錄集
您可以儲存階層式**資料錄集**藉由呼叫 ADTG 或 XML 格式檔[儲存](../../../ado/reference/ado-api/save-method.md)方法。 不過，兩個限制會套用儲存階層式時**資料錄集**s 以 XML 格式： 如果無法儲存在 XML 中階層式**資料錄集**包含擱置的更新，而且無法儲存參數化階層式**資料錄集**。  
  
 如需資料成形提供者的詳細資訊，請參閱[Microsoft Data Shaping Service 的 OLE DB](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) (ADO) 和[的 OLE DB Data Shaping Service 概觀](http://msdn.microsoft.com/en-us/9f51e471-8e85-448e-9fb8-b64bbf767bf3)。  
  
## <a name="see-also"></a>另請參閱  
 [資料成形範例](../../../ado/guide/data/data-shaping-example.md)   
 [型式圖形文法](../../../ado/guide/data/formal-shape-grammar.md)   
 [一般 Shape 命令](../../../ado/guide/data/shape-commands-in-general.md)
