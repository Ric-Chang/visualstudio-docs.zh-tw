---
title: IScriptEntry::GetSignature |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetSignature
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetSignature
ms.assetid: 8cbf37ac-b14c-4e15-a613-06f34857da9b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 245b5806006ad94740e09e23f881e26e071a3bc1
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092725"
---
# <a name="iscriptentrygetsignature"></a>IScriptEntry::GetSignature
傳回的型別資訊`IScriptEntry`函式物件。  
  
## <a name="syntax"></a>語法  
  
```cpp
HRESULT GetSignature(  
   ITypeInfo          **ppti  
   ULONG              *piMethod  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ppti`  
 [out]輸入與此相關的資訊`IScriptEntry`函式物件。  
  
 `piMethod`  
 [out]方法中的索引`ITypeInfo`物件。  
  
## <a name="return-value"></a>傳回值  
 `HRESULT`。 可能的值包括 (但不限於) 下表中的這些值。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>備註  
 使用設定類型資訊[IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md)或是[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)。 根據內部函式表示的項目也可以產生型別資訊。  
  
## <a name="see-also"></a>另請參閱  
 [IScriptEntry 介面](../../winscript/reference/iscriptentry-interface.md)