---
title: 'Idiainjectedsource:: Get_source |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_source method
ms.assetid: 3c0b5386-321f-4f8f-85cc-e2ee7b4cc3d2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b5582990ff3db2e03dce9dc0c198a907de978d9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971071"
---
# <a name="idiainjectedsourcegetsource"></a>IDiaInjectedSource::get_source
擷取來源的程式碼位元組。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT get_source (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>參數  
 `cbData`  
 [in]表示資料緩衝區的大小的位元組數目。  
  
 `pcbData`  
 [out]傳回表示個位元組的位元組數傳回。 如果`data`已`NULL`，然後`pcbData`可用資料的位元組總數。  
  
 `data[]`  
 [out]要填入來源位元組的緩衝區。  
  
## <a name="return-value"></a>傳回值  
 如果成功，會傳回 `S_OK`。 傳回`S_FALSE`不支援這個屬性，則為。 反之則傳回錯誤碼。  
  
## <a name="see-also"></a>請參閱  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)