---
title: SccUninitialize 函式 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8dba45116c956c1edc1a8ffb691397375345c661
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54967202"
---
# <a name="sccuninitialize-function"></a>SccUninitialize 函式
此函式會清除任何配置或開啟先前呼叫所建立的連線[SccInitialize](../extensibility/sccinitialize-function.md)準備關閉原始檔控制外掛程式。  
  
## <a name="syntax"></a>語法  
  
```cpp  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>參數  
 pvContext  
 [in]在中建立的原始檔控制外掛程式的內容結構的指標[SccInitialize](../extensibility/sccinitialize-function.md)。  
  
## <a name="return-value"></a>傳回值  
 此函式的原始檔控制外掛程式實作應該會傳回下列值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|清除工作順利完成。|  
  
## <a name="remarks"></a>備註  
 原始檔控制外掛程式負責準備關閉並釋出外掛程式已配置的內容結構的記憶體。 針對每個外掛程式的特定執行個體中，函式會呼叫一次。 呼叫[SccInitialize](../extensibility/sccinitialize-function.md)前面這個呼叫。 沒有專案仍然可以開啟在呼叫時`SccUninitialize`。  
  
## <a name="see-also"></a>另請參閱  
 [原始檔控制外掛程式 API 函式](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)