---
title: 偵錯工具無法顯示原始程式碼或反組譯碼 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd959a572e29e172f3acede5fe56a33547111086
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51720802"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>偵錯工具無法顯示原始程式碼或反組譯碼
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

這個錯誤為：  
  
 偵錯工具無法顯示目前位置的原始程式碼或反組譯碼。  
  
 此錯誤訊息的發生原因可能有幾種：  
  
-   所叫用的中斷點位置可能沒有原始程式碼，可是您正在偵錯不支援反組譯碼的語言。 開啟**中斷點**視窗中，找出中斷點，並將它刪除。  
  
-   若您正在偵錯指令碼，可能會叫用中斷點，但是程式中卻沒有任何執行緒。 選擇**步驟**或是**繼續**從**偵錯**繼續偵錯 功能表。  
  
-   安全性考量可能會禁止偵錯工具從您正在偵錯的程式中讀取堆疊、執行緒、暫存器和其他的內容資訊。 您正在偵錯 Web 應用程式，但沒有正確的使用權限來存取虛擬目錄時，最常發生這種情形。 請將虛擬目錄的安全性設成 [匿名]，然後再試一次。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯工具基礎](../debugger/debugger-basics.md)   
 [Visual Studio 偵錯](../debugger/debugging-in-visual-studio.md)   
 [在偵錯工具中檢視資料](../debugger/viewing-data-in-the-debugger.md)



