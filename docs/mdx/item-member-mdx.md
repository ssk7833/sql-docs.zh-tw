---
title: "Item （成員） (MDX) |Microsoft 文件"
ms.custom: 
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ITEM
dev_langs: kbMDX
helpviewer_keywords: Item function
ms.assetid: 71cca249-910b-4ecd-9097-1a17b224e219
caps.latest.revision: "35"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: db417d352d7e2e30ebd81ba64afba24f1777c2ee
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2018
---
# <a name="item-member-mdx"></a>Item (成員) (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  傳回一個來自指定 Tuple 的成員。  
  
## <a name="syntax"></a>語法  
  
```  
  
Tuple_Expression.Item( Index )  
```  
  
## <a name="arguments"></a>引數  
 *Tuple_Expression*  
 傳回 Tuple 的有效多維度運算式 (MDX) 運算式。  
  
 *Index*  
 有效的數值運算式，會依所要傳回之 Tuple 中的位置指定特定的成員。  
  
## <a name="remarks"></a>備註  
 **項目**函式會傳回指定 tuple 成員。 函式會傳回所指定的以零為起始位置，請參閱*索引*。  
  
## <a name="example"></a>範例  
 下列範例會傳回成員 `[2003]` - 在資料行上 `[Date].[Calendar Year].&[2003], [Measures].[Internet Sales Amount] ).` Tuple 的第一個項目。  
  
 `SELECT`  
  
 `{( [Date].[Calendar Year].&[2003], [Measures].[Internet Sales Amount] ).Item(0)} ON 0`  
  
 `,{[Measures].[Reseller Sales Amount]} ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>請參閱  
 [MDX 函數參考 &#40;MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
