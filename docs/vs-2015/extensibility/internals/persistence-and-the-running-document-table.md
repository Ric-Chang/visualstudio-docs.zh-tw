---
title: 持續性和執行記錄資料表 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b734d21950fd3765a7c331bbcdc47177f48e2b0a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51726090"
---
# <a name="persistence-and-the-running-document-table"></a>持續性與執行中的文件資料表
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

在  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE 中，專案會完全負責管理其專案，這些項目在完成使用服務，持續性<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>。 文件是在 Visual Studio 環境中的持續性的基本單位。 專案協調開啟、 儲存和重新命名的文件與執行文件資料表 (RDT)，會追蹤所有開啟的文件的狀態的資源。  
  
## <a name="managing-persistence"></a>管理持續性  
 專案來控制環境的持續性服務實作<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem>介面。 雖然環境永遠不會直接詢問要保存本身的文件時，它會要求儲存文件的主控專案 （或階層）。 這可讓專案，以將其專案項目資料儲存到本機檔案、 遠端檔案、 資料庫、 儲存機制或其他媒體。  
  
 全域環境中維護 RDT。 環境會維護所有已開啟視窗的項目和文件中 RDT，如此才能接收特殊的通知，例如方案已關閉時。 RDT 此外，可讓要追蹤其對應的節點中的環境**方案總管 中**。 RDT 會維護每個開啟的、 永久性的物件，包括專案檔和專案項目文件的一筆記錄。  
  
## <a name="see-also"></a>另請參閱  
 [執行文件資料表](../../extensibility/internals/running-document-table.md)   
 [IDE 中的選取項目和貨幣](../../extensibility/internals/selection-and-currency-in-the-ide.md)

