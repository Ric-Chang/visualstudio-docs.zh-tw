---
title: IDebugComPlusSymbolProvider::GetNameFromToken | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugComPlusSymbolProvider::GetNameFromToken
- GetNameFromToken
ms.assetid: 6e8cf468-5fd1-4655-93ed-88828d6068b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3cc1bf67a04fd625bc3e3431a510906072c7d375
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017535"
---
# <a name="idebugcomplussymbolprovidergetnamefromtoken"></a>IDebugComPlusSymbolProvider::GetNameFromToken
傳回與指定的語彙基元指定它的中繼資料物件相關聯的名稱。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetNameFromToken (  
   IUnknown* pMetadataImport,  
   DWORD     dwToken,  
   BSTR*     pbstrName  
);  
```  
  
```csharp  
int GetNameFromToken (  
   object     pMetadataImport,  
   uint       dwToken,  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pMetadataImport`  
 [in]包含中繼資料資訊的物件。  
  
 `dwToken`  
 [in]要命名為語彙基元。  
  
 `pbstrName`  
 [out]對應至權杖的名稱。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="example"></a>範例  
 下列範例示範如何實作這個方法，如**CDebugSymbolProvider**公開 （expose） 的物件[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)介面。  
  
```cpp  
HRESULT CDebugSymbolProvider::GetNameFromToken(  
    IUnknown* pMetadataImport,  
    DWORD dwToken,  
    BSTR* pbstrName  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<IMetaDataImport> pMetaData;  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidInterfacePtr(pMetadataImport, IUnknown));  
  
    METHOD_ENTRY(CDebugSymbolProvider::GetNameFromToken);  
  
    IfFalseGo( pMetadataImport && pbstrName, E_INVALIDARG );  
  
    *pbstrName = NULL;  
    IfFailGo( pMetadataImport->QueryInterface( IID_IMetaDataImport,  
              (void**) &pMetaData ) );  
  
    switch ( TypeFromToken(dwToken) )  
    {  
        case mdtModule:  
            IfFailGo( GetModuleName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtTypeDef:  
            IfFailGo( GetTypeName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtFieldDef:  
            IfFailGo( GetFieldName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtMethodDef:  
            IfFailGo( GetMethodName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtEvent:  
            IfFailGo( GetEventName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtProperty:  
            IfFailGo( GetPropertyName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtAssembly:  
            IfFailGo( GetAssemblyName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        default:  
            ASSERT(!"Unsupported token passed to GetNameFromToken");  
            hr = E_FAIL;  
            break;  
    }  
  
Error:  
  
    METHOD_EXIT(CDebugSymbolProvider::GetNameFromToken, hr);  
    return hr;  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)