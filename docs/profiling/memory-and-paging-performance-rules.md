---
title: 記憶體和分頁效能規則 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a71d39f7aaa0dd36d8774af097d2ffddb73561c6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54936472"
---
# <a name="memory-and-paging-performance-rules"></a>記憶體和分頁效能規則
記憶體和分頁分類中的效能規則，會在執行的分析中找出可能影響應用程式效能和回應性的分頁活動。  
  
|||  
|-|-|  
|[DA0014：極高比率的使用中記憶體分頁到磁碟](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|在執行分析的過程中，磁碟使用中的記憶體有極高的比率會發生來回分頁。 此程度的分頁比率通常會影響應用程式效能和回應性。 請考慮修改演算法減少記憶體配置。 您也必須考慮應用程式的記憶體需求。 請在有較多記憶體的電腦上再次嘗試執行分析。 當分頁活動量超過規則 D0017 的上限臨界值時，就會引發此規則。|  
|[DA0017：高比率的使用中記憶體分頁到磁碟](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|在執行分析的過程中，磁碟使用中的記憶體有相當高的比率會發生來回分頁。 此程度的分頁比率通常會影響應用程式效能和回應性。 請考慮修改演算法減少記憶體配置。 您也必須考慮應用程式的記憶體需求。 請在有較多記憶體的電腦上再次嘗試執行分析。|