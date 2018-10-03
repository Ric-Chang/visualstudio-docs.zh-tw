---
title: 專案模型化 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], implementing project objects
- project models, automation
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 58262c6d4edda1dd0be7d147ae21645b3305bfaa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47487411"
---
# <a name="project-modeling"></a>將專案模型化
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[專案模型化](https://docs.microsoft.com/visualstudio/extensibility/internals/project-modeling)。  
  
您的專案實作標準專案物件，提供自動化的下一個步驟：<xref:EnvDTE.Projects>並`ProjectItems`集合，而`Project`和<xref:EnvDTE.ProjectItem>物件; 並且您的實作唯一剩餘的物件。 Dteinternal.h 檔案中，會定義這些標準的物件。 BscPrj 範例中，會提供標準的物件的實作。 您可以使用這些類別為模型來建立您自己的標準專案物件，並排顯示，就能從其他專案類型的專案物件。  
  
 自動化取用者會假設要能夠呼叫<xref:EnvDTE.Solution>(「`<UniqueProjName>")`並<xref:EnvDTE.ProjectItems>(`n`) 其中 n 是個取得特定方案的專案中的索引號碼。 進行這個自動化呼叫導致環境呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A>上適當的專案階層架構，傳遞 VSITEMID_ROOT 做 VSHPROPID_ExtObject VSHPROPID 參數做為項目識別碼參數。 `IVsHierarchy::GetProperty` 會傳回`IDispatch`提供核心的 automation 物件的指標`Project`您已實作的介面。  
  
 以下是語法`IVsHierarchy::GetProperty`。  
  
 `HRESULT GetProperty (`  
  
 `VSITEMID` `itemid`,  
  
 `VSHPROPID` `propid`,  
  
 `VARIANT` `*pvar`  
  
 `);`  
  
 專案容納巢狀結構，並使用集合來建立群組的專案項目。 階層如下所示。  
  
```  
Projects  
  |– Project  
      |– ProjectItems (a collection of ProjectItem)  
          |– ProjectItem (single object) or ProjectItems (another collection)  
```  
  
 巢狀結構表示<xref:EnvDTE.ProjectItem>物件可以是<xref:EnvDTE.ProjectItems>集合中的相同時間因為`ProjectItems`集合可以包含巢狀的物件。 在基本的專案範例不會示範這個巢狀結構。 藉由實作`Project`物件時，您參與特性之整體的自動化模型的設計類似樹狀目錄結構。  
  
 專案自動化遵循下圖中的路徑。  
  
 ![Visual Studio 專案物件](../../extensibility/internals/media/projectobjects.gif "ProjectObjects")  
專案自動化  
  
 如果您不會實作`Project`物件時，環境仍會傳回泛型`Project`物件，其中包含專案的名稱。  
  
## <a name="see-also"></a>另請參閱  
 <xref:EnvDTE.Projects>   
 <xref:EnvDTE.ProjectItem>   
 <xref:EnvDTE.ProjectItems>
