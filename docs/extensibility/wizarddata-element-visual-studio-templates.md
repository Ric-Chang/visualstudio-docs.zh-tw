---
title: WizardData 項目 （Visual Studio 範本） |Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardData
helpviewer_keywords:
- WizardData element [Visual Studio Templates]
- <WizardData> element [Visual Studio Templates]
ms.assetid: d0403a16-5d07-4fe5-b474-19ae3d9fd3ab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c6b61c62e8a3b69963bd56129fd3e7168271fc07
ms.sourcegitcommit: a916ce1eec19d49f060146f7dd5b65f3925158dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2019
ms.locfileid: "55231580"
---
# <a name="wizarddata-element-visual-studio-templates"></a>WizardData 項目 (Visual Studio 範本)

指定自訂 XML

```xml
\<VSTemplate>
\<WizardData>
```

## <a name="syntax"></a>語法

```xml
<WizardData>
    <!-- XML to pass to the custom wizard extension -->
    ...
</WizardData>
```

## <a name="attributes-and-elements"></a>屬性和項目

下列章節將說明屬性、子項目和父項目。

### <a name="attributes"></a>屬性

無。

### <a name="child-elements"></a>子元素

無。

### <a name="parent-elements"></a>父項目

|項目|描述|
|-------------|-----------------|
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|必要項目。<br /><br /> 包含專案範本、 項目範本，或入門套件的所有中繼資料。|

## <a name="text-value"></a>文字值

可選擇使用文字值。

此文字會指定要傳遞給自訂精靈延伸模組中所指定的自訂 XML [WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)項目。

## <a name="remarks"></a>備註

此項目中，可以指定任何的 XML。 XML 將會傳遞做為參數自訂精靈延伸模組，讓此擴充功能使用此項目的內容。 這項資料不進行任何驗證。

內容**WizardData**元素傳遞，則保持不變，做為參數字串字典中的參數內`IWizard.RunStarted`方法。 字典索引鍵名為`$wizarddata$`。

## <a name="example"></a>範例

下列範例說明的標準專案範本的中繼資料C#Windows 應用程式。

```xml
<VSTemplate Version="3.0.0" Type="Item"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyTemplate</Name>
        <Description>Template using IWizard extension</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
    <WizardExtension>
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom=null</Assembly>
        <FullClassName>MyWizard.CustomWizard</FullClassName>
    </WizardExtension>
    <WizardData>
        <!-- XML to pass to the custom wizard extension -->
    </WizardData>
</VSTemplate>
```

## <a name="see-also"></a>另請參閱

- [Visual Studio 範本結構描述參考](../extensibility/visual-studio-template-schema-reference.md)
- [建立專案和項目範本](../ide/creating-project-and-item-templates.md)
- [WizardExtension 元素 (Visual Studio 範本)](../extensibility/wizardextension-element-visual-studio-templates.md)
- [如何：使用精靈與專案範本](../extensibility/how-to-use-wizards-with-project-templates.md)