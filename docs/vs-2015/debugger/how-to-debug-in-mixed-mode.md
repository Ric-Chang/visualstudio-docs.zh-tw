---
title: 如何： 在混合模式偵錯 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6ee85e5822d4792046c755c85d699dd6a9a5d26
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51737166"
---
# <a name="how-to-debug-in-mixed-mode"></a>How to: Debug in Mixed Mode
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

下列程序描述如何同時偵錯 Managed 和原生程式碼，這也稱為混合模式偵錯。 依照 DLL 或應用程式是否以機器碼撰寫而定，會有下列兩種情況：  
  
-   呼叫 DLL 的呼叫應用程式是以機器碼撰寫。 在這個情況中，您的 DLL 是 Managed，而且 Managed 和原生偵錯工具都必須啟用，才能為兩種程式碼偵錯。 您可以檢查這**\<專案 > 屬性頁** 對話方塊。 不同的做法是取決於您是由 DLL 專案啟動偵錯，或者由呼叫應用程式專案啟動偵錯。  
  
-   呼叫 DLL 的呼叫應用程式是以 Managed 程式碼撰寫，而您的 DLL 是以機器碼撰寫。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
### <a name="to-enable-mixed-mode-debugging"></a>若要啟用混合模式偵錯  
  
1.  在 [**方案總管] 中**，選取專案。  
  
2.  在 **檢視**功能表上，按一下**屬性頁**。  
  
3.  在  **\<專案 > 屬性頁**對話方塊方塊中，展開**組態屬性**節點，然後再選取**偵錯**。  
  
4.  設定**偵錯工具類型**要**混合**或是**自動**。  
  
## <a name="see-also"></a>另請參閱  
 [How to: Debug from a DLL Project](../debugger/how-to-debug-from-a-dll-project.md)



