---
title: IEnumDebugCodeContexts2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugCodeContexts2
helpviewer_keywords:
- IEnumDebugCodeContexts2
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 75765f714bd52d7e7b01eca15e451152ceba54a7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54980579"
---
# <a name="ienumdebugcodecontexts2"></a>IEnumDebugCodeContexts2
此介面列舉與偵錯工作階段中，或特定的程式或文件相關聯的程式碼內容。  
  
## <a name="syntax"></a>語法  
  
```  
IEnumDebugCodeContexts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者的附註  
 偵錯引擎 (DE) 會實作這個介面來代表在程式中，特定的文字位置的程式碼內容的清單或一份特定文件內容的程式碼內容。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 呼叫[EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)來取得這個介面，表示該應用程式的來源文件中的特定文字位置的程式碼內容的清單。  
  
 呼叫[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)來取得這個介面，表示特定的來源文件中的所有程式碼內容的清單。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 下表顯示的方法`IEnumDebugCodeContexts2`。  
  
|方法|描述|  
|------------|-----------------|  
|[下一步](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)|擷取指定的數目的列舉型別序列中的程式碼內容。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-skip.md)|略過指定的數目的列舉型別序列中的程式碼內容。|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-reset.md)|將列舉型別序列重設到開頭。|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-clone.md)|建立列舉值，包含目前的列舉值相同的列舉型別狀態。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-getcount.md)|取得列舉值中的程式碼內容的數目。|  
  
## <a name="remarks"></a>備註  
 Visual Studio 呼叫[EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)來填入清單的程式碼內容的使用者可以選擇從時設定下一個陳述式，或顯示反組譯的原始程式檔。 比方說，多個程式碼內容可以發生的 c + + 樣式範本的多個執行個體時。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間:Microsoft.VisualStudio.Debugger.Interop  
  
 組件︰Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [核心介面](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)