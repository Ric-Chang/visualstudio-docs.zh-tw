---
title: 關機 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b9b8848399ea88b5f4ce7ebf30f970e2091e6406
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2019
ms.locfileid: "54784595"
---
# <a name="shutdown"></a>關機
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[關機] 選項等候任何目前已分析的處理序結束或中斷連接，然後關閉分析工具，結束分析資料檔案。 [關機] 選項必須是分析執行的最後一道命令。  
  
 如未指定逾時參數，[關機] 選項會無限期等候。 如已指定逾時參數，則此選項會在指定的秒數後傳回，不關閉分析工具或結束資料檔。  
  
 [關機] 選項必須是命令列上指定的唯一選項。  
  
## <a name="syntax"></a>語法  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>參數  
 `Timeout`  
 -   (選擇性) 如已指定，則此選項會在指定的秒數後傳回，不關閉分析工具或結束分析資料檔。  
  
## <a name="see-also"></a>請參閱  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [對獨立應用程式進行程式碼剖析](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [對 ASP.NET Web 應用程式進行程式碼剖析](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [對服務進行程式碼剖析](../profiling/command-line-profiling-of-services.md)
