---
title: FIELD_KIND_EX | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- FIELD_KIND_EX enumeration
ms.assetid: 922c3208-1e94-485f-b70a-3bc96affeff8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab27dfe2c1f391711b5eeabe73b38a41df38cc46
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54954263"
---
# <a name="fieldkindex"></a>FIELD_KIND_EX
列舉其他類型的欄位， [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)物件可以包含。 這個列舉型別會擴充[FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)列舉型別。  
  
## <a name="syntax"></a>語法  
  
```cpp  
enum enum_FIELD_KIND_EX  
{  
   FIELD_KIND_EX_NONE = 0,  
   FIELD_TYPE_EX_METHODVAR = 0x1,  
   FIELD_TYPE_EX_CLASSVAR = 0x2  
} ;  
typedef DWORD FIELD_KIND_EX;  
```  
  
```csharp  
public enum enum_FIELD_KIND_EX  
{  
   FIELD_KIND_EX_NONE = 0,  
   FIELD_TYPE_EX_METHODVAR = 0x1,  
   FIELD_TYPE_EX_CLASSVAR = 0x2  
};  
```  
  
## <a name="members"></a>成員  
 FIELD_KIND_EX_NONE  
 欄位不包含擴充的型別。  
  
 FIELD_TYPE_EX_METHODVAR  
 欄位包含方法的變數。  
  
 FIELD_TYPE_EX_CLASSVAR  
 欄位包含的類別變數。  
  
## <a name="requirements"></a>需求  
 標頭：Sh.h  
  
 命名空間:Microsoft.VisualStudio.Debugger.Interop  
  
 組件︰Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)