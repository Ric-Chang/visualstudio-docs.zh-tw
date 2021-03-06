---
title: 核心檢視 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 869980fe7bbb773d566dffd38088b003e3a97a3d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763004"
---
# <a name="cores-view"></a>核心檢視
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

核心檢視顯示執行緒執行如何對應至邏輯處理器核心。 如果您要撰寫伺服器應用程式，此檢視可使用執行緒同質性或執行緒集區管理協助您最佳化快取效能。 它也可以協助您檢查使用執行緒同質性可能讓跨核心移轉問題惡化的情況。 核心檢視有兩個部分：圖形和圖例。  
  
 圖形在 y 軸顯示邏輯核心數，在 x 軸顯示時間。 圖形中的每個執行緒都有唯一的色彩，以便您追蹤執行緒在核心之間隨時間的移動。 您可以在圖例區域中選取執行緒，篩選此圖形上的執行緒。  
  
 圖例區域有圖形中每一種色彩的項目。 每個項目會顯示執行緒色彩和名稱、跨核心內容切換的次數、內容切換總數和跨核心之內容切換的百分比。 圖例以遞減順序，依跨核心內容切換的次數排序。 只列出在顯示的時間範圍內執行的執行緒。  如果您縮放或平移，就會更新清單。  
  
## <a name="see-also"></a>請參閱  
 [並行視覺化檢視](../profiling/concurrency-visualizer.md)   
 [使用率檢視](../profiling/utilization-view.md)   
 [執行緒檢視](../profiling/threads-view-parallel-performance.md)
