---
title: 模組檢視 - .NET 記憶體取樣資料 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Modules view
ms.assetid: 9c05b51a-8382-44cf-a8f7-3fabdd2e8f1b
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: abc5f1f6a15271fa3ec530658add2b6ca3027959
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2019
ms.locfileid: "54804091"
---
# <a name="modules-view---net-memory-sampling-data"></a>模組檢視 - .NET 記憶體取樣資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用取樣方法收集的 .NET 記憶體檢測資料模組檢視，會將記憶體資料依據分析執行中所執行的模組來分類。 每個模組都是階層式樹狀結構的根。 模組的函式列在模組節點之下。  
  
 配置記憶體之陳述式的原始程式檔行號會列在函式節點下，且執行配置之指示的位址會列在行節點下。 程式行資料和指令資料的內含與專屬值一律相同。  
  
|資料行|說明|  
|------------|-----------------|  
|**名稱**|模組、函式、行號或指令位址的名稱。|  
|**處理序 ID**|分析執行的處理序 ID (PID)。|  
|**處理序名稱**|處理序的名稱。|  
|**模組名稱**|包含該函式的模組名稱。|  
|**模組路徑**|模組的路徑。|  
|**原始程式檔**|含有這個函式定義的原始程式檔。|  
|**函式行號**|原始程式檔中這個函式的開頭行號。|  
|**內含配置**|-   對於函式，這是該函式所建立物件的總數。 該數量包含此函式呼叫之函式建立的物件。<br />-   對於模組，則為在分析執行中，當至少執行一個該模組之函式時所配置的物件數量。 該數量包含在該模組函式呼叫的函式中建立的物件。<br />-   對於程式行或指令，這是該程式行或指令配置的物件總數。|  
|**內含配置 %**|分析執行期間，模組、函式、程式行或指令的內含配置佔所有已配置物件的百分比。|  
|**專有配置**|- 若為目前的函式，這是當函式執行函式主體程式碼時 (即函式位於呼叫堆疊的最上方) 所建立的物件數目。 該數量不包含此函式呼叫之函式建立的物件。<br />-   對於模組，這是模組中函式專有配置的總和。<br />-   對於程式行或指令，這是此程式行或指令建立的物件總數。|  
|**專有配置 %**|分析執行期間，模組、函式、程式行或指令的專有配置佔所有已配置物件的百分比。|  
|**內含位元組**|-   對於函式，這是該函式配置的位元組數。 該數量包含配置在由此函式所呼叫函式中的專有位元組。<br />-   對於模組，是在執行分析期間，模組中至少有一個函式正在執行時所配置的位元組數。 該數量包含在該模組函式呼叫的所有函式中建立的物件。<br />-   對於程式行或指令，這是該程式行或指令建立的物件總數。|  
|**內含位元組 %**|分析執行期間，模組、函式、程式行或指令的內含位元組佔所有已配置位元組的百分比。|  
|**專有位元組**|-   對於函式，這是該函式配置的位元組總數。 該數量不包含由此函式呼叫之函式所配置的位元組。<br />-   對於模組，這是該模組中的函式所配置的專有位元組總和。<br />-   對於程式行或指令，這是此程式行或指令配置的物件總數。|  
|**專有位元組 %**|分析執行期間，模組、函式、程式行或指令的專有位元組佔所有已配置位元組的百分比。|  
  
## <a name="see-also"></a>請參閱  
 [如何：自訂報表檢視資料行](../profiling/how-to-customize-report-view-columns.md)   
 [模組檢視 - 檢測](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [模組檢視](../profiling/modules-view-sampling-data.md)   
 [模組檢視](../profiling/modules-view-instrumentation-data.md)
