---
title: 'Iactivescriptprofilerheapenum:: Freeobjectandoptionalinfo 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fdd5f7cc-be4e-4c13-a181-6320d26b44eb
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8dd2b827deba31af1958842cf0dacd2a85f4260d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095689"
---
# <a name="iactivescriptprofilerheapenumfreeobjectandoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 方法
釋放指定[PROFILER_HEAP_OBJECT 結構](../../winscript/reference/profiler-heap-object-structure.md)結構和其相關聯[PROFILER_HEAP_OBJECT_OPTIONAL_INFO 結構](../../winscript/reference/profiler-heap-object-optional-info-structure.md)項目。  
  
## <a name="syntax"></a>語法  
  
```cpp
HRESULT FreeObjectAndOptionalInfo (    [in] ULONG celt,    [in, size_is(celt)] PROFILER_HEAP_OBJECT** heapObjects);  
```  
  
#### <a name="parameters"></a>參數  
 `celt`  
 要釋放的物件數目。  
  
 `heapObjects`  
 陣列[PROFILER_HEAP_OBJECT 結構](../../winscript/reference/profiler-heap-object-structure.md)結構。  
  
## <a name="return-value"></a>傳回值  
 HRESULT。