---
title: "Reporting Services 延伸模組程式庫 |Microsoft 文件"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- namespaces [Reporting Services]
- Reporting Services, extending
- extensions [Reporting Services], library
- library [Reporting Services]
ms.assetid: e8eff470-64d6-41c3-b98b-5ec916c121c3
caps.latest.revision: 33
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: b9a1ce1e388575d6d5b9b46a00dbc85ae8cde84b
ms.contentlocale: zh-tw
ms.lasthandoff: 06/22/2017

---
# <a name="reporting-services-extension-library"></a>Reporting Services 延伸模組程式庫
  Reporting Services 延伸模組程式庫是一組包括在 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 中的類別、介面和值類型。 此程式庫提供存取系統功能，而且是所在的基礎[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]應用程式可以用來擴充[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]元件。  
  
## <a name="namespaces"></a>命名空間  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 延伸程式庫提供下列命名空間。  
  
 <xref:Microsoft.ReportingServices.DataProcessing>  
 包含的類別與介面可讓您建立元件並擴充 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 的資料處理功能。  
  
 <xref:Microsoft.ReportingServices.Interfaces>  
 包含的類別與介面，可讓您透過自己的傳遞延伸模組建構和傳送自訂通知給使用者，並為 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 建立自訂安全性延伸模組。  
  
 **Microsoft.ReportingServices.ReportRendering**  
 包含的類別與介面可讓您擴充 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 的轉譯功能。 透過使用此命名空間的成員以及 <xref:Microsoft.ReportingServices.Interfaces> 命名空間的成員，就可以為 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 建立自己的自訂轉譯延伸模組。  
  
## <a name="see-also"></a>另請參閱  
 [Reporting Services 延伸模組](../../reporting-services/extensions/reporting-services-extensions.md)  
  
  