---
title: CA1711:識別項名稱不應該使用不正確的後置字元
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a612aa39899336eda4802e849529ae61faf192be
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935640"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711:識別項名稱不應該使用不正確的後置字元

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|分類|Microsoft.Naming|
|中斷變更|中斷|

## <a name="cause"></a>原因

識別項具有不正確的後置詞。

## <a name="rule-description"></a>規則描述

依照慣例，只有擴充特定基底類型或實作特定介面或從這些型別，衍生類型的類型名稱應該以特定保留的後置字元為結尾。 其他類型名稱不得使用這些保留的後置字元。

下表列出保留的後置詞的基底類型和與它們相關聯的介面。

|尾碼|基底型別/介面|
|------------|--------------------------|
|屬性|<xref:System.Attribute?displayProperty=fullName>|
|集合|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|字典|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|EventHandler|事件處理常式委派|
|例外|<xref:System.Exception?displayProperty=fullName>|
|權限|<xref:System.Security.IPermission?displayProperty=fullName>|
|Queue|<xref:System.Collections.Queue?displayProperty=fullName>|
|堆疊|<xref:System.Collections.Stack?displayProperty=fullName>|
|資料流|<xref:System.IO.Stream?displayProperty=fullName>|

此外，下列尾碼應該**不**可用：

- `Delegate`

- `Enum`

- `Impl` (使用`Core`改為)

- `Ex` 或類似的後置詞，以區分它與舊版相同的型別

命名慣例提供了通用程式庫 common language runtime 為目標。 這可降低學習曲線，需要新的軟體程式庫，並增加程式庫，開發人員專業開發的 managed 程式碼中的其他人的客戶信心。

## <a name="how-to-fix-violations"></a>如何修正違規

從型別名稱中移除後置詞。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機

除非後置字元在應用程式定義域中具有明確的意義，否則請不要隱藏這項規則的警告。

## <a name="related-rules"></a>相關的規則

- [CA1710:識別項應該使用正確的後置詞](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>另請參閱

- [屬性](/dotnet/standard/design-guidelines/attributes)
- [處理和引發事件](/dotnet/standard/events/index)