---
title: IDebugApplicationNodeEvents::onDetach |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationNodeEvents.onDetach
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugApplicationNodeEvents::onDetach
ms.assetid: ef0cbe40-8c52-4bc9-bed0-9fc508abec6e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86a19a0c8ff2ce64cf524ae9b5f0ad258409f2df
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094467"
---
# <a name="idebugapplicationnodeeventsondetach"></a>IDebugApplicationNodeEvents::onDetach
處理表示偵錯應用程式節點物件已中斷連結，從父節點的事件。  
  
## <a name="syntax"></a>語法  
  
```cpp
HRESULT onDetach();  
```  
  
#### <a name="parameters"></a>參數  
 這個方法會接受任何參數。  
  
## <a name="return-value"></a>傳回值  
 方法會傳回 `HRESULT`。 可能的值包括 (但不限於) 下表中的這些值。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>備註  
 這個方法會處理表示偵錯應用程式節點物件已中斷連結，從父節點的事件。  
  
 實作器`IDebugApplicationNode`介面會引發這個事件。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugApplicationNodeEvents 介面](../../winscript/reference/idebugapplicationnodeevents-interface.md)   
 [IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)   
 [IDebugApplicationNode 介面](../../winscript/reference/idebugapplicationnode-interface.md)