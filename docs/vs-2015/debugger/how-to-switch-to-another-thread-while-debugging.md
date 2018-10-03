---
title: 如何： 偵錯時切換到另一個執行緒 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c682ddff5fd4dc44fe79fa81c1615362f8121e5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47491917"
---
# <a name="how-to-switch-to-another-thread-while-debugging"></a>如何：在偵錯時切換到另一個執行緒
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[如何： 切換至另一個執行緒偵錯同時](https://docs.microsoft.com/visualstudio/debugger/how-to-switch-to-another-thread-while-debugging)。  
  
當您偵錯多執行緒應用程式時，您可以使用數個方法中的任何一種方法，將內容從目前使用的執行緒切換至另一個執行緒。  
  
### <a name="to-switch-to-any-thread-that-appears-in-the-threads-window"></a>切換至執行緒視窗中出現的任何執行緒  
  
-   按兩下執行緒。  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>若要切換至來源視窗中的執行緒  
  
-   在左側的裝訂邊上，以滑鼠右鍵按一下執行緒指標，並指向**切換至**，然後按一下您要切換該執行緒的名稱。 捷徑功能表只會顯示該特定位置上的執行緒。  
  
     如果沒有指標出現，請以滑鼠右鍵按一下**執行緒** 視窗，並確認**在來源中顯示執行緒**已選取。  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>若要切換至偵錯位置工具列中的執行緒  
  
1.  在 [**偵錯位置**工具列上，按一下**執行緒**] 方塊中。  
  
2.  在清單中，按一下您要切換至哪個執行緒。  
  
## <a name="see-also"></a>另請參閱  
 [對多執行緒應用程式進行偵錯](../debugger/debug-multithreaded-applications-in-visual-studio.md)


