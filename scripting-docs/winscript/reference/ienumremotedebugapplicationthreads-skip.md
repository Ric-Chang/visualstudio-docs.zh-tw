---
title: IEnumRemoteDebugApplicationThreads::Skip |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumRemoteDebugApplicationThreads.Skip
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumRemoteDebugApplicationThreads::Skip
ms.assetid: bb13a18b-bcf8-4542-8b1a-55a4f2769536
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4369eb0cbe8d27938ee1b8ec3e217e3b69c7eb5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093076"
---
# <a name="ienumremotedebugapplicationthreadsskip"></a>IEnumRemoteDebugApplicationThreads::Skip
略過指定的數目的列舉型別序列中的區段。  
  
## <a name="syntax"></a>語法  
  
```cpp
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>參數  
 `celt`  
 [in]略過列舉序列中的區段數目。  
  
## <a name="return-value"></a>傳回值  
 方法會傳回 `HRESULT`。 可能的值包括 (但不限於) 下表中的這些值。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>備註  
 這個方法會略過指定的數目的列舉型別序列中的區段。  
  
## <a name="see-also"></a>另請參閱  
 [IEnumRemoteDebugApplicationThreads 介面](../../winscript/reference/ienumremotedebugapplicationthreads-interface.md)