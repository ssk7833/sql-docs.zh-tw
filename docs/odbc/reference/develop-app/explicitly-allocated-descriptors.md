---
title: "明確配置描述元 |Microsoft 文件"
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
- descriptors [ODBC], allocating and freeing
- explicitly allocated descriptors [ODBC]
- allocating and freeing descriptors [ODBC]
ms.assetid: f590251d-56a6-4d58-a405-9e85e68fbc47
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 791d7620afc4f952ccb99c80cad980ebd2e2e9ea
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="explicitly-allocated-descriptors"></a>明確配置描述元
應用程式可以明確地配置隨時連線到資料庫的連接上的應用程式描述元。 藉由指定該描述元控制代碼，以在陳述式的屬性可讓您處理使用**SQLSetStmtAttr**，應用程式會引導驅動程式使用該描述元取代對應的隱含地配置應用程式描述元。 應用程式無法指定替代的實作描述元。  
  
 應用程式可以關聯多個陳述式明確配置描述項。 應用程式確實連接到資料庫時，才描述元可以是明確配置描述項。 應用程式可以釋放這類描述元明確地或隱含的方式釋出其連線。
