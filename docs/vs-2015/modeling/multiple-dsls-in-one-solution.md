---
title: 一個方案中的多個 Dsl |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e668620-6217-4e87-aea7-e9036776c8e4
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8bf5e3d69b67cf51c1e70ec8ffe9e91d87a1dcbe
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49820170"
---
# <a name="multiple-dsls-in-one-solution"></a>一個方案中有多個 DSL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

您可以將數個 DSL 封裝成單一方案的一部分，以便能夠一起安裝。  
  
 用來整合多個 DSL 的方法有幾種。 如需詳細資訊，請參閱[使用 Visual Studio Modelbus 整合模型](../modeling/integrating-models-by-using-visual-studio-modelbus.md)並[如何： 加入拖放處理常式](../modeling/how-to-add-a-drag-and-drop-handler.md)並[自訂複製行為](../modeling/customizing-copy-behavior.md)。  
  
### <a name="to-build-more-than-one-dsl-in-the-same-solution"></a>在同一個方案中建置多個 DSL  
  
1. 建立兩個或多個 DSL 方案和一個 VSIX 專案，然後將所有專案加入至一個方案。  
  
   -   若要建立新的 VSIX 專案： 在**新的專案**對話方塊中，選取**Visual C#**，**擴充性**， **VSIX 專案**。  
  
   -   在 VSIX 方案目錄中建立兩個或多個 DSL 方案。  
  
        針對每個 DSL，開啟 Visual Studio 的新執行個體。 建立新的 DSL，然後指定與 VSIX 方案相同的方案資料夾。  
  
        確定使用不同的副檔名建立各個 DSL。  
  
   -   變更的名稱**Dsl**並**DslPackage**專案，使其完全不同。 例如：`Dsl1`、`DslPackage1`、`Dsl2`、`DslPackage2`。  
  
   -   在每個**DslPackage\*\source.extension.tt**，這行更新為正確的 Dsl 專案名稱：  
  
        `string dslProjectName = "Dsl2";`  
  
   -   在 VSIX 方案中，加入 Dsl * 和 DslPackage\*專案。  
  
        您可能想將每組專案置於各自的方案資料夾中。  
  
2. 合併 DSL 的 VSIX 資訊清單：  
  
   1.  開啟_您的 vsix 專案_**\source.extension.manifest**。  
  
   2.  針對每個 DSL 中，選擇**加入內容**並新增：  
  
       -   `Dsl*` 專案做為**MEF 元件**  
  
       -   `DslPackage*` 專案做為**MEF 元件**  
  
       -   `DslPackage*` 專案做為**VS 套件**  
  
3. 建置方案。  
  
   產生的 VSIX 會同時安裝這兩個 DSL。 您可以使用 f5 鍵，就可以將它測試它們，或部署_您的 vsix 專案_**\bin\Debug\\\*.vsix**。  
  
## <a name="see-also"></a>另請參閱  
 [使用 Visual Studio Modelbus 整合模型](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [如何： 加入拖放處理常式](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [自訂複製行為](../modeling/customizing-copy-behavior.md)



