---
title: CA2133： 委派必須繫結至方法具有一致透明度 |Microsoft Docs
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
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 16e766979e71b36f816e1265ef5da520c16d85b4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49909694"
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133：委派必須繫結至透明度一致的方法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DelegatesMustBindWithConsistentTransparency|
|CheckId|CA2133|
|分類|Microsoft.Security|
|中斷變更|中斷|

> [!NOTE]
>  這個警告只會套用至執行 CoreCLR （CLR 的 Silverlight Web 應用程式特定的版本） 的程式碼中。

## <a name="cause"></a>原因
 這個警告會以標記的委派繫結的方法，就會引發<xref:System.Security.SecurityCriticalAttribute>方法，它是透明或標記著<xref:System.Security.SecuritySafeCriticalAttribute>。 此警告也會引發將透明或安全關鍵性的委派繫結至關鍵方法的方法。

## <a name="rule-description"></a>規則描述
 委派型別和繫結到方法必須有一致的透明度。 透明且安全關鍵性的委派可能只能繫結至其他透明或安全關鍵方法。 同樣地，重要的委派可能只能繫結至關鍵方法。 這些繫結規則確保唯一的程式碼可以叫用方法，以透過委派可能有也叫用的相同方法直接。 比方說，繫結規則防止 transparent 程式碼呼叫 critical 程式碼，直接透過透明的委派。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正這個警告的違規情形，變更其繫結，讓兩個透明度是相等的方法或委派的透明度。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。

### <a name="code"></a>程式碼
 [!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2133.delegatesmustbindwithconsistenttransparency/cs/ca2133 - delegatesmustbindwithconsistenttransparency.cs#1)]



