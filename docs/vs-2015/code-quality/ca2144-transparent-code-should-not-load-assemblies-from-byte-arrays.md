---
title: CA2144： 透明程式碼不可以載入組件從位元組陣列 |Microsoft Docs
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
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 395a21b7926f9b47a001eb3021026e27b3e4eb39
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49922792"
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144：透明程式碼不可以從位元組陣列載入組件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|
|CheckId|CA2144|
|分類|Microsoft.Security|
|中斷變更|中斷|

## <a name="cause"></a>原因
 透明方法會載入組件從位元組陣列，使用下列方法之一：

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

## <a name="rule-description"></a>規則描述
 透明程式碼的安全性檢閱不如關鍵性程式碼的安全性檢閱徹底，因為透明程式碼無法執行安全性敏感動作。 透明程式碼中可能不會注意到從位元組陣列載入的組件，而該位元組陣列可能包含需要稽核之重大或更重要的安全關鍵性程式碼。 因此，transparent 程式碼應該不從位元組陣列載入組件。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，將標記正在載入組件的方法<xref:System.Security.SecurityCriticalAttribute>或<xref:System.Security.SecuritySafeCriticalAttribute>屬性。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。

## <a name="example"></a>範例
 因為透明方法會從位元組陣列載入組件上的下列程式碼會引發此規則。

 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2144.transparentmethodsshouldnotloadassembliesfrombytearrays/cs/ca2144 - transparentmethodsshouldnotloadassembliesfrombytearrays.cs#1)]



