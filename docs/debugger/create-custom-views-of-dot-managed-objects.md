---
title: 建立物件的自訂檢視 |Microsoft Docs
ms.date: 01/08/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types, custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 57480eff4e2ad6e6c33008be6f1bbc2a2f332432
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015091"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>建立自訂檢視的物件 (C#，Visual Basic、 c + +)
您可以自訂 Visual Studio 在偵錯工具變數視窗中顯示資料型別的方式。  

## <a name="native-code"></a>機器碼

針對 c + + 程式碼，您可以新增自訂資料型別擴充，使用 Natvis 架構，如中所述[偵錯工具中建立原生物件的自訂檢視](/visualstudio/debugger/create-custom-views-of-native-objects)。 C + /cli 程式碼，您也可以使用此處所述，在這篇文章中的屬性。

## <a name="attributes"></a>屬性

在C#，Visual Basic 和 c + + (C + + /cli 僅限 CLI 程式碼)，您可以新增自訂資料使用的擴充功能<xref:System.Diagnostics.DebuggerTypeProxyAttribute>， <xref:System.Diagnostics.DebuggerDisplayAttribute>，和<xref:System.Diagnostics.DebuggerBrowsableAttribute>。  
  
在 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 程式碼中，Visual Basic 不支援 DebuggerBrowsable 屬性。 最新版的 .NET Framework 中已移除此限制。    

## <a name="visualizers"></a>視覺化工具

您可以撰寫視覺化檢視以顯示任何 Managed 資料型別。 如需詳細資訊，請參閱[＜How to：撰寫視覺化檢視](/visualstudio/debugger/create-custom-visualizers-of-data)。
  
## <a name="see-also"></a>請參閱  
 [使用 DebuggerTypeProxy 屬性](../debugger/using-debuggertypeproxy-attribute.md)   
 [使用 DebuggerDisplay 屬性](../debugger/using-the-debuggerdisplay-attribute.md)   
 [監看式及快速監看式視窗](../debugger/watch-and-quickwatch-windows.md)   
 [使用偵錯工具顯示屬性增強偵錯功能](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)