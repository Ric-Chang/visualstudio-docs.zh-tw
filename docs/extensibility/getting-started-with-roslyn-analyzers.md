---
title: 開始使用 Roslyn 分析器 |Microsoft Docs
ms.date: 04/02/2018
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 57573adeceda942b2968bfe07108ff4d54a8435f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54927690"
---
# <a name="get-started-with-roslyn-analyzers"></a>開始使用 Roslyn 分析器

使用 Visual Studio 中的即時、 以專案為基礎的程式碼分析器，API 作者可以送出定義域專屬的程式碼分析，其 NuGet 套件的一部分。 因為這些分析器由.NET 編譯器平台 (代號為"Roslyn")，它們就會產生程式碼中的警告，當您輸入時即使您已完成的一行 （不需等待建置您的程式碼，找出問題）。 分析器可能也會出現有透過立即清除您的程式碼讓您的 Visual Studio 燈泡提示的自動程式碼修正。

## <a name="get-started"></a>開始使用

[Roslyn 即時程式碼分析器簡介和逐步解說](https://msdn.microsoft.com/magazine/dn879356.aspx)

[加入程式碼修正逐步解說：提供使用者修正分析器問題](https://msdn.microsoft.com/magazine/dn904670.aspx)

[簡介和真實世界分析器的逐步解說的討論](https://channel9.msdn.com/events/Build/2015/3-725)

[真實世界的 Roslyn 分析器](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md)，您也可以觀看為[討論](https://channel9.msdn.com/events/Build/2015/3-725)

[在 GitHub 上的數個範例分組為三種類型的分析器](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[簡介與教學課程的幾個分析器的討論](https://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>另請參閱

- [Roslyn 分析器概觀](../code-quality/roslyn-analyzers-overview.md)
- [教學課程：撰寫您的第一個分析器和程式碼修正](/dotnet/csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix)
- [.NET 編譯器平台的套件版本參考](roslyn-version-support.md)
- [GitHub OSS 網站上的多個 docs](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [實作使用 Roslyn 分析器的 FxCop 規則](http://roslynanalyzersstatus.azurewebsites.net/)
