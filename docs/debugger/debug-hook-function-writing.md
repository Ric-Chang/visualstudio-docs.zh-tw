---
title: 撰寫偵錯攔截函式 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1ff144a30646ec29c022ba8e55c950e086179337
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941939"
---
# <a name="debug-hook-function-writing"></a>撰寫偵錯攔截函式
本節將說明一些您可以撰寫的自訂偵錯攔截函式，這些函式可讓您將程式碼插入偵錯工具正常處理中的某些預先定義點。  
  
## <a name="in-this-section"></a>本節內容  
 [用戶端區塊攔截函式](../debugger/client-block-hook-functions.md)  
 針對能夠驗證或報告儲存於 _CLIENT_BLOCK 區塊內資料內容的函式，提供撰寫的指引和原型 (Prototype)。  
  
 [配置攔截函式](../debugger/allocation-hook-functions.md)  
 定義配置攔截函式、瀏覽其不同用法、指出限制並提供原型。  
  
 [配置攔截和 CRT 記憶體配置](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 描述如果它們呼叫任何配置內部記憶體的 C 執行階段程式庫函式時，明確忽略 `_CRT_BLOCK` 區塊的配置攔截函式所受到的限制。 這個主題也列出如果配置攔截沒有忽略 `_CRT_BLOCK` 區塊的後果 (附範例)，以及如何變更預設配置攔截函式 **CrtDefaultAllocHook**。  
  
 [報告攔截函式](../debugger/report-hook-functions.md)  
 討論 `_CrtSetReportHook`，您可以使用這個函式來篩選報告，以著重在特定類型的配置。 這個主題也提供原型。  
  
## <a name="related-sections"></a>相關章節  
 [CRT 偵錯技術](../debugger/crt-debugging-techniques.md)  
 C 執行階段程式庫之偵錯技術的連結，包括使用 CRT 偵錯程式庫、報告巨集、`malloc` 和 `_malloc_dbg` 之間的差異、撰寫偵錯攔截函式和 CRT 偵錯堆積。