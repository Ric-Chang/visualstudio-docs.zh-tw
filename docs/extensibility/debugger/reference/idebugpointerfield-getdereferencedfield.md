---
title: IDebugPointerField::GetDereferencedField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerField::GetDereferencedField
helpviewer_keywords:
- IDebugPointerField::GetDereferencedField method
ms.assetid: 8de988ab-cd79-4287-be72-3c900f2fe407
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 74c3853389f52253b4aa62547c8a0b89a36d03e6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54962715"
---
# <a name="idebugpointerfieldgetdereferencedfield"></a>IDebugPointerField::GetDereferencedField
這個方法會傳回這個指標物件所指向的物件型別。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetDereferencedField(  
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetDereferencedField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ppField`  
 [out]傳回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述的目標物件類型。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 例如，如果[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)物件會指向整數[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)這個方法所傳回的型別描述該整數類型。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)