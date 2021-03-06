---
title: 在 Vspackage 中的資源 |Microsoft Docs
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
- managed VSPackages, resources in
- resources, managed VSPackages
- VSPackages, managed resources
ms.assetid: cc8c17a6-b190-4856-b001-0c1104f104b2
caps.latest.revision: 24
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f6330055eb3e7b410cc71dc7bab9bc55769c4fd
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51725321"
---
# <a name="resources-in-vspackages"></a>VSPackage 中的資源
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

您可以在 managed VSPackage 本身或原生附屬 UI Dll managed 的附屬 Dll 中內嵌的當地語系化的資源。  
  
 在 Vspackage 中，不可以內嵌一些資源。 下列的 managed 型別可內嵌：  
  
- 字串  
  
- 封裝載入機碼 （這也是字串）  
  
- 工具視窗圖示  
  
- 已編譯的命令資料表輸出 (CTO) 檔案  
  
- CTO 點陣圖  
  
- 命令列說明  
  
- 關於對話方塊資料  
  
  受管理的封裝中的資源選取的資源識別碼。 例外狀況是必須命名為 CTMENU 的 CTO 檔案。 CTO 檔案必須出現在資源資料表作為`byte[]`。 所有其他資源項目是由型別識別。  
  
  您可以使用<xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>屬性來指出要[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]受管理的資源可供使用。  
  
  [!code-csharp[VSSDKResources#1](../../snippets/csharp/VS_Snippets_VSSDK/vssdkresources/cs/vssdkresourcespackage.cs#1)]
  [!code-vb[VSSDKResources#1](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdkresources/vb/vssdkresourcespackage.vb#1)]  
  
  設定<xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>以這種方式表示[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]它會搜尋資源，例如，使用時，應該忽略未受管理的附屬 Dll <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A>。 如果[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]遇到兩個或多個資源具有相同的資源識別碼，它會使用找到的第一個資源。  
  
## <a name="example"></a>範例  
 下列範例是受管理的工具視窗圖示表示。  
  
```  
<data name="1001"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyToolWinIcon.bmp;  
     System.Drawing.Bitmap,  
     System.Drawing,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
 下列範例示範如何內嵌必須命名為 CTMENU CTO 位元組陣列。  
  
```  
<data name="CTMENU"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyPackage.cto;  
     System.Byte[],  
     mscorlib,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
## <a name="implementation-notes"></a>實作注意事項  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 延遲載入的 Vspackage，盡可能。 在 VSPackage 中內嵌的 CTO 檔案的結果[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]必須在安裝期間，會建立合併的命令表時才會載入記憶體中的所有這類 Vspackage。 資源可以擷取從 VSPackage，藉由檢查不在 VSPackage 中執行程式碼的中繼資料。 VSPackage 未初始化在這個階段中，因此是最基本的效能損失。  
  
 當[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]從之後安裝 VSPackage 的資源要求，該套件是可能已經載入和初始化，因此是最基本的效能損失。  
  
## <a name="see-also"></a>另請參閱  
 [Managed 的 Vspackage](../../misc/managed-vspackages.md)   
 [管理 Vspackage](../../extensibility/managing-vspackages.md)   
 [MFC 應用程式中的當地語系化資源： 附屬 Dll](http://msdn.microsoft.com/library/3a1100ae-a9c8-47b5-adbd-cbedef5992ef)   
 [Managed VSPackages](../../misc/managed-vspackages.md)

