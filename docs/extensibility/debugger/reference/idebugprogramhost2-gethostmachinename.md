---
title: IDebugProgramHost2::GetHostMachineName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramHost2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramHost2::GetHostMachineName
ms.assetid: 4677ffe4-aa9b-4450-a63b-74cd3984d956
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 94fe3b6b1aff0f83905970cc5bda89d54aa783a9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54990507"
---
# <a name="idebugprogramhost2gethostmachinename"></a>IDebugProgramHost2::GetHostMachineName
取得裝載此程式的處理序上執行的電腦名稱。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetHostMachineName(   
   BSTR* pbstrHostMachineName  
);  
```  
  
```csharp  
int GetHostMachineName(   
   out string pbstrHostMachineName  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pbstrHostMachineName`  
 [out]傳回電腦名稱。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)