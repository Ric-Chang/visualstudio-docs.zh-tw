---
title: CvInitProvider 函式 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvInitProvider
helpviewer_keywords:
- CvInitProvider method
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2fed378aad3a988daa532bb22c0dfd6cb3cbfd2f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923222"
---
# <a name="cvinitprovider-function"></a>CvInitProvider 函式
初始化標記提供者。 必須在任何其他並行視覺化檢視 SDK 函式之前呼叫。  
  
## <a name="syntax"></a>語法  
  
```C  
HRESULT CvInitProvider(  
   _In_ const GUID* pGuid,  
   _Out_ PCV_PROVIDER* ppProvider  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pGuid`  
 提供者的 GUID。 不可以是 NULL。  
  
 `ppProvider`  
 將儲存提供者內容的輸出變數位址。 不可以是 NULL。  
  
## <a name="return-value"></a>傳回值  
 成功初始化提供者時傳回 S_OK，發生任何錯誤時則傳回錯誤碼。 您可以使用 SUCCEEDED/FAILED 巨集檢查是否有錯誤狀況。  
  
## <a name="requirements"></a>需求  
 **標頭︰** *cvmarkers.h*  
  
## <a name="see-also"></a>另請參閱  
 [C++ 程式庫參考](../profiling/cpp-library-reference.md)