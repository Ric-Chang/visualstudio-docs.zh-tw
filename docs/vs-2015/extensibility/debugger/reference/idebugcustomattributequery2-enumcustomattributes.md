---
title: IDebugCustomAttributeQuery2::EnumCustomAttributes |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
helpviewer_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
ms.assetid: 94bfce74-aa3d-45f0-8e04-5715faf85217
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 66ab06ccdf66a0502997551b82f12e9efba95c33
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51772193"
---
# <a name="idebugcustomattributequery2enumcustomattributes"></a>IDebugCustomAttributeQuery2::EnumCustomAttributes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

取得附加至這個欄位的所有自訂屬性的列舉值。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT EnumCustomAttributes(   
   IEnumDebugCustomAttributes** ppEnum  
);  
```  
  
```csharp  
int EnumCustomAttributes(  
   out IEnumDebugCustomAttributes ppEnum  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ppEnum`  
 [out]會傳回[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)物件，表示自訂屬性的清單; 如果沒有自訂屬性，否則會傳回 null 值。  
  
## <a name="return-value"></a>傳回值  
 如果成功，傳回 S_OK 或 S_FALSE，如果此欄位上沒有自訂屬性。 否則，傳回錯誤碼;  
  
## <a name="remarks"></a>備註  
 欄位可以有多個自訂屬性。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)

