---
title: THREADPROPERTY_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- THREADPROPERTY_FIELDS
helpviewer_keywords:
- THREADPROPERTY_FIELDS enumeration
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b181cc341ea0297cc78c0970a5de64df830dc3e6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54937531"
---
# <a name="threadpropertyfields"></a>THREADPROPERTY_FIELDS
指定要擷取執行緒的相關資訊。  
  
## <a name="syntax"></a>語法  
  
```cpp  
enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD THREADPROPERTY_FIELDS;  
```  
  
```csharp  
public enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>成員  
 TPF_ID  
 初始化/使用`dwThreadId`欄位[THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)結構。  
  
 TPF_SUSPENDCOUNT  
 初始化/使用`dwSuspendCount`欄位`THREADPROPERTIE`S 結構。  
  
 TPF_STATE  
 初始化/使用`dwThreadState`欄位`THREADPROPERTIE`S 結構。  
  
 TPF_PRIORITY  
 初始化/使用`bstrPriority`欄位`THREADPROPERTIE`S 結構。  
  
 TPF_NAME  
 初始化/使用`bstrName`欄位`THREADPROPERTIE`S 結構。  
  
 TPF_LOCATION  
 初始化/使用`bstrLocation`欄位`THREADPROPERTIE`S 結構。  
  
 TPF_ALLFIELDS  
 指定所有欄位。  
  
## <a name="remarks"></a>備註  
 這些值會傳遞做為引數[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)方法，以表示哪些欄位[THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)結構會進行初始化。  
  
 這些值也會在`dwFields`隸屬`THREADPROPERTIES`表示哪些欄位已使用且有效的結構。  
  
 這些旗標可能會結合的位元`OR`。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間:Microsoft.VisualStudio.Debugger.Interop  
  
 組件︰Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)