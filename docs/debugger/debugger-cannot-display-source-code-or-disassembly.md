---
title: 偵錯工具無法顯示原始程式碼或反組譯碼
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fe3d745622666bd6458d5c3de916bc7b7787292e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54916455"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>偵錯工具無法顯示原始程式碼或反組譯碼
這個錯誤為：  
  
 偵錯工具無法顯示目前位置的原始程式碼或反組譯碼。  
  
 此錯誤訊息的發生原因可能有幾種：  
  
-   所叫用的中斷點位置可能沒有原始程式碼，可是您正在偵錯不支援反組譯碼的語言。 開啟**中斷點**視窗中，找出中斷點，並將它刪除。  
  
-   若您正在偵錯指令碼，可能會叫用中斷點，但是程式中卻沒有任何執行緒。 從 [偵錯] 功能表選擇 [逐步執行] 或 [繼續]，以繼續偵錯。  
  
-   安全性考量可能會禁止偵錯工具從您正在偵錯的程式中讀取堆疊、執行緒、暫存器和其他的內容資訊。 您正在偵錯 Web 應用程式，但沒有正確的使用權限來存取虛擬目錄時，最常發生這種情形。 請將虛擬目錄的安全性設成 [匿名]，然後再試一次。  
  
## <a name="see-also"></a>請參閱
 [Visual Studio 偵錯](../debugger/index.md)  
 [偵錯工具簡介](../debugger/debugger-feature-tour.md)  
 [在偵錯工具中檢視資料](../debugger/viewing-data-in-the-debugger.md)