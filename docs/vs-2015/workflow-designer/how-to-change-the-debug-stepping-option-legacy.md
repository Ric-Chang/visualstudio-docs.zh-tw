---
title: 如何： 變更偵錯逐步執行選項 （舊版） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: b89ad55fec7b15884acefd5607cfd863a45564b3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49179230"
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>HOW TO：變更偵錯逐步執行選項 (舊版)
本主題描述如何在具有並行動作的舊版 [!INCLUDE[wf](../includes/wf-md.md)] 中變更 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 應用程式的偵錯逐步執行選項。 當您需要以 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 或 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 為目標時，請使用舊版 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]。  
  
 當您正在偵錯舊版的活動，具有並行執行，例如**ParallelActivity**或是**ConditionedActivityGroup**，您可以使用兩個選項之一來逐步執行程式碼。  
  
 依照下列步驟變更舊版工作流程專案中的偵錯逐步執行選項。  
  
## <a name="procedures"></a>程序  
  
#### <a name="to-change-the-debug-stepping-option"></a>若要變更偵錯逐步執行選項  
  
1.  啟動 Visual Studio。  
  
2.  開啟現有的舊版工作流程專案或建立新的專案，使其利用並行活動並以 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 或 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] 為目標。  
  
3.  在上**工作流程**在舊版的功能表[!INCLUDE[wfd2](../includes/wfd2-md.md)]，指向**偵錯**，然後指向**逐步執行選項**。  
  
4.  選取 **執行個體**或是**分支**。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯舊版工作流程](../workflow-designer/debugging-legacy-workflows.md)   
 [偵錯逐步執行選項 (舊版)](../workflow-designer/debug-stepping-options-legacy.md)