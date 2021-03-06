---
title: POPDIRLISTFUNC |Microsoft Docs
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
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7b1361350b5a0c349ec8bd95a877c4fbaf75eafc
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51802749"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

這是提供給回呼函式[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)函式來更新目錄，以及 （選擇性） 若要了解它們在原始檔控制下的檔案名稱的集合。  
  
 `POPDIRLISTFUNC`應該呼叫回呼，僅適用於這些目錄和檔案名稱 (在清單中指定給`SccPopulateDirList`函式)，實際上是在原始檔控制。  
  
## <a name="signature"></a>簽章  
  
```cpp#  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>參數  
 pvCallerData  
 [in]若要指定的使用者值[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)。  
  
 bFolder  
 [in]`TRUE`如果中的名稱`lpDirectoryOrFileName`是一個目錄中; 否則為名稱是檔名。  
  
 lpDirectoryOrFileName  
 [in]完整的本機路徑是在原始程式碼控制之下的目錄或檔案名稱。  
  
## <a name="return-value"></a>傳回值  
 IDE 會傳回適當的錯誤程式碼：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|繼續處理。|  
|SCC_I_OPERATIONCANCELED|停止處理。|  
|SCC_E_xxx|任何適當的原始檔控制錯誤應該停止處理。|  
  
## <a name="remarks"></a>備註  
 如果`fOptions`的參數`SccPopulateDirList`函式包含`SCC_PDL_INCLUDEFILES`旗標，則檔案名稱，以及目錄名稱，可能會包含清單。  
  
## <a name="see-also"></a>另請參閱  
 [IDE 所實作的回呼函式](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [錯誤碼](../extensibility/error-codes.md)

