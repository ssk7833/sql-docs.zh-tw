---
title: "SQLSetPos （桌面資料庫驅動程式） |Microsoft 文件"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLSetPos function [ODBC], Desktop Database Drivers
ms.assetid: 8ef027ec-8512-48fe-8fe2-2ff7cd81e331
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 2b630be96f099e1f2553c8d03b9896f32ea3e670
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="sqlsetpos-desktop-database-drivers"></a>SQLSetPos （桌面資料庫驅動程式）
大量模型語意**SQLSetPos**呼叫*irow*支援等於 0 的引數。  
  
 支援 SQL_LOCK_NO_CHANGE *fLock*。 不支援 SQL_LOCK_EXCLUSIVE 和 SQL_LOCK_UNLOCK。  
  
 **SQLSetPos**支援可更新的聯結。 (如需詳細資訊，請參閱*Microsoft Jet 資料庫引擎程式設計人員指南*。)