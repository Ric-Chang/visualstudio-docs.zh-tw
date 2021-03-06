---
title: 產生方法
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2c2de6f8608857d102454d03a98aacd175a22cef
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55024938"
---
# <a name="generate-a-method-in-visual-studio"></a>在 Visual Studio 中產生方法

此程式碼產生適用於：

- C#

- Visual Basic

**功能：** 讓您立即將方法新增至類別。

**時機：** 您引進新的方法，並想要自動正確地宣告它。

**原因：** 您可以在使用方法和參數之前先宣告方法和參數；不過，此功能將可自動產生宣告。

## <a name="how-to"></a>操作說明

1. 將游標放在有紅色曲線的行上。 紅色波浪線表示尚不存在的方法。

   - C#: 

       ![醒目提示的程式碼 C#](media/method-highlight-cs.png)

   - Visual Basic：

       ![醒目提示的程式碼 VB](media/method-highlight-vb.png)

2. 接著，執行下列其中一項操作：

   - **鍵盤**
      - 在字行任何地方按 **Ctrl**+**.**， 以觸發 [快速動作與重構] 功能表。
   - **滑鼠**
      - 以滑鼠右鍵按一下並選取 [快速動作與重構] 功能表。
      - 將游標暫留在紅色曲線上，然後按一下顯示的 ![燈泡](media/bulb-cs.png) 圖示。
      - 按一下 ![燈泡](media/bulb-cs.png) 圖示，如果文字游標已經在含有紅色曲線的行上，此圖示就會出現在左邊界上。

      ![「產生方法」預覽](media/method-preview-cs.png)

3. 從下拉功能表選取 [產生方法]。

   > [!TIP]
   > 請使用位於預覽視窗底部的 [預覽變更] 連結，以在進行選取之前先[查看將進行的所有變更](../../ide/preview-changes.md)。

   方法隨即建立，而任何參數會從使用方式推斷。

   - C#: 

       ![產生方法結果 C#](media/method-result-cs.png)

   - Visual Basic：

       ![產生方法結果 VB](media/method-result-vb.png)

## <a name="see-also"></a>另請參閱

- [程式碼產生](../code-generation-in-visual-studio.md)
- [預覽變更](../../ide/preview-changes.md)