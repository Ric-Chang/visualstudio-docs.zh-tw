---
title: ： 多載運算子 ca2231 覆寫 ValueType.Equals |Microsoft Docs
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
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ebbe414c26d5784f8db96125c4112c01ca82eecb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829752"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231：覆寫 ValueType.Equals 時必須一併多載等號比較運算子
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|分類|Microsoft.Usage|
|中斷變更|非中斷|

## <a name="cause"></a>原因
 實值型別會覆寫<xref:System.Object.Equals%2A?displayProperty=fullName>但不會實作等號比較運算子。

## <a name="rule-description"></a>規則描述
 在大部分的程式設計語言不會有預設實作實值型別中使用等號比較運算子 （= =）。 如果您的程式語言支援運算子多載，您應該考慮實作等號比較運算子。 其行為應該與相同<xref:System.Object.Equals%2A>。

 您無法使用預設等號比較運算子多載等號比較運算子的實作中。 這樣會導致堆疊溢位。 若要實作等號比較運算子，請在您的實作中使用 Object.Equals 方法。 例如: 

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，實作等號比較運算子。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 安全地隱藏的警告，這項規則;不過，我們建議您盡可能提供等號比較運算子。

## <a name="example"></a>範例
 下列範例會定義違反此規則的型別。

 [!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.EqualsGetHashCode/cs/FxCop.Usage.EqualsGetHashCode.cs#1)]

## <a name="related-rules"></a>相關的規則
 [CA1046：請勿多載參考類型上的等號比較運算子](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225：運算子多載必須有具名的替代方法](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226：運算子應該有對稱的多載](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224：多載等號比較運算子時必須一併覆寫 Equals](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218：覆寫 Equals 時必須一併覆寫 GetHashCode](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>另請參閱
 <xref:System.Object.Equals%2A?displayProperty=fullName>



