---
title: CA1415:P-Invokes 必須正確宣告。
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd948964899c58aa5c0f34b5421cfb370c4dd7eb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54967111"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415:P/Invokes 必須正確宣告

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|分類|Microsoft.Interoperability|
|中斷變更|在組件外，看不到非-中斷-如果 P/Invoke 宣告的參數。 中斷-可以看到組件外部的 P/Invoke 宣告的參數。|

## <a name="cause"></a>原因
 平台叫用方法不正確地宣告。

## <a name="rule-description"></a>規則描述
 平台叫用方法存取 unmanaged 程式碼，並使用定義`Declare`中的關鍵字[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]或<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>。 目前，此規則會尋找平台叫用瞄準具有指向 OVERLAPPED 結構參數的 Win32 函式的方法宣告和對應的 managed 的參數不是指標<xref:System.Threading.NativeOverlapped?displayProperty=fullName>結構。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，正確地宣告平台叫用方法。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。

## <a name="example"></a>範例
 下列範例會顯示平台叫用方法違反此規則並滿足的規則。

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>另請參閱
 [與 Unmanaged 程式碼互通](/dotnet/framework/interop/index)