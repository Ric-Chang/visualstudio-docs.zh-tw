---
title: HOW TO：逐步執行 WCF 服務 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d82ee388ff6325a92b8e82a385ace727a754ad2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017106"
---
# <a name="how-to-step-into-wcf-services"></a>HOW TO：逐步執行 WCF 服務
在 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 中，您可以逐步執行 WCF 服務。 如果 WCF 服務與用戶端都位於相同的 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 方案，您就可以執行到達 WCF 服務內部的中斷點。  
  
 您必須在 app.config 或 Web.config 檔案內啟用偵錯，才能使用逐步執行。 如需如何啟用偵錯並逐步執行 WCF 服務的限制，請參閱 < [WCF 偵錯的限制](../debugger/limitations-on-wcf-debugging.md)。  
  
### <a name="to-step-into-a-wcf-service"></a>若要逐步執行 WCF 服務  
  
1. 建立 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 方案，其中包含 WCF 用戶端和 WCF 服務專案。  
  
2. 在 [方案總管] 中，以滑鼠右鍵按一下 WCF 用戶端專案，然後按一下 [設定為啟始專案]。  
  
3. 在 app.config 或 web.config 檔案內啟用偵錯。 如需詳細資訊，請參閱 < [WCF 偵錯的限制](../debugger/limitations-on-wcf-debugging.md)。  
  
4. 在用戶端專案中要開始逐步執行的位置設定中斷點。 這通常會是在 WCF 服務呼叫之前。  
  
5. 執行至中斷點，然後開始逐步執行。 偵錯工具將自動逐步執行服務。  
  
## <a name="see-also"></a>請參閱  
 [對 WCF 服務進行偵錯](../debugger/debugging-wcf-services.md)   
 [WCF 偵錯的限制](../debugger/limitations-on-wcf-debugging.md)   
 [如何：針對自我裝載的 WCF 服務進行偵錯](../debugger/how-to-debug-a-self-hosted-wcf-service.md)