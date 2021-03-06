---
title: ISimpleConnectionPoint 介面 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ISimpleConnectionPoint interface
ms.assetid: f632a82f-942d-4291-963e-e9fa2b162493
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a756fa3f933f4adff56c41a86aee19a0a2a93aa
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346406"
---
# <a name="isimpleconnectionpoint-interface"></a>ISimpleConnectionPoint 介面
提供簡單的方式來描述和列舉的特定連接點上引發的事件。 此介面也可輕易連接`IDispatch`那些事件的物件。 此介面是實作的處理序偵錯管理員 (PDM)，並由指令碼引擎。  
  
 這個介面是可從`IDebugHelper::CreateSimpleConnectionPoint`。  
  
 除了繼承自方法`IUnknown`，則`ISimpleConnectionPoint`介面會公開下列方法。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
  
|方法|描述|  
|------------|-----------------|  
|[ISimpleConnectionPoint::Advise](../../winscript/reference/isimpleconnectionpoint-advise.md)|建立簡單的連接點物件與用戶端接收之間的連線。|  
|[ISimpleConnectionPoint::DescribeEvents](../../winscript/reference/isimpleconnectionpoint-describeevents.md)|在指定範圍的事件中傳回的 DISPID 和每個事件的名稱。|  
|[ISimpleConnectionPoint::GetEventCount](../../winscript/reference/isimpleconnectionpoint-geteventcount.md)|傳回此介面上公開的事件數目。|  
|[ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)|終止透過先前建立的諮詢連接`ISimpleConnectionPoint::Advise`。|  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProperty 介面](../../winscript/reference/idebugproperty-interface.md)