---
title: IDebugEngine2::SetLocale | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::SetLocale
helpviewer_keywords:
- IDebugEngine2::SetLocale
ms.assetid: cd0d2cf1-2aac-43da-a830-4bb3d696c219
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e736211dd4256b2a2d85a8b2f23e2474e1e4da30
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54934782"
---
# <a name="idebugengine2setlocale"></a>IDebugEngine2::SetLocale
設定偵錯引擎 (DE) 的地區設定。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT SetLocale(   
   WORD wLangID  
);  
```  
  
```csharp  
int SetLocale(   
   ushort wLangID  
);  
```  
  
#### <a name="parameters"></a>參數  
 `wLangID`  
 [in]指定的語言地區設定。 例如，1033 代表英文。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 此方法稱為工作階段的偵錯管理員 (SDM) 傳播 IDE 的地區設定，以便適當地當地語系化 DE 所傳回的字串。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)