---
title: IDebugField::GetKind |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugField::GetKind
helpviewer_keywords:
- IDebugField::GetKind method
ms.assetid: e7c9c60a-8e55-4ecc-aa63-0c814a1e92cc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e2f78ab95ce7a6fe5897f24da70e6c50e33c8eba
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029162"
---
# <a name="idebugfieldgetkind"></a>IDebugField::GetKind
這個方法會取得欄位的類型。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetKind(   
   FIELD_KIND* pdwKind  
);  
```  
  
```csharp  
int GetKind(  
   out enum_FIELD_KIND pdwKind  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pdwKind`  
 [out]傳回的欄位類型為的組合[FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)常數。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)