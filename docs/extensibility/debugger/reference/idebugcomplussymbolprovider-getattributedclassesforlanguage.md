---
title: IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetAttributedClassesForLanguage
- IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
ms.assetid: e5b1b8b6-52a6-4ade-9a36-644abfa9f4b2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0a30bd52cbb7e3d47682045402dc0ac98c9b459c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013765"
---
# <a name="idebugcomplussymbolprovidergetattributedclassesforlanguage"></a>IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
擷取具有指定屬性中指定的程式設計語言實作的類別。  
  
## <a name="syntax"></a>語法  
  
```  
[C++]  
HRESULT GetAttributedClassesForLanguage (  
   GUID               guidLanguage,  
   LPOLESTR           pstrAttribute,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```  
[C#]  
int GetAttributedClassesForLanguage (  
   Guid                 guidLanguage,  
   string               pstrAttribute,  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>參數  
 `guidLanguage`  
 [in]語言的唯一識別碼。  
  
 `pstrAttribute`  
 [in]屬性的字串。  
  
 `ppEnum`  
 [out]傳回屬性類別的列舉。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="example"></a>範例  
 下列範例示範如何實作這個方法，如**CDebugSymbolProvider**公開 （expose） 的物件[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)介面。  
  
```cpp  
HRESULT CDebugSymbolProvider::GetAttributedClassesForLanguage(  
    GUID guidLanguage,  
    __in_z LPOLESTR pstrAttribute,  
    IEnumDebugFields** ppEnum  
)  
{  
    HRESULT hr = S_OK;  
    CFieldList listFields;  
    CModIter ModIter;  
    CModule* pModule; // the iterator owns the reference  
    ULONG cClasses = 0;  
    DWORD iTypeDef = 0;  
    mdTypeDef* rgTypeDefs = NULL;  
    IDebugField** rgFields = NULL;  
    DWORD ctField = 0;  
    CEnumDebugFields* pEnumFields = NULL;  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidWritePtr(ppEnum, IEnumDebugFields*));  
  
    METHOD_ENTRY( CDebugSymbolProvider::GetAttributedClassesForLanguage );  
  
    IfFalseGo( ppEnum, E_INVALIDARG );  
    *ppEnum = NULL;  
  
    // For Each Module - call EnumFields  
    IfFailGo( GetModuleIter(&ModIter) );  
  
    // Find the Max number of classes  
    while (ModIter.GetNext(&pModule))  
    {  
        CComPtr<IMetaDataImport> pMetaData;  
        HCORENUM hEnum = 0;  
        ULONG cTypeDefs;  
        ULONG cEnum;  
  
        pModule->GetMetaData( &pMetaData );  
  
        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,  
                                           NULL,  
                                           0,  
                                           &cTypeDefs ) );  
        IfFailGo( pMetaData->CountEnum( hEnum, &cEnum ) );  
        cClasses += cEnum;  
    }  
  
    IfNullGo( rgTypeDefs = new mdTypeDef[cClasses], E_OUTOFMEMORY );  
    IfNullGo( rgFields = new IDebugField * [cClasses], E_OUTOFMEMORY );  
  
    ModIter.Reset();  
  
    // Create the classes  
    while (ModIter.GetNext(&pModule))  
    {  
        CComPtr<IMetaDataImport> pMetaData;  
        HCORENUM hEnum = 0;  
        ULONG cTypeDefs;  
        ULONG cEnum;  
        const void* pUnused;  
        ULONG cbUnused;  
  
        pModule->GetMetaData( &pMetaData );  
  
        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,  
                                           NULL,  
                                           0,  
                                           &cTypeDefs ) );  
        IfFailGo( pMetaData->CountEnum( hEnum, &cEnum ) );  
        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,  
                                           rgTypeDefs,  
                                           cEnum,  
                                           &cTypeDefs ) );  
  
        pMetaData->CloseEnum(hEnum);  
        hEnum = NULL;  
  
        for ( iTypeDef = 0; iTypeDef < cTypeDefs; iTypeDef++)  
        {  
  
            if (pMetaData->GetCustomAttributeByName( rgTypeDefs[iTypeDef],  
                    pstrAttribute,  
                    &pUnused,  
                    &cbUnused ) == S_OK)  
            {  
                // Only return classes implemeted in the correct language  
  
                if (pModule->ClassImplementedInLanguage( rgTypeDefs[iTypeDef],  
                        guidLanguage) )  
                {  
                    if (CreateClassType( pModule->GetID(),  
                                         rgTypeDefs[iTypeDef],  
                                         rgFields + ctField) == S_OK)  
                    {  
                        ctField++;  
                    }  
                    else  
                    {  
                        ASSERT(!"Failed to Create Attributed Class");  
                    }  
                }  
            }  
        }  
    }  
  
    IfNullGo( pEnumFields = new CEnumDebugFields, E_OUTOFMEMORY );  
    IfFailGo( pEnumFields->Initialize(rgFields, ctField) );  
    IfFailGo( pEnumFields->QueryInterface( __uuidof(IEnumDebugFields),  
                                           (void**) ppEnum ) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::GetAttributedClassesForLanguage, hr );  
  
    DELETERG( rgTypeDefs );  
  
    for ( iTypeDef = 0; iTypeDef < ctField; iTypeDef++)  
    {  
        RELEASE( rgFields[iTypeDef] );  
    }  
  
    DELETERG( rgFields );  
    RELEASE( pEnumFields );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)