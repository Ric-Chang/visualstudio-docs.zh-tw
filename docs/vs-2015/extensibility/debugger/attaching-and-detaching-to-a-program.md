---
title: 附加和中斷連結至程式 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3b6bba6600d3ea32073a908199f5cd6ddaa33ef9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51762803"
---
# <a name="attaching-and-detaching-to-a-program"></a>附加至程式及中斷連結程式
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

附加偵錯工具需要傳送正確的順序，方法和事件，使用適當的屬性。  
  
## <a name="sequence-of-methods-and-events"></a>序列的方法和事件  
  
1. 工作階段的偵錯管理員 (SDM) 會呼叫[OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)方法。  
  
    根據偵錯引擎 (DE) 處理序模型，`IDebugProgramNodeAttach2::OnAttach`方法會傳回其中一種下列方法，用來決定接下來的情況。  
  
    如果`S_FALSE`會傳回成功的程式連結的偵錯引擎。 否則，請[附加](../../extensibility/debugger/reference/idebugengine2-attach.md)完成附加程序會呼叫方法。  
  
    如果`S_OK`傳回，預設會在 SDM 相同的程序中載入。 在 SDM 會執行下列工作：  
  
   1.  呼叫[GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)取得 DE 的引擎資訊。  
  
   2.  共同建立 DE。  
  
   3.  呼叫[附加](../../extensibility/debugger/reference/idebugengine2-attach.md)。  
  
2. DE 傳送[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)來使用 SDM`EVENT_SYNC`屬性。  
  
3. DE 傳送[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)來使用 SDM`EVENT_SYNC`屬性。  
  
4. DE 傳送[IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)來使用 SDM`EVENT_SYNC_STOP`屬性。  
  
   從程式中斷連結的簡單、 雙步驟程序，如下所示：  
  
5. SDM 呼叫[卸離](../../extensibility/debugger/reference/idebugprogram2-detach.md)。  
  
6. DE 傳送[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)。  
  
## <a name="see-also"></a>另請參閱  
 [呼叫偵錯工具事件](../../extensibility/debugger/calling-debugger-events.md)

