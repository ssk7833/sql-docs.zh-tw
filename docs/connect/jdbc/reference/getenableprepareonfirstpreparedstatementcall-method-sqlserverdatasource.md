---
title: "getEnablePrepareOnFirstPreparedStatementCall 方法 (SQLServerDataSource) |Microsoft 文件"
ms.custom: 
ms.date: 01/19/2018
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 766a00c0a92c3df65e39bbfcd7ad87c5529a5b98
ms.sourcegitcommit: 9d0467265e052b925547aafaca51e5a5e93b7e38
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2018
---
# <a name="getenableprepareonfirstpreparedstatementcall-method-sqlserverdatasource"></a>getEnablePrepareOnFirstPreparedStatementCall 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  傳回的值**enablePrepareOnFirstPreparedStatementCall**連接屬性。 如果此設定會傳回 false 會呼叫 sp_executesql 備妥的陳述式的第一次的執行，並不準備的陳述式，它會呼叫 sp_prepexec 和實際設定的已備妥的陳述式控制代碼，第二次執行發生之後。 下列執行，會呼叫 sp_execute。 這減輕 sp_unprepare 備妥的陳述式需要關閉如果陳述式只執行一次。 
  
## <a name="syntax"></a>語法  
  
```
public boolean getEnablePrepareOnFirstPreparedStatementCall();  
```  
  
## <a name="return-value"></a>傳回值  
 傳回**布林**值**enablePrepareOnFirstPreparedStatementCall**連接屬性。  
  
## <a name="exceptions"></a>例外狀況  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
 
## <a name="remarks"></a>備註  
 這個方法是從 JDBC 驅動程式版本 6.4 可用且向外。
 
## <a name="see-also"></a>另請參閱  
 [SQLServerDataSource 成員](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 類別](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
