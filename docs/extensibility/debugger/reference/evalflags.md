---
title: EVALFLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 39586e8d6c6417bbfa828b2dc58b63b1cfdc532b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54920465"
---
# <a name="evalflags"></a>EVALFLAGS
指定控制運算式評估的旗標。  
  
## <a name="syntax"></a>語法  
  
```cpp  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```csharp  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>成員  
 EVAL_RETURNVALUE  
 指定的評估傳回的值，如果有的話。  
  
 EVAL_NOSIDEEFFECTS  
 指定不允許副作用。  
  
 EVAL_ALLOWBPS  
 指定中斷點停止。  
  
 EVAL_ALLOWERRORREPORT  
 指定允許主應用程式報告的錯誤。 主要用於在 Internet Explorer 中的指令碼中的運算式評估。  
  
 EVAL_FUNCTION_AS_ADDRESS  
 要評估做為位址，而不是叫用函式的強制函式。  
  
 EVAL_NOFUNCEVAL  
 函式可防止進行評估。 例如，請考慮`int`運算式中的語彙基元`myExpression(int) + 10`。 為位址，但不是能作為值，就可以正確評估此函式。  
  
 EVAL_NOEVENTS  
 旗標，指出工作階段的偵錯管理員 (SDM) 或 ide，不應該傳送之運算式評估期間發生的事件。  
  
## <a name="remarks"></a>備註  
 這些旗標會傳遞做為引數[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)並[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)方法。  
  
 這些旗標可能會與位元 OR 運算結合。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間:Microsoft.VisualStudio.Debugger.Interop  
  
 組件︰Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)