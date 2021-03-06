---
title: Vspackage 和 Managed 的封裝架構 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed package framework
- VSPackages, managed package framework
- managed VSPackages, managed package framework
ms.assetid: e8d80e0f-6b5b-4baf-a7df-59fd808c60cd
caps.latest.revision: 16
manager: douge
ms.openlocfilehash: 2e265a342ec32abea40ab9b352b5735079462a46
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49227977"
---
# <a name="vspackages-and-the-managed-package-framework"></a>VSPackage 和 Managed 封裝架構
您可以建立 VSPackage 使用 managed 封裝架構 (MPF) 類別，而不是使用 COM interop 的類別，以減少開發時間。  
  
 有兩種方式可建立 managed 的 VSPackage:  
  
-   使用[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]Package 專案範本  
  
     如需詳細資訊，請參閱 <<c0> [ 逐步解說： 建立功能表命令，使用 Visual Studio Package 範本](http://msdn.microsoft.com/library/1985fa7d-aad4-4866-b356-a125b6a246de)。  
  
-   建立不含 VSPackage [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Package 專案範本  
  
     比方說，您可以將範例 VSPackage 複製，並變更 Guid 和名稱。 您可以找到範例的 VSX 節[程式碼庫](http://code.msdn.microsoft.com/vsx/)。  
  
## <a name="in-this-section"></a>本節內容  
 [Managed 封裝架構類別](../misc/managed-package-framework-classes.md)  
 描述並列出 MPF 類別命名空間和 DLL 檔案。  
  
## <a name="related-sections"></a>相關章節  
 [逐步解說： 使用 Visual Studio Package 範本建立功能表命令](http://msdn.microsoft.com/library/1985fa7d-aad4-4866-b356-a125b6a246de)  
 說明如何建立 managed 的 VSPackage。  
  
 [Managed VSPackages](../misc/managed-vspackages.md)  
 介紹適用於 managed 程式碼的 Vspackage 的層面。