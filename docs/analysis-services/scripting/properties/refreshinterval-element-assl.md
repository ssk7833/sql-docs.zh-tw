---
title: "RefreshInterval 元素 (ASSL) |Microsoft 文件"
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: RefreshInterval Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: RefreshInterval
helpviewer_keywords: RefreshInterval element
ms.assetid: 2761d26a-5fb0-452c-9a89-12f8dc658c33
caps.latest.revision: "37"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 1cc3ba13afdae0f85272564985cd7e002a78a24b
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2018
---
# <a name="refreshinterval-element-assl"></a>RefreshInterval 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]指定的繫結與父元素相關聯的資料重新整理的間隔。  
  
## <a name="syntax"></a>語法  
  
```xml  
  
<DimensionBinding> <!-- or MeasureGroupBinding, ProactiveCachingIncrementalProcessingBinding, ProactiveCachingQueryBinding -->  
   ...  
   <RefreshInterval>...</RefreshInterval>  
   ...  
</DimensionBinding>  
```  
  
## <a name="element-characteristics"></a>元素特性  
  
|特性|描述|  
|--------------------|-----------------|  
|資料類型和長度|XML 持續時間|  
|預設值|上階或父系是[ProactiveCachingIncrementalProcessingBinding](../../../analysis-services/scripting/data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md)或[ProactiveCachingQueryBinding](../../../analysis-services/scripting/data-type/proactivecachingquerybinding-data-type-assl.md)，預設值是 PT 順序為 1。 在其他情況下，它是 PT1m。|  
|基數|0-1：只能出現一次的選擇性元素。|  
  
## <a name="element-relationships"></a>元素關聯性  
  
|關聯性|元素|  
|------------------|-------------|  
|父元素|[DimensionBinding](../../../analysis-services/scripting/data-type/dimensionbinding-data-type-assl.md)， [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md)， [ProactiveCachingIncrementalProcessingBinding](../../../analysis-services/scripting/data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md)， [ProactiveCachingQueryBinding](../../../analysis-services/scripting/data-type/proactivecachingquerybinding-data-type-assl.md)|  
|子元素|無|  
  
## <a name="remarks"></a>備註  
 對應至父系的項目**RefreshInterval**在 「 分析管理物件 (AMO) 物件模型是<xref:Microsoft.AnalysisServices.DimensionBinding>， <xref:Microsoft.AnalysisServices.MeasureGroupBinding>， <xref:Microsoft.AnalysisServices.ProactiveCachingIncrementalProcessingBinding>，和<xref:Microsoft.AnalysisServices.ProactiveCachingQueryBinding>。  
  
## <a name="see-also"></a>請參閱  
 [屬性 &#40;ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
