---
title: "sys.dm_pdw_component_health_status (TRANSACT-SQL) |Microsoft 文件"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-non-specified
ms.prod_service: pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68cc3f7a-693c-4d5d-a76b-455352af8d7f
caps.latest.revision: 
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9de0ecd4e004d45f3cf56a5f9fcadd6563eb04f6
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2018
---
# <a name="sysdmpdwcomponenthealthstatus-transact-sql"></a>sys.dm_pdw_component_health_status (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  保留應用裝置元件的目前健全狀況的相關資訊。  
  
|資料行名稱|資料類型|Description|範圍|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**||不是 NULL|  
|component_id|int|元件的識別碼。 請參閱[sys.pdw_health_components &#40;TRANSACT-SQL &#41;](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md).<br /><br /> pdw_node_id、 component_id、 屬性識別碼和 component_instance_id 形成這個檢視的索引鍵。|不是 NULL|  
|property_id|**int**|屬性的識別碼。 請參閱[sys.pdw_health_component_properties &#40;TRANSACT-SQL &#41;](../../relational-databases/system-catalog-views/sys-pdw-health-component-properties-transact-sql.md).|NOT NULL|  
|component_instance_id|**nvarchar(255)**|識別元件的執行個體。 執行個體的 cpu，例如可能由 component_instance_id = 'CPU1'。<br /><br /> pdw_node_id、 component_id、 屬性識別碼和 component_instance_id 形成這個檢視的索引鍵。|NOT NULL|  
|property_value|**nvarchar(255)**|目前的屬性值。|NULL|  
|update_time|**datetime**|上次更新度量。|NOT NULL|  
  
## <a name="see-also"></a>另請參閱  
 [SQL 資料倉儲和平行處理資料倉儲動態管理檢視 &#40;TRANSACT-SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
