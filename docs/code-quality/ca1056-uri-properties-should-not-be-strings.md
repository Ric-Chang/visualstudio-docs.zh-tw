---
title: CA1056:URI 屬性不應該為字串
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
helpviewer_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
ms.assetid: fdc99d29-0904-4a65-baa8-4f76833c953e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a237485729a31e555dd47770e295d928ffad5393
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55023102"
---
# <a name="ca1056-uri-properties-should-not-be-strings"></a>CA1056:URI 屬性不應該為字串

|||
|-|-|
|TypeName|UriPropertiesShouldNotBeStrings|
|CheckId|CA1056|
|分類|Microsoft.Design|
|中斷變更|中斷|

## <a name="cause"></a>原因
 類型會宣告其名稱中包含"uri"、"Uri"、"urn"、"Urn"、"url"或"Url"的字串屬性。

## <a name="rule-description"></a>規則描述
 此規則會將屬性名稱分割為 pascal 命名法大小寫慣例為基礎的權杖，並檢查每個語彙基元是否等於"uri"、"Uri"、"urn"、"Urn"、"url"或"Url"。 如果沒有相符項目，此規則會假設屬性代表統一資源識別元 (URI)。 URI 的字串表示方式容易發生剖析和編碼錯誤，並且可能因此產生安全性弱點。 <xref:System.Uri?displayProperty=fullName>類別會提供這些服務安全的方式。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，將屬性變更為<xref:System.Uri>型別。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 它會安全地隱藏此規則的警告，如果屬性不代表 URI。

## <a name="example"></a>範例
 下列範例顯示的型別`ErrorProne`，，違反這項規則和一個型別， `SaferWay`，符合規則。

 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1056-uri-properties-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1056-uri-properties-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1056-uri-properties-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>相關的規則
 [CA1054:URI 參數不應該為字串](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055:URI 會傳回值不應該為字串](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

 [CA2234： 必須必須傳遞 System.Uri 物件而不是字串](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057:字串 URI 多載呼叫 System.Uri 多載](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)