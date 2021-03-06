---
title: IDebugMemoryContext2::Compare | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2d2e29cb65fb94ac5e244b7cb0536b6ac7be1901
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54946564"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
比較每個內容中的比較旗標，傳回的第一個符合之內容的索引所指示的方式在給定陣列中的記憶體內容。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT Compare(   
   CONTEXT_COMPARE        compare,  
   IDebugMemoryContext2** rgpMemoryContextSet,  
   DWORD                  dwMemoryContextSetLen,  
   DWORD*                 pdwMemoryContext  
);  
```  
  
```csharp  
int Compare(  
   enum_CONTEXT_COMPARE   compare,   
   IDebugMemoryContext2[] rgpMemoryContextSet,   
   uint                   dwMemoryContextSetLen,   
   out uint               pdwMemoryContext  
);  
```  
  
#### <a name="parameters"></a>參數  
 `compare`  
 [in]值，以從[CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)決定比較類型的列舉型別。  
  
 `rgpMemoryContextSet`  
 [in]若要參考的陣列[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)要比較的物件。  
  
 `dwMemoryContextSetLen`  
 [in]中的內容數目`rgpMemoryContextSet`陣列。  
  
 `pdwMemoryContext`  
 [out]傳回符合比較的第一個記憶體內容的索引。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。 傳回`E_COMPARE_CANNOT_COMPARE`如果無法比較兩個內容。  
  
## <a name="remarks"></a>備註  
 偵錯引擎 (DE) 並沒有支援所有類型的比較，但必須至少都支援`CONTEXT_EQUAL`， `CONTEXT_LESS_THAN`，`CONTEXT_GREATER_THAN`和`CONTEXT_SAME_SCOPE`。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)