---
title: 指令指標 (IP) 檢視 - 取樣資料 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: c7f647bb-c5a3-4708-9f9d-33c0fd6e2e96
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b2d4ce3c3a6ba7e49d70b335a85a17a847739962
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758482"
---
# <a name="instruction-pointers-ips-view---sampling-data"></a>指令指標 (IP) 檢視 - 取樣資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

取樣資料的 IP 檢視會針對在程式碼剖析執行期間收集樣本時直接執行的組件指令，列出效能資料。  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 增強式安全性功能需要的重大變更，會以 Visual Studio 分析工具在這些平台收集資料的方式表現。 Windows 市集應用程式也需要新的資料收集技術。 請參閱 [Windows 8 和 Windows Server 2012 應用程式的效能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
  
|資料行|說明|  
|------------|-----------------|  
|**處理序 ID**|分析執行的處理序 ID (PID)。|  
|**處理序名稱**|處理序的名稱。|  
|**模組名稱**|包含該指令的模組名稱。|  
|**模組路徑**|包含該指令的模組路徑。|  
|**原始程式檔**|包含此指令的原始程式檔。|  
|**函式名稱**|包含此指令的函式名稱。|  
|**函式行號**|原始程式檔中這個函式的開頭行號。|  
|**函式位址**|在載入的二進位檔中函式的起始記憶體位址。|  
|**原始程式碼開頭行**|收集這個樣本的原始程式檔中的起始行號。|  
|**原始程式碼結尾行**|收集這個樣本的原始程式檔中的結尾行號。|  
|**原始程式碼開頭字元**|收集這個樣本的原始程式檔行中，起始字元的位移。|  
|**原始程式碼結尾字元**|收集這個樣本的原始程式檔行中，結尾字元的位移。|  
|**指令位址**|載入的二進位檔中指令的位址。|  
|**專有樣本**|當正在執行指令時所收集的總樣本數。|  
|**專有樣本 %**|執行程式碼剖析期間，執行指令時所收集的所有樣本的百分比。|  
  
## <a name="see-also"></a>請參閱  
 [指令指標 (IP) 檢視 - 取樣](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)
