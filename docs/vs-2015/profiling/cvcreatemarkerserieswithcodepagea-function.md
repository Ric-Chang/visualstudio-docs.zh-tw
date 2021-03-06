---
title: CvCreateMarkerSeriesWithCodePageA 函式 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 635a872372ab775eceb00854a616884f3fc19fef
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2019
ms.locfileid: "54793980"
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>CvCreateMarkerSeriesWithCodePageA 函式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

為特定提供者與指定字碼頁建立標記系列。 此函式可以用來明確指定標記 API ANSI 函式所寫出文字的字碼頁。 如果要擷取追蹤並使用不同的地區設定/語言在不同電腦上進行分析，設定字碼頁會很有用。 預設會使用 GetACP() 函式所傳回的字碼頁。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT CvCreateMarkerSeriesWithCodePageA(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ LPCSTR pSeriesName,  
   _In_ UINT nTextCodePage,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pProvider`  
 CvInitProvider 先前初始化的提供者物件。 不可以是 NULL。  
  
 `pSeriesName`  
 標記系列名稱。 不可以是 NULL，但允許空字串。  
  
 `nTextCodePage`  
 有效的字碼頁。  
  
 `ppMarkerSeries`  
 將儲存標記系列內容的輸出變數位址。 不可以是 NULL。  
  
## <a name="return-value"></a>傳回值  
 成功建立標記系列時傳回 S_OK，發生任何錯誤時則傳回錯誤碼。 您可以使用 SUCCEEDED/FAILED 巨集檢查是否有錯誤狀況。  
  
## <a name="requirements"></a>需求  
 **標頭︰** cvmarkers.h  
  
## <a name="see-also"></a>請參閱  
 [C++ 程式庫參考](../profiling/cpp-library-reference.md)
