---
title: "建立及結束執行緒 |Microsoft 文件"
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
- terminating threads [ODBC]
- threads [ODBC]
- multithreaded applications [ODBC]
ms.assetid: a2cf98ef-1c71-4742-8ee2-b53fd8e04333
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 62950dba2174baac8e3bc34c60f268e07304fa5a
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-terminating-threads"></a>建立及結束執行緒
使用 ODBC 的多執行緒應用程式應該呼叫 Microsoft® C++® 執行階段程式庫函式**_beginthread**和**_endthread** (或**_beginthreadex**和**_endthreadex**) 來建立和結束呼叫 ODBC 驅動程式管理員的執行緒。 如果應用程式呼叫 Microsoft Windows NT® 函式**CreateThread**和**EndThread**相反地，記憶體流失會發生，因為驅動程式管理員和某些 ODBC 驅動程式呼叫 C 執行階段函式藉由呼叫建立的執行緒上將無法運作**CreateThread**。 如需詳細資訊，請參閱 Microsoft Windows® 文件。
