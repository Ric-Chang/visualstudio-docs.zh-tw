---
title: IDebugProcess3::Continue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::Continue
helpviewer_keywords:
- IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 58cae37bb73a397a7d1b1226c91f68ecb44484c8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54985428"
---
# <a name="idebugprocess3continue"></a>IDebugProcess3::Continue
會繼續執行此程序，從停止的狀態。 會保留任何先前的執行狀態 （例如在步驟），並在處理序啟動重新執行。  
  
> [!NOTE]
>  應該使用這個方法，而不是[繼續](../../../extensibility/debugger/reference/idebugprogram2-continue.md)。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT Continue(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pThread`  
 [in][IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)物件，代表要繼續執行的執行緒。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`，否則會傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 在此程序，不論多少處理序正在進行偵錯，或哪個處理序產生 「 停止 」 事件上呼叫這個方法。 實作必須保留先前的執行狀態 （例如在步驟），並繼續執行，就好像它永遠不會具有停止之前完成其前一次執行。 也就是如果中的執行緒這項程序所執行工作不進入函式的作業和已停止，因為其他處理序已停止，然後`Continue`呼叫，則會指定執行緒必須完成原先不進入函式的作業。  
  
 **警告**不會傳送停止事件或即時 （同步） 事件，以[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)時處理這個呼叫; 否則為偵錯工具可能會停止回應。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)