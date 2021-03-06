---
title: IDebugProperty::EnumMembers |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.EnumMembers
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::EnumMembers
ms.assetid: 8ce398a5-6452-4804-ae8f-5c54cd11c661
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7edf2d2f94519146a81cf94b3bf30946af59bbe9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097028"
---
# <a name="idebugpropertyenummembers"></a>IDebugProperty::EnumMembers
列舉屬性的成員。  
  
## <a name="syntax"></a>語法  
  
```cpp
HRESULT EnumMembers (  
   DBGPROP_INFO_FLAGSdwFieldSpec,  
   UINTnRadix,  
   REFIIDrefiid,  
   IEnumDebugPropertyInfo**ppEnum  
);  
```  
  
#### <a name="parameters"></a>參數  
 `dwFieldSpec`  
 [in]指定`DBGPROP_INFO_FLAGS`判斷列舉的偵錯屬性結構中的哪些欄位要填入的常數。  
  
 `nRadix`  
 [in]用於解譯任何數字資訊的基數。  
  
 `refiid`  
 [in]此 IID 為篩選的列舉值傳遞。 IID 是其中一個`IDebugPropertyEnumType`介面繼承自`IDebugPropertyEnumType_All`。  
  
 `ppEnum`  
 [out]傳回`IEnumDebugPropertyInfo`列舉的成員屬性的介面。  
  
## <a name="return-value"></a>傳回值  
 會傳回有效`HRESULT`，通常是`S_OK`。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProperty 介面](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)   
 [IDebugPropertyEnumType_All 介面](../../winscript/reference/idebugpropertyenumtype-all-interface.md)   
 [IEnumDebugPropertyInfo 介面](../../winscript/reference/ienumdebugpropertyinfo-interface.md)