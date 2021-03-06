---
title: 錯誤： 遠端電腦不會顯示在 [遠端連線] 對話方塊 |Microsoft Docs
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
ms.assetid: 5fd98a5b-2cf3-4438-8b0f-6f1a742a62ce
caps.latest.revision: 5
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 929072304e462e08a45a29c84ab9ce1e20043c49
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51739612"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>錯誤：遠端電腦未顯示於 [遠端連線] 對話方塊
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

如果遠端電腦沒有出現在 [遠端連接] 對話方塊中，請檢查下列常見的原因。  
  
 如果您使用 Managed 相容性模式，請參閱 Visual Studio 2010 文件： [疑難排解遠端偵錯 - Visual Studio 2010](https://msdn.microsoft.com/library/2ys11ead\(v=vs.100\).aspx) 。  
  
### <a name="common-causes-for-this-error"></a>這項錯誤的常見原因  
  
-   執行遠端機器的電腦位於不同的子網路中。 若要修正此問題，請在 [限定詞] 對話方塊中手動輸入電腦名稱或 IP 位址  
  
-   遠端電腦上並未執行遠端偵錯工具。 若要修正此問題，請啟動遠端偵錯工具。  
  
-   防火牆封鎖 Visual Studio 和遠端電腦之間的通訊。 若要修正此問題，請設定防火牆允許 Visual Studio 和遠端偵錯工具 (msvsmon) 進行通訊。  
  
-   防毒軟體封鎖 Visual Studio 和遠端電腦之間的通訊。 若要修正此問題，請設定防毒軟體允許 Visual Studio 和遠端偵錯工具 (msvsmon) 進行通訊。  
  
## <a name="see-also"></a>另請參閱  
 [在裝置上設定遠端工具](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



