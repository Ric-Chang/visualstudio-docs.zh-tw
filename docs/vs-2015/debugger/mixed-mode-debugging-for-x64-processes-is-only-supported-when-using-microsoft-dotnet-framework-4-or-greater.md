---
title: 偵錯 x64 處理序，才支援使用 Microsoft.NET Framework 4 或更新版本的混合的模式 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0297d9bcfb380261d2ad2e73853ded70285f1b35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47487864"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>只有使用 Microsoft.NET Framework 4 或更新版本時才支援 x64 處理序的混合模式偵錯
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[偵錯 x64 處理序，才支援使用 Microsoft.NET Framework 4 或更新版本的混合的模式](https://docs.microsoft.com/visualstudio/debugger/mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoft-dotnet-framework-4-or-greater)。  
  
NET Framework 版本早於 4 不提供支援混合模式偵錯 x64 的處理。 這表示在偵錯時，您無法從 Managed 程式碼逐步執行到機器碼，或從機器碼逐步執行到 Managed 程式碼。  
  
### <a name="workarounds"></a>替代解決辦法  
  
-   更新專案，以使用 Microsoft .NET Framework 4 (含) 以後版本。  
  
     -或-  
  
     在不同的偵錯工作階段中分別偵錯 Managed 程式碼和機器碼。  
  
     -或-  
  
     將混合程式碼當做 32 位元處理序來偵錯，如下列程序所述。  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>若要將平台變更為 32 位元 (Visual Basic 或 C#)  
  
1.  在 **方案總管**，以滑鼠右鍵按一下您的專案，然後按一下**屬性**。  
  
2.  在 [屬性頁中，按一下**編譯**或**偵錯**] 索引標籤。  
  
3.  按一下 **平台**然後從平台清單中選取 x86。  
  
     根據預設，Visual Basic 和 C# 編譯器會產生可在任何 CPU 上執行的程式碼。 在 64 位元電腦上，這些二進位檔會當做 64 位元處理序執行。 若要在 32 位元處理程序上執行，您必須選擇**Win32**，而非**AnyCPU**。  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>若要將平台變更為 32 位元 (C/C++)  
  
1.  在 **方案總管**，以滑鼠右鍵按一下您的專案，然後按一下**屬性**。  
  
2.  在 屬性頁中，按一下**平台**然後從平台清單中選取 Win32。  
  
### <a name="to-correct-this-error"></a>更正這個錯誤  
  
-   請參閱[設定 SQL 偵錯](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯 64 位元應用程式](../debugger/debug-64-bit-applications.md)


