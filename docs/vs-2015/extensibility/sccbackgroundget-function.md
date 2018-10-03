---
title: SccBackgroundGet 函式 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccBackgroundGet
helpviewer_keywords:
- SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 162bbc427b48ee10ea3a0b88837cf012f1c3fd07
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47485081"
---
# <a name="sccbackgroundget-function"></a>SccBackgroundGet 函式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[SccBackgroundGet 函式](https://docs.microsoft.com/visualstudio/extensibility/sccbackgroundget-function)。  
  
此函式會擷取從原始檔控制每個指定的檔案而不需要使用者互動。  
  
## <a name="syntax"></a>語法  
  
```cpp  
SCCRTN SccBackgroundGet(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LONG    dwFlags,  
   LONG    dwBackgroundOperationID  
);  
```  
  
#### <a name="parameters"></a>參數  
 pContext  
 [in]原始檔控制外掛程式的內容指標。  
  
 nFiles  
 [in]中指定的檔案數目`lpFileNames`陣列。  
  
 lpFileNames  
 [in、 out]要擷取的檔案名稱的陣列。  
  
> [!NOTE]
>  名稱必須是完整的本機檔案名稱。  
  
 dwFlags  
 [in]命令旗標 (`SCC_GET_ALL`， `SCC_GET_RECURSIVE`)。  
  
 dwBackgroundOperationID  
 [in]這項作業相關聯的唯一值。  
  
## <a name="return-value"></a>傳回值  
 此函式的原始檔控制外掛程式實作應該會傳回下列值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|作業已順利完成。|  
|SCC_E_BACKGROUNDGETINPROGRESS|背景擷取已正在的進行 （原始檔控制外掛程式應該傳回這才是它不支援同時批次作業）。|  
|SCC_I_OPERATIONCANCELED|在完成前已取消作業。|  
  
## <a name="remarks"></a>備註  
 不同於載入原始檔控制外掛程式的另一個執行緒上，一律會呼叫此函數。 此函式不應該傳回之前完成;不過，它可以與多個清單的檔案，所有同時呼叫多次。  
  
 善用`dwFlags`引數是相同[SccGet](../extensibility/sccget-function.md)。  
  
## <a name="see-also"></a>另請參閱  
 [原始檔控制外掛程式 API 函式](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGet](../extensibility/sccget-function.md)
