---
title: CA2143:透明方法不可以使用安全性要求
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 08a7c4d6d7c71954869311b402eed65492391432
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043073"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143:透明方法不可以使用安全性要求

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|分類|Microsoft.Security|
|中斷變更|中斷|

## <a name="cause"></a>原因
 透明類型或方法以宣告方式標記著<xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>`.Demand`需求或方法呼叫<xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>方法。

## <a name="rule-description"></a>規則描述
 安全性透明程式碼不應負責驗證作業的安全性，因此不應要求權限。 安全性透明程式碼應使用完整的要求做出安全性決策，而且安全關鍵程式碼不應依賴透明程式碼提出完全要求。 會執行安全性檢查，例如安全性需求的任何程式碼應改為安全關鍵。

## <a name="how-to-fix-violations"></a>如何修正違規
 一般情況下，若要修正此規則的違規情形，將方法標示與<xref:System.Security.SecuritySafeCriticalAttribute>屬性。 您也可以移除需求。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。

## <a name="example"></a>範例
 在下列程式碼的規則檔案，因為透明方法會讓宣告式安全性需求。

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>另請參閱
 [CA2142:透明程式碼不應該使用 Linkdemand 加以保護](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)