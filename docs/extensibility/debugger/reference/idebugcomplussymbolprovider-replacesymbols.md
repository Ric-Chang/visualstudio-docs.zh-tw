---
title: IDebugComPlusSymbolProvider::ReplaceSymbols | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ReplaceSymbols
- IDebugComPlusSymbolProvider::ReplaceSymbols
ms.assetid: 82fbc8db-c4b1-432f-bec9-1a9dc09570be
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 61370695ad363d6e3eb3a62ac517f34c707eac94
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54963004"
---
# <a name="idebugcomplussymbolproviderreplacesymbols"></a>IDebugComPlusSymbolProvider::ReplaceSymbols
目前的偵錯符號取代指定的資料流中。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT ReplaceSymbols(  
   ULONG32  ulAppDomainID,  
   GUID     guidModule,  
   IStream* pStream  
);  
```  
  
```csharp  
int ReplaceSymbols(  
   uint    ulAppDomainID,  
   Guid    guidModule,  
   IStream pStream  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ulAppDomainID`  
 [in]應用程式定義域的識別項。  
  
 `guidModule`  
 [in]模組的唯一識別碼。  
  
 `pStream`  
 [in]資料流，其中包含新的符號。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="example"></a>範例  
 下列範例示範如何實作這個方法，如**CDebugSymbolProvider**公開 （expose） 的物件[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)介面。  
  
```cpp  
HRESULT CDebugSymbolProvider::ReplaceSymbols(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    IStream* pStream  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::ReplaceSymbols );  
  
    IfFailGo( GetModule( idModule, &pModule ) );  
    IfFailGo( pModule->ReplaceSymbols( pStream ) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::ReplaceSymbols, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)