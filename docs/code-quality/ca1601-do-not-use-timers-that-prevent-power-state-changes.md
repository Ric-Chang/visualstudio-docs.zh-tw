---
title: CA1601:不要使用會妨礙電源狀態變更的計時器
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9a75954b4846e24d25e964d9574772469fba32ec
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951803"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601:不要使用會妨礙電源狀態變更的計時器

|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|分類|Microsoft.Mobility|
|中斷變更|中斷|

## <a name="cause"></a>原因
 計時器已設定一個以上的時間，每秒的間隔。

## <a name="rule-description"></a>規則描述
 不會被輪詢頻率超過一次秒或使用計時器的發生頻率比每秒的時間。 更高頻率的週期性活動會使 CPU 始終處於忙碌狀態，並且會干擾用於關閉顯示器和硬碟的省電閒置計時器。

## <a name="how-to-fix-violations"></a>如何修正違規
 設定計時器的間隔，以每秒小於一次發生。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 只有當所引發的計時器每秒超過一次，而且行動力考量可以放心地忽略，則應該隱藏此規則。