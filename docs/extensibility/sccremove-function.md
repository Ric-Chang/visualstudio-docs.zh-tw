---
title: SccRemove 函式 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccRemove
helpviewer_keywords:
- SccRemove function
ms.assetid: 20830fdc-c0e9-4a5f-bf60-33f28874442f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4db8360f6874f8e2c506aefb153c663670fa5cba
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55014831"
---
# <a name="sccremove-function"></a>SccRemove 函式
此函式會從原始檔控制系統中刪除檔案。  
  
## <a name="syntax"></a>語法  
  
```cpp  
SCCRTN SccRemove(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>參數  
 pvContext  
 [in]原始檔控制外掛程式的內容結構。  
  
 hWnd  
 [in]原始檔控制外掛程式時，可以使用當做父代上，它會提供任何對話方塊 IDE 視窗的控制代碼。  
  
 nFiles  
 [in]中指定的檔案數目`lpFileNames`陣列。  
  
 lpFileNames  
 [in]要移除之檔案的完整格式的本機路徑名稱的陣列。  
  
 lpComment  
 [in]要套用至要移除的每個檔案的註解。  
  
 fOptions  
 [in]命令的旗標 （未使用）。  
  
 pvOptions  
 [in]原始檔控制外掛程式特定選項。  
  
## <a name="return-value"></a>傳回值  
 此函式的原始檔控制外掛程式實作應該會傳回下列值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|已成功移除。|  
|SCC_E_FILENOTCONTROLLED|選取的檔案不在原始檔控制中。|  
|SCC_E_OPNOTSUPPORTED|原始檔控制系統不支援這項作業。|  
|SCC_E_ISCHECKEDOUT|無法移除檔案，因為使用者目前已簽出它。|  
|SCC_E_ACCESSFAILURE|發生問題，存取原始檔控制系統，可能是因為網路或競爭問題。|  
|SCC_E_NOTAUTHORIZED|若要執行這項作業不允許的使用者。|  
|SCC_E_NONSPECIFICERROR|不明確的失敗;檔案不會移除。|  
|SCC_I_OPERATIONCANCELED|作業已完成前取消。|  
  
## <a name="remarks"></a>備註  
 此函式會從原始檔控制系統中移除的檔案，但不會刪除它們從使用者的本機硬碟。  
  
## <a name="see-also"></a>另請參閱  
 [原始檔控制外掛程式 API 函式](../extensibility/source-control-plug-in-api-functions.md)