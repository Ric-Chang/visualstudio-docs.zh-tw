---
title: IDebugGenericParamField::GetFlags | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetFlags
- IDebugGenericParamField::GetFlags
ms.assetid: adcbbca1-8960-4c88-86b0-8b9467056c97
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2d52dccbc614bf03b26d823ebaf7eb5f69ccf49b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028621"
---
# <a name="idebuggenericparamfieldgetflags"></a>IDebugGenericParamField::GetFlags
擷取此泛型參數的旗標。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetFlags(  
   DWORD* pdwFlags  
);  
```  
  
```csharp  
int GetFlags(  
   ref uint pdwFlags  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pdwFlags`  
 [out]傳回此泛型參數的旗標。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 這些旗標包含各種特殊條件約束的相關資訊。  
  
## <a name="example"></a>範例  
 下列範例示範如何實作這個方法，如**CDebugGenericParamFieldType**公開 （expose） 的物件[IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)介面。  
  
```cpp  
HRESULT CDebugGenericParamFieldType::GetFlags(DWORD *pdwFlags)  
{  
    HRESULT hr = S_OK;  
  
    METHOD_ENTRY( CDebugGenericParamFieldType::GetFlags );  
  
    IfFalseGo( pdwFlags, E_INVALIDARG );  
    IfFailGo( this->LoadProps() );  
    *pdwFlags = m_dwFlags;  
  
Error:  
  
    METHOD_EXIT( CDebugGenericParamFieldType::GetFlags, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)