---
title: 使用 Automation 模型 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], automation model
ms.assetid: 0c7f7889-fbfb-4b19-804f-b742138baecd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 39c3de415e7c0c8f95380a76de7f8f8a717d97d4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015429"
---
# <a name="using-the-automation-model"></a>使用 Automation 模型
您已經連接 VSPackage 自動化之後，您可以藉由呼叫取得的屬性和方法<xref:EnvDTE.DTEClass.GetObject%2A>方法<xref:EnvDTE._DTE>物件，並傳遞字串，表示您想要擷取的物件。  
  
## <a name="obtaining-project-objects"></a>取得專案物件  
 以下是兩個程式碼範例示範如何自動化取用者會取得專案 automation 物件。 如需有關如何取得 DTE 物件的資訊，請參閱[How to:取得參考至 DTE 和 DTE2 物件](https://msdn.microsoft.com/Library/c92e3c8e-82e6-4a67-85da-e43c50ffd8e4)。  
  
```vb  
Sub DoAutomation()  
    Dim MyProjects As Projects  
    MyProjects = DTE.GetObject("AcmeProject")  
End Sub  
```  
  
```cpp  
void DoAutomation(void)  
{  
  CComQIPtr<Projects> pMyPkg; // Use an IDispatch-derived object type.  
    pMyPkg = pDTE->GetObject("AcmeProjects");   
  
   // The '=' performs a Query Interface.  
   // Assumes pDTE is already available as a global.  
   // Use pMyPkg to access your projects object's properties and methods.  
}  
  
```  
  
 此時，您可以使用標準專案的物件屬於特定 VSPackage 也可以下移階層的模型。  
  
 下列程式碼範例示範如何取得自訂專案類型的屬性的自訂物件。:  
  
```vb  
Dim MyPrj As Project  
Dim MyPrjItem As ProjectItem  
Dim objMyObject as MyExtendedObject  
  
MyPrj = MyProjects.Item(1) 'use the Projects collection to get a project  
objMyObject = MyPrj.Object 'You call .Object to get to special Project  
                           'implementation  
objMyObject.MySpecialMethodOrProperty  
```  
  
 下列程式碼會列出所有的屬性名稱[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]環境**一般**選項**工具**功能表：  
  
```vb  
dim objDTE  
dim objEnv  
set objDTE = CreateObject("VisualStudio.DTE")  
set objEnv = objDTE.Properties("Environment", "General")  
for each obj in ObjEnv  
MsgBox obj.Name  
Next  
  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:EnvDTE.DTEClass.GetObject%2A>