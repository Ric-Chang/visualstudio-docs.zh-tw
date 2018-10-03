---
title: 傳送所需的事件 |Microsoft Docs
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
- debugging [Debugging SDK], required events
ms.assetid: 08319157-43fb-44a9-9a63-50b919fe1377
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d1a3803b12c2941f9e76d1bb97d5885940197192
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498885"
---
# <a name="sending-the-required-events"></a>傳送所需的事件
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[所需的事件傳送](https://docs.microsoft.com/visualstudio/extensibility/debugger/sending-the-required-events)。  
  
使用此程序傳送必要的事件。  
  
## <a name="process-for-sending-required-events"></a>傳送必要的事件的處理序  
 下列事件是必要的在這個順序，當建立偵錯引擎 (DE)，並將它連結至程式：  
  
1.  傳送[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)事件工作階段的偵錯管理員 (SDM) DE 初始化偵錯的處理序中的一或多個程式時的物件。  
  
2.  當要偵錯程式附加至時，傳送[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) SDM 事件物件。 此事件可能會停止 」 事件，視您的引擎設計而定。  
  
3.  如果程式附加至處理序啟動時，傳送[IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)通知 IDE 新執行緒的 SDM 事件物件。 此事件可能會停止 」 事件，視您的引擎設計而定。  
  
4.  傳送[IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) SDM 正在偵錯程式完成的載入，或當附加至程式完成時的事件物件。 這個事件必須停止事件。  
  
5.  如果要進行偵錯應用程式啟動時，傳送[IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) SDM 時執行的執行階段架構中的程式碼的第一個指令的物件事件。 這個事件永遠是 「 停止 」 事件。 當逐步執行偵錯工作階段，IDE 會停止此事件。  
  
> [!NOTE]
>  許多語言會使用全域初始設定式或外部的先行編譯的函式 （從 CRT 程式庫或 _Main） 在其程式碼的開頭。 如果您正在偵錯的程式語言包含這些類型的初始項目點之前的項目，然後執行此程式碼，並會傳送項目點事件時的使用者進入點，例如**主要**或`WinMain`，已達到。  
  
## <a name="see-also"></a>另請參閱  
 [啟用要偵錯的程式](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)
