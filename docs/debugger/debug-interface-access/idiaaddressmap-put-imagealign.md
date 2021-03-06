---
title: 'Idiaaddressmap:: Put_imagealign |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0188a0faa4f9fe7a711cbdfd7c006e7e423713fa
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/02/2019
ms.locfileid: "53879727"
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
設定的影像對齊方式。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT put_imageAlign (   
   DWORD NewVal  
);  
```  
  
#### <a name="parameters"></a>參數  
 NewVal  
 [in]新映像對齊值的可執行檔。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 指定的記憶體界限對齊映像 （載入可執行檔）。 目前的系統架構以及編譯和連結的時間選項，可能會影響這種對齊方式。 影像對齊方式一律為位元組界限上。 下列影像的對齊值是有效的：1、 2、 4、 8、 16、 32 和 64 位元組的界限。  
  
 藉由呼叫可擷取目前的影像對齊[idiaaddressmap:: Get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)方法。  
  
> [!NOTE]
>  映像已載入時，可以呼叫這個方法。 `put_imageAlign`映像已經移動或變更和新的對齊是必要時，通常會使用方法。  
  
## <a name="see-also"></a>請參閱  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)