---
title: 使用舊版 API，核心編輯器具現化 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - instantiating editor
ms.assetid: dda23b18-96ef-43c6-b0dc-06d15cbe5cbb
caps.latest.revision: 30
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d092994ad66d96a3fe7141cb898c7ef9b811eaf5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765782"
---
# <a name="instantiating-the-core-editor-by-using-the-legacy-api"></a>使用舊版 API，核心編輯器具現化
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

編輯器會負責文字編輯功能，例如插入、 刪除、 複製和貼。 它會結合這些函式所提供的語言服務，例如文字著色、 縮排，並完成 IntelliSense 陳述式。  
  
 您可以具現化核心編輯器，在三種方式之一執行的個體：  
  
- 明確地建立執行個體的核心編輯器視窗中。  
  
- 提供編輯器處理站會傳回核心編輯器的執行個體  
  
- 從專案階層架構中開啟檔案。  
  
  下列各節討論如何使用舊版的 API 來具現化編輯器。  
  
## <a name="explicitly-opening-a-core-editor-instance"></a>明確地開啟核心編輯器執行個體  
 當明確取得核心編輯器的執行個體：  
  
- 取得<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>來保存要編輯的文件資料物件。  
  
- 藉由建立建立文件資料物件導向的線條表示法<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>介面從<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>介面。  
  
- 設定<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>做為文件資料物件的預設實作的執行個體<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>介面，使用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetBuffer%2A>方法。  
  
   主機<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>執行個體中<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>介面使用<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateToolWindow%2A>方法。  
  
  到目前為止，顯示<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>介面會提供視窗，其中包含的核心編輯器執行個體。  
  
  不過，這不是非常有用的執行個體，因為它不會有快速鍵，或存取進階的功能。 若要取得存取快速鍵和進階的功能：  
  
- 使用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A>語言服務和編輯器使用的文件資料物件建立關聯的方法。  
  
- 建立您自己的快速鍵，或使用系統預設值，藉由設定<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>物件顯示的屬性。 若要這樣做，請呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetGuidProperty%2A>方法使用<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>屬性。  
  
   若要取得並使用非標準的快速鍵，產生使用.vsct 檔。 如需詳細資訊，請參閱 [Visual Studio Command Table (.Vsct) Files](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)。  
  
## <a name="how-to-use-an-editor-factory-to-obtain-the-core-editor"></a>如何使用編輯器 factory 取得核心編輯器  
 當實作編輯器處理站使用的核心編輯器<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>方法，遵循所有步驟，明確裝載上一節中所述<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>使用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>文件資料物件，在<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>物件。  
  
 若要顯示的文字，取得<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>從介面<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>物件並呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>方法。  
  
 若要提供語言服務的編輯器中，呼叫<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A>方法內<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>方法。  
  
 若要取得預設快速鍵，不同於上節中，您可以使用命令傳回的內容的<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>方法取得從核心編輯器時<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>方法。  
  
 如果<xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>方法會傳回相同的命令 GUID 做為文字編輯器，核心編輯器的執行個體自動取得預設的快速鍵。  
  
 如需一般資訊，請參閱 <<c0> [ 逐步解說： 建立核心編輯器和註冊編輯器檔案類型](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)。  
  
## <a name="see-also"></a>另請參閱  
 [在核心編輯器](../extensibility/inside-the-core-editor.md)   
 [開啟和儲存專案項目](../extensibility/internals/opening-and-saving-project-items.md)   
 [逐步解說：建立核心編輯器和註冊編輯器檔案類型](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)

