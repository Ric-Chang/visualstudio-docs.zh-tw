---
title: IDebugApplication110::CallableWaitForHandles |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::CallableWaitForHandles
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31802d8b86f007139959f3ece3bd1a0260599181
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54350020"
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
等候任何一個指定的控制代碼接收信號，同時允許跨執行緒呼叫張貼到此對話。 從偵錯工具的執行緒，就必須呼叫這個方法。  
  
> [!IMPORTANT]
>  [IDebugApplication110 介面](../../winscript/reference/idebugapplication110-interface.md)是實作由 PDM v11.0 和更新版本。 可在 activdbg100.h 中找到。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>參數  
 `handleCount`  
 等候控制代碼數目。  
  
 `pHandles`  
 一組的等候控制代碼。  
  
 `pIndex`  
 HRESULT 值時 s_ok 時，索引`pHandles`接獲訊號的控制代碼。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugApplication110 介面](../../winscript/reference/idebugapplication110-interface.md)