---
title: 適用於.NET Framework 進行平行擴充內部資訊 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 16ce4309cc8951d068b3d048e6bfac9ae863cd89
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47487894"
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>.NET Framework 適用的平行延伸模組內部資訊
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[平行擴充內部資訊適用於.NET Framework](https://docs.microsoft.com/visualstudio/extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework)。  
  
本章節描述內部型別、 方法和欄位的類別可協助您實作自訂的 parallel extensions 到.NET Framework 偵錯工具。  
  
## <a name="in-this-section"></a>本節內容  
 [Task 類別](../../extensibility/debugger/task-class-internal-members.md)  
 描述內部的資料成員的<xref:System.Threading.Tasks.Task?displayProperty=fullName>類別。  
  
 [TaskScheduler 類別](../../extensibility/debugger/taskscheduler-class-internal-members.md)  
 描述內部的資料成員的<xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>類別。  
  
 [ContingentProperties 類別](../../extensibility/debugger/contingentproperties-class-internal-members.md)  
 描述內部的資料成員的`System.Threading.Tasks.ContingentProperties`類別。  
  
 [AsyncTaskMethodBuilder 結構](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)  
 描述的內部成員<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>結構。  
  
 [AsyncTaskMethodBuilder\<TResult > 結構](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 描述的內部成員<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>結構。  
  
 [AsyncVoidMethodBuilder 結構](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 描述的內部成員<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>結構。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Visual Studio 偵錯工具擴充性](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [平行程式設計](http://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d)
