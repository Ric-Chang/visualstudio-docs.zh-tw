---
title: AsyncTaskMethodBuilder&lt;TResult&gt;結構-內部成員 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- AsyncTaskMethodBuilder<TResult> structure [.NET Framework debug engines]
- debug engines, AsyncTaskMethodBuilder<TResult> structure [.NET Framework]
ms.assetid: 17ebc340-8170-4aff-bf54-dc4548c83632
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6042b574976be6587a918de6b595d0e7b254defb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55014051"
---
# <a name="asynctaskmethodbuilderlttresultgt-structure---internal-members"></a>AsyncTaskMethodBuilder&lt;TResult&gt;結構-內部成員
本主題描述的內部成員<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>類別。 如需此類別的一般資訊，請參閱<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>參考主題。  
  
 **命名空間︰** <xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **組件：** mscorlib （在 mscorlib.dll 中)  
  
 因為您無法從.NET Framework 來存取這些內部成員，下列語法提供通用中繼語言 (CIL)。  
  
## <a name="syntax"></a>語法  
  
```csharp  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<TResult>  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## <a name="internal-members"></a>內部成員  
  
|名稱|描述|  
|----------|-----------------|  
|[ObjectIdForDebugger 屬性](../../extensibility/debugger/asynctaskmethodbuilder-tresult-objectidfordebugger-property.md)|取得物件，可用來唯一識別這個產生器偵錯工具。|  
|[m_task 欄位](../../extensibility/debugger/asynctaskmethodbuilder-tresult-m-task-field.md)|表示延遲初始化建置工作。|  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>   
 [適用於.NET Framework 的平行擴充內部資訊](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)