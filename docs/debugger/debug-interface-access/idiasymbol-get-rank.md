---
title: 'Idiasymbol:: Get_rank |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_rank method
ms.assetid: 14cc9c4b-a5ec-414a-b01f-4a142c17b7cc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3a2f3a9201441abdc9a92fd6ac7f9ddcab385711
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55016898"
---
# <a name="idiasymbolgetrank"></a>IDiaSymbol::get_rank
擷取 FORTRAN 多維陣列的陣序 （維度數目）。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT get_rank (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pRetVal`  
 [out]FORTRAN 多維陣列中傳回維度的數目。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回`S_FALSE`或錯誤碼。  
  
> [!NOTE]
>  傳回值為`S_FALSE`表示此屬性不適用於符號。  
  
## <a name="remarks"></a>備註  
 陣序規範是指的陣列會宣告為陣列中的維度數目`myarray[1,2,3]`。 此範例中有 3 和 3 個維度的順位。 陣序規範不適用於 c + + 會使用每個維度的陣列的陣列的概念 (亦即`myarray[1][2][3]`)。  
  
## <a name="see-also"></a>請參閱  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)