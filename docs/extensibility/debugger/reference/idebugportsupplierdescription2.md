---
title: IDebugPortSupplierDescription2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugPortSupplierDescription2 interface
ms.assetid: dd19b9d6-0703-44b3-9498-cedffa0ce5b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 49ee702c33c322a88c2124b6c6002c5f1fd82d10
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54966003"
---
# <a name="idebugportsupplierdescription2"></a>IDebugPortSupplierDescription2
可讓[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]UI，以顯示內部文字**傳輸資訊**一節**附加至處理序** 對話方塊。  
  
## <a name="syntax"></a>語法  
  
```  
IDebugPortSupplierDescription2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者的附註  
 連接埠提供者會實作這個介面。  
  
## <a name="methods"></a>方法  
 下表顯示的方法`IDebugPortSupplierDescription2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetDescription](../../../extensibility/debugger/reference/idebugportsupplierdescription2-getdescription.md)|擷取連接埠提供者的描述和描述中繼資料。|  
  
## <a name="requirements"></a>需求  
 標頭：Msdbg.h  
  
 命名空間:Microsoft.VisualStudio.Debugger.Interop  
  
 組件︰Microsoft.VisualStudio.Debugger.Interop.dll