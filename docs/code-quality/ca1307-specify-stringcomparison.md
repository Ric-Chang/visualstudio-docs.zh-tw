---
title: CA1307:必須指定 StringComparison
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e3896056612631bac0c871ea7b09204e2622492
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018276"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307:必須指定 StringComparison

|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|分類|Microsoft.Globalization|
|中斷變更|非重大|

## <a name="cause"></a>原因
 字串比較作業會使用不會設定一個方法多載<xref:System.StringComparison>參數。

## <a name="rule-description"></a>規則描述
 許多字串作業，最重要<xref:System.String.Compare%2A>並<xref:System.String.Equals%2A>方法，提供可接受的多載<xref:System.StringComparison>做為參數的列舉值。

 每當多載存在該採用<xref:System.StringComparison>參數，它應該用來取代不接受此參數的多載。 藉由明確將此參數，通常的程式碼是會較清楚且容易維護。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，請將字串比較方法變更為接受的多載<xref:System.StringComparison>列舉型別做為參數。 例如： 變更`String.Compare(str1, str2)`至`String.Compare(str1, str2, StringComparison.Ordinal)`。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 它可安全地隱藏此規則的警告，當文件庫或應用程式供有限的本機對象，因此不會當地語系化。

## <a name="see-also"></a>另請參閱

- [全球化警告](../code-quality/globalization-warnings.md)
- [CA1309:使用循序的 StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)