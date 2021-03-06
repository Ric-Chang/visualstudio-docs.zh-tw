---
title: IDebugErrorEvent2::GetErrorMessage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 70dc659fa1e3db2d4db797f3be82ba0239368f47
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069430"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
傳回可讓人類看得懂的錯誤訊息建構的資訊。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pMessageType`  
 [out]傳回值，以從[MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)描述的訊息類型的列舉。  
  
 `pbstrErrorFormat`  
 [out]使用者的最後一個訊息的格式 （如需詳細資訊，請參閱 < 備註 >）。  
  
 `hrErrorReason`  
 [out]錯誤碼訊息是關於。  
  
 `pdwType`  
 [out]錯誤的嚴重性 (使用如 MB_XXX 常數`MessageBox`; 例如，`MB_EXCLAMATION`或`MB_WARNING`)。  
  
 `pbstrHelpFileName`  
 [out]說明檔 （設為 null 值，如果沒有說明檔） 的路徑。  
  
 `pdwHelpId`  
 [out][說明] 主題的顯示 （設為 0，如果沒有任何 [說明] 主題） 的識別碼。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 格式化錯誤訊息應該像`"What I was doing.  %1"`。 `"%1"`就會取代呼叫端所衍生自錯誤碼的錯誤訊息 (這會傳入`hrErrorReason`)。 `pMessageType`參數會告訴呼叫端應該顯示的最後一個錯誤訊息的方式。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)