---
title: MSSQLSERVER_1222 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: errors-events
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 743031212890f81073ac39bb617170cc0e4d218e
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver1222"></a>MSSQLSERVER_1222
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>詳細資料  
  
|||  
|-|-|  
|產品名稱|SQL Server|  
|事件識別碼|1222|  
|事件來源|MSSQLSERVER|  
|元件|SQLEngine|  
|符號名稱|LK_TIMEOUT|  
|訊息文字|鎖定要求的逾時期間已過。|  
  
## <a name="explanation"></a>說明  
其他交易鎖定必要資源的時間比這項查詢可以等候的時間還長。  
  
## <a name="user-action"></a>使用者動作  
執行下列工作來減少問題：  
  
1.  如果可以的話，請找出鎖定必要資源的交易。 使用 **sys.dm_os_waiting_tasks** 和 **sys.dm_tran_locks** 動態管理檢視。  
  
2.  如果交易仍然鎖定資源，請依適當情況結束該交易。  
  
3.  重新執行查詢。  
  
如果這項錯誤經常發生，請變更鎖定逾時期限，或請修改造成問題的交易，以縮短這些交易鎖定資源的時間。  
  
