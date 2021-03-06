---
title: 在 DSL 定義中加入擴充功能 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07e133be-92ab-4936-a02b-45d2012bd0a6
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 9c3e74f66edc0a8b33ad1fe8205cc02cd0e80054
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49866151"
---
# <a name="adding-extensions-to-dsl-definitions"></a>在 DSL 定義中加入擴充功能
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DSL 定義延伸模組可讓您建立的特定領域語言 (DSL) 延伸模組套件。 DSL 的延伸模組，其包含在 Visual Studio 整合擴充功能 (VSIX)，可以安裝在使用者的電腦，做為 DSL 相同的方式。 額外的功能可動態啟用及停用在執行階段。 不需要針對延伸模組，明確設計 Dsl 和擴充功能可以設計成更新版本，或由協力廠商沒有改變擴充的 DSL。  
  
 其他功能包括：  
  
- 模型和呈現項目的屬性  
  
- 圖案和接點的裝飾項目  
  
- 類別、 關聯性、 圖形和連接器  
  
- 驗證條件約束  
  
- 工具箱項目和索引標籤  
  
  擴充 DSL 的使用者可以建立和儲存模型，包含執行個體的其他功能，並已安裝適當的延伸模組的其他使用者可以讀取這些。 尚未安裝擴充功能的使用者無法使用額外的功能，但是它們可以更新，並儲存模型，而不會遺失的其他功能。  
  
  範例程式碼和有關這項功能的詳細資訊，請參閱[Visual Studio Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=186128)網站。  
  
## <a name="see-also"></a>另請參閱  
 [Visual Studio Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=186128)



