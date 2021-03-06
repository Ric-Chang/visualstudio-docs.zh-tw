---
title: 升級 Dotfuscator Community Edition (CE)
ms.date: 02/08/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.topic: conceptual
keywords: Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, 保護, Community Edition, 混淆, .NET, 免費, Visual Studio 2017, 升級, 命令列
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator upgrade
- upgrade Dotfuscator
- upgrading Dotfuscator
- register Dotfuscator
- registering Dotfuscator
- Dotfuscator command line
- Dotfuscator Professional
description: 了解如何升級 Visual Studio 2017 中隨附的免費 Dotfuscator Community Edition。
ms.assetid: c7c60904-27f9-4f1f-b79b-ddf65041b810
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 62a9273ef55a84c26714d2ad2ea1ebb7efe94319
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55034138"
---
# <a name="upgrade-dotfuscator-community-edition-ce"></a>升級 Dotfuscator Community Edition (CE)

Dotfuscator Community Edition (Dotfuscator CE) 為所有使用 Microsoft Visual Studio 的開發人員立即提供許多應用程式保護與強化功能。
不過，使用者在升級其 Dotfuscator 版本之後，會有更多功能可用。

## <a name="registering-dotfuscator-ce"></a>註冊 Dotfuscator CE

Dotfuscator CE 的已註冊使用者可存取額外的功能，例如[命令列支援][cli]，這可讓您輕鬆地將 Dotfuscator CE 整合到自動建置流程。 註冊也會授與對 Lucidator 的存取權，這是用於[解碼模糊化的堆疊追蹤][decode-obfuscated]的內建工具。

註冊不但簡單快速，而且完全免費。
若要註冊 Dotfuscator CE，請參閱[完整《Dotfuscator CE User Guide》(Dotfuscator CE 使用者指南) 之 ＜Getting Started＞(使用者入門) 頁面上的＜Registering Dotfuscator CE＞ (註冊 Dotfuscator CE) 一節][register-ce]。

## <a name="dotfuscator-professional"></a>Dotfuscator Professional

Dotfuscator Community Edition 提供基本層級的保護，而 **_PreEmptive Protection - Dotfuscator_ Professional Edition** 則包含增強的混淆轉換和保護功能。 增強的轉換和功能包括：

* 智慧財產權保護
  * 額外的重新命名選項，包括 Enhanced Overload Induction™ 和隨機化識別碼選取。
  * 用於解碼經過混淆處理之堆疊追蹤的工具。
  * 存取企業級混淆轉換，包括[目標為防止自動程式碼反向組譯的轉換][control-flow]。
  * 能夠[混淆敏感性字串][string-encryption]，以防止執行反向組譯程式碼的簡單搜尋。
  * 能夠[以不顯眼的方式將擁有權和發佈字串嵌入您的組件][watermarking]，讓您判斷未經授權的軟體漏洞來源。
  * 能夠[將多個組件合併成一個組件][linking]，由於消除了關注點分離 (Separation of Concerns) 的問題，因此攻擊者更難判斷程式碼項目的角色。
  * 能夠[自動從您的應用程式移除未使用的程式碼][pruning]，以減少送出的敏感性程式碼數量。
* 應用程式完整性保護
  * 額外的[應用程式防禦行為][check-actions]。
  * 能夠在應用程式生命週期結束期限之前提供一段警告期間。
  * 能夠在生命週期結束警告期間或在期限之後通知應用程式程式碼。

Dotfuscator Professional 是業界標準 [.NET 混淆器][net-obfuscator]，適合需要持續支援、維護和產品更新的企業開發人員。
此外，Dotfuscator Professional 提供與 Visual Studio 的緊密整合，並針對商業用途授權。

如需 Dotfuscator Professional 之進階應用程式保護功能的詳細資訊，請前往 PreEmptive Solutions 的 [Dotfuscator 概觀頁面][product-about]並[與 Community Edition 進行比較][product-compare]。
[您可以在 preemptive.com 取得完整支援的試用版][eval]。

## <a name="see-also"></a>請參閱

[完整 Dotfuscator CE User Guide (Dotfuscator CE 使用者指南) 中的本主題][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[control-flow]:  https://www.preemptive.com/products/dotfuscator/features#controlflow
[string-encryption]:  https://www.preemptive.com/products/dotfuscator/features#string
[watermarking]:  https://www.preemptive.com/products/dotfuscator/features#watermarking
[linking]:  https://www.preemptive.com/products/dotfuscator/features#linking
[pruning]:  https://www.preemptive.com/products/dotfuscator/features#pruning

[check-actions]:  https://www.preemptive.com/dotfuscator/pro/userguide/en/protection_checks_overview.html#actions

[net-obfuscator]:  https://www.preemptive.com/products/dotfuscator/overview
[eval]:  https://www.preemptive.com/eval-request

[product-about]:  https://www.preemptive.com/products/dotfuscator/overview
[product-compare]:  https://www.preemptive.com/products/dotfuscator/compare-editions

[cli]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_cli.html
[register-ce]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html#register

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_upgrades.html
[decode-obfuscated]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_decode_stack_trace.html