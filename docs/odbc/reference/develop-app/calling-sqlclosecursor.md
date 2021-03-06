---
title: "呼叫 SQLCloseCursor |Microsoft 文件"
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
- application upgrades [ODBC], SQLCloseCursor
- backward compatibility [ODBC], SqlCloseCursor
- SQLCloseCursor function [ODBC], calling
- upgrading applications [ODBC], SQLCloseCursor
- compatibility [ODBC], SQLCloseCursor
ms.assetid: ef448c39-a9ad-4f07-8ef3-65bd4cef672a
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3c3870a36138fd55a2e404d38e28db327990ba1b
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="calling-sqlclosecursor"></a>呼叫 SQLCloseCursor
因為**SQLCloseCursor**幾乎相同**SQLFreeStmt** SQL_CLOSE，與驅動程式管理員未對應此函式。 取代函式對應，讓現有的 ODBC 2*.x*應用程式可以輕鬆地將移至 ODBC 3。*x*使用新的函式。 這類移動可讓您更輕鬆地開始使用新的 ODBC 3 這類應用程式。*x*模組化的方式中的條件式程式碼內的功能。 **SQLCloseCursor**不代表任何新功能。 應用程式不會將移至無法取得任何優點**SQLCloseCursor**從**SQLFreeStmt**與 SQL_CLOSE。
