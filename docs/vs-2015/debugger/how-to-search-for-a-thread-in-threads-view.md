---
title: 如何： 搜尋執行緒 檢視中的往來文章 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- threads, searching
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb1c3979b0505305fd4f6a600e3352c0d08955de
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51766908"
---
# <a name="how-to-search-for-a-thread-in-threads-view"></a>如何：在執行緒檢視中搜尋執行緒
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

您可以使用它的執行緒識別碼或模組字串做為搜尋準則來搜尋特定執行緒在執行緒檢視中。 您也可以指定搜尋的初始方向。 在對話方塊中的欄位會顯示所選取執行緒的屬性，在執行緒樹狀目錄中。  
  
### <a name="to-search-for-a-thread-in-threads-view"></a>若要搜尋 [執行緒] 檢視中的執行緒  
  
1. 因此排列的視窗，Spy + + 和作用[執行緒檢視](../debugger/threads-view.md)視窗會顯示。  
  
2. 從**搜尋**功能表上，選擇**尋找執行緒**。  
  
    [執行緒搜尋對話方塊](../debugger/thread-search-dialog-box.md)隨即開啟。  
  
3. 輸入執行緒 ID 或模組字串做為搜尋準則。  
  
4. 清除，您不想指定值的任何欄位。  
  
   > [!TIP]
   >  若要尋找模組所擁有的所有執行緒，請清除**執行緒**文字方塊並輸入模組中的名稱**模組** 方塊中。 然後使用**尋找下一個**繼續搜尋執行緒。  
  
5. 選擇**向上**或是**向下**初始搜尋的方向。  
  
6. 按一下 [確定 **Deploying Office Solutions**]。  
  
   如果找到相符的執行緒，則它會反白顯示 [執行緒] 檢視視窗中。



