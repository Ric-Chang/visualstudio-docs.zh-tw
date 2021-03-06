---
title: IActiveScriptProfilerCallback::ScriptCompiled |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.ScriptCompiled
apilocation:
- scrobj.dll
ms.assetid: 1bb8e9be-cbb1-4a61-b36c-805127a56ac7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf653e5623506a68e6353e3d9f97077592e87941
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091503"
---
# <a name="iactivescriptprofilercallbackscriptcompiled"></a>IActiveScriptProfilerCallback::ScriptCompiled
通知分析工具物件，指令碼引擎編譯的指令碼。 編譯每個指令碼會呼叫這個方法。  
  
## <a name="syntax"></a>語法  
  
```cpp
HRESULT ScriptCompiled(  
    [in] PROFILER_TOKEN scriptId,  
    [in] PROFILER_SCRIPT_TYPE type,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>參數  
 `scriptId`  
 [in]已編譯的指令碼的唯一識別碼。 此識別碼會指定指令碼引擎。  
  
 `type`  
 [in]已編譯的指令碼型別。 值會定義於[PROFILER_SCRIPT_TYPE 列舉](../../winscript/reference/profiler-script-type-enumeration.md)。  
  
 `pIDebugDocumentContext`  
 [in]如果有的話，指標`IUnknown`分析工具必須查詢的介面[IDebugDocumentContext 介面](../../winscript/reference/idebugdocumentcontext-interface.md)指標。 否則，這會是 null。  
  
## <a name="return-value"></a>傳回值  
 這個方法的傳回值會忽略指令碼引擎。  
  
## <a name="remarks"></a>備註  
 指令碼引擎可以提供的文件內容，只有當主應用程式支援此功能。  
  
## <a name="see-also"></a>另請參閱  
 [IActiveScriptProfilerCallback 介面](../../winscript/reference/iactivescriptprofilercallback-interface.md)