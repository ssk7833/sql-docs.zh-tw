---
title: "Analysis Services 連線管理員 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: connection-manager
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connections [Integration Services], Analysis Services
- connection managers [Integration Services], Analysis Services
- Analysis Services connection manager
ms.assetid: 9f9cadad-a1d0-4db5-98f5-df5dbbec1be4
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a140037121a7c33d23d6485c11684c0ba6a69505
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2018
---
# <a name="analysis-services-connection-manager"></a>Analysis Services 連接管理員
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 連線管理員能使封裝連接到執行 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 資料庫的伺服器，或者連接到提供 Cube 和維度資料存取權的 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 專案。 在 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 中開發封裝時，您只能連接到 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]專案。 在執行階段，封裝會連接到您部署 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 專案的伺服器和資料庫。  
  
 工作 (例如「[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 執行 DDL」工作和「[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 處理」工作) 及目的地 (例如「資料採礦模型定型」目的地) 都使用 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 連線管理員。  
  
 如需 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 資料庫的詳細資訊，請參閱[多維度模型資料庫 &#40;SSAS&#41;](../../analysis-services/multidimensional-models/multidimensional-model-databases-ssas.md)。  
  
## <a name="configuration-of-the-analysis-services-connection-manager"></a>Analysis Services 連接管理員的組態  
 當您將 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 連線管理員加入封裝時， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 會建立一個連線管理員 (在執行階段會解析為 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 連接)、設定連線管理員屬性，並將該連線管理員加入封裝上的 **Connections** 集合。 連線管理員的 **ConnectionManagerType** 屬性會設為 **MSOLAP100**。  
  
 您可以利用下列方式設定 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 連線管理員：  
  
-   提供一個設定為符合 Microsoft OLE Provider for Analysis Services 提供者需求的連接字串。  
  
-   指定要連接的 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 執行個體或 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 專案。  
  
-   如果您要連接到 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]執行個體，請指定驗證模式。  
  
-   指示是否在執行階段保留從連接管理員建立的連接。  
  
 您可以透過 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 設計師或以程式設計方式設定屬性。  
  
 如需有關可以在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 設計師中設定之屬性的詳細資訊，請按下列其中一個主題：  
  
-   [加入 Analysis Services 連接管理員對話方塊 UI 參考](../../integration-services/connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)  
  
 如需以程式設計方式設定連線管理員的資訊，請參閱 <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> 和 [以程式設計方式加入連線](../../integration-services/building-packages-programmatically/adding-connections-programmatically.md)專案。  
  
  
