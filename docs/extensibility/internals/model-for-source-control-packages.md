---
title: 模型的原始檔控制套件 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], model
ms.assetid: 6164b2d3-a622-4de8-bef3-a6de985e9ebd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3986a90754f073fa28ecce11ff0053ecad512289
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957919"
---
# <a name="model-for-source-control-packages"></a>原始檔控制套件的模型
下列模型代表來源控制項實作的範例。 在模型中，您會看到您必須實作的介面和環境服務，您必須呼叫。 如同所有的服務，您實際上會呼叫您取得透過服務的特定介面的方法。 讓您更輕鬆地查看原始檔控制會論及如何識別類別的名稱。  
  
 ![SCC&#95;TUP 範例](../../extensibility/internals/media/scc_tup.gif "SCC_TUP")  
範例原始檔控制專案  
  
## <a name="interfaces"></a>介面  
 您可以為您新的專案類型，在 Visual Studio 中使用下表所示的介面清單來實作原始檔控制。  
  
|介面|使用|  
|---------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|由專案和編輯器，在儲存或變更 (dirty) 檔案之前呼叫。 此介面可使用<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>服務。|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|呼叫以要求權限，來新增、 移除或重新命名檔案或目錄的專案。 此介面也會呼叫以通知的環境時的已核准的新增、 移除或重新命名動作已完成的專案。 使用存取<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>服務。|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|藉由新增、 重新命名或移除檔案或目錄的專案時收到通知註冊任何實體。 若要註冊事件通知，請呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>。|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|呼叫專案與原始檔控制套件註冊並取得原始檔控制狀態的詳細資訊。 此介面可使用<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>服務。|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|藉由回應檔案的相關資訊的來源控制要求，並取得原始檔控制設定所需的專案檔的專案。|  
  
## <a name="see-also"></a>另請參閱  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 [支援原始檔控制](../../extensibility/internals/supporting-source-control.md)