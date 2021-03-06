---
title: CA2132： 預設建構函式必須至少和基底型別的預設建構函式一樣關鍵 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f8452ac1c8d75c684a0f8e7a83c8ae3436e5c2b7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49811150"
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132：預設建構函式至少必須和基底類型的預設建構函式一樣關鍵
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|
|CheckId|CA2132|
|分類|Microsoft.Security|
|中斷變更|中斷|

> [!NOTE]
>  這個警告只會套用至執行 CoreCLR （CLR 的 Silverlight Web 應用程式特定的版本） 的程式碼中。

## <a name="cause"></a>原因
 在衍生類別中的預設建構函式的透明度屬性不是重要性不如基底類別的透明度。

## <a name="rule-description"></a>規則描述
 型別和成員具有<xref:System.Security.SecurityCriticalAttribute>不可由 Silverlight 應用程式程式碼。 重視安全性的類型以及成員，只能夠由 .NET Framework for Silverlight 類別庫中的受信任程式碼使用。 由於衍生類別中的公用或受保護建構所具有的透明度必須大於或等於其基底類別，因此應用程式中的類別不可衍生自標記為 SecurityCritical 的類別。

 CoreCLR 平台程式碼，如果基底型別具有公用或保護之不透明的預設建構函式再衍生的型別必須遵守的預設建構函式繼承規則。 衍生的型別也必須擁有預設建構函式，該建構函式必須至少為重要的預設建構函式的基底型別。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此違規情形，請移除類型或不是衍生自安全性不透明的類型。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏這項規則的警告。 違反此規則應用程式程式碼將會導致拒絕載入的型別與 CoreCLR <xref:System.TypeLoadException>。

### <a name="code"></a>程式碼
 [!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2132.defaultconstructorsmusthaveconsistenttransparency/cs/ca2132 - defaultconstructorsmusthaveconsistenttransparency.cs#1)]

### <a name="comments"></a>註解



