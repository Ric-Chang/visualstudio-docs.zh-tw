---
title: IDebugApplicationNode100::SetFilterForEventSink | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100::SetFilterForEventSink
ms.assetid: cfb34efe-c6e1-4692-8ffd-3ede3a24cd4b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4b273b770a1d82edbf5bbbe26c0865060234b852
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346484"
---
# <a name="idebugapplicationnode100setfilterforeventsink"></a>IDebugApplicationNode100::SetFilterForEventSink
特定設定的篩選條件[IDebugApplicationNodeEvents 介面](../../winscript/reference/idebugapplicationnodeevents-interface.md)實作。 它可讓指令碼偵錯工具若要篩選出編譯器產生的子應用程式節點，使 PDM 會不會再傳送事件時，這些是建立或移除。 根據預設，會傳送所有的節點。  
  
> [!IMPORTANT]
>  [IDebugApplicationNode100 介面](../../winscript/reference/idebugapplicationnode100-interface.md)是由 PDM v10.0 實作和更新版本。 可在 activdbg100.h 中找到。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT SetFilterForEventSink(        [in] DWORD dwCookie,        [in] APPLICATION_NODE_EVENT_FILTER filter        );  
```  
  
#### <a name="parameters"></a>參數  
 `dwCookie`  
 篩選條件的 cookie。  
  
 `filter`  
 篩選器。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugApplicationNode100 介面](../../winscript/reference/idebugapplicationnode100-interface.md)