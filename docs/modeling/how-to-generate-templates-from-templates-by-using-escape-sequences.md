---
title: HOW TO：使用逸出序列從範本產生範本
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: b286f3ac432da786a0fbdf5f6c03c2e18075e18e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55020339"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>HOW TO：使用逸出序列從範本產生範本
您可以建立的文字範本會建立另一個文字範本，做為其產生的文字輸出。 若要這樣做，您必須使用逸出序列來描述文字範本標記。 如果您不使用逸出序列，產生的文字範本會有預先定義的意義。 如需文字範本中使用逸出序列的詳細資訊，請參閱[文字範本中使用逸出序列](../modeling/using-escape-sequences-in-text-templates.md)。

### <a name="to-generate-a-text-template-from-within-a-text-template"></a>若要產生的文字範本內從文字範本

-   使用反斜線 (\\) 當做逸出字元，產生的文字範本指示詞、 陳述式、 運算式、 內所需的標記和類別不同的文字範本檔案中的功能。

    ```
    \<#@ directive \#>
    \<# statement \#>
    \<#= expression \#>
    \<#+ classfeature \#>
    ```

## <a name="example"></a>範例
 下列範例會使用逸出字元來產生文字範本，從文字範本。 `output`指示詞將目的地檔案類型設定為文字範本檔案類型 (.tt)。

```csharp
\<#@ output extension=".tt" \#>
\<#@ assembly name="System.Xml.dll" \#>
\<#@ import namespace="System.Xml" \#>
\<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {\#>
           \<#= attr.Name \#>
       \<#}
     }
\#>
```

 產生的文字輸出是文字範本。

```
<#@ output extension=".tt" #>
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>
<#
XmlDocument xDoc = new XmlDocument();
//System.Diagnostics.Debugger.Break();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {#>
           <#= attr.Name #>
       <#}
     }
#>
```