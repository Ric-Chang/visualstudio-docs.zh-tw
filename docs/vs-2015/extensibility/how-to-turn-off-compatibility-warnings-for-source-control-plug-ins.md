---
title: 如何： 關閉的原始檔控制外掛程式的相容性警告 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
caps.latest.revision: 22
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eacdce1e311ad15e449ddec6e99ffcf9e4d26c8a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51726111"
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>如何： 關閉的原始檔控制外掛程式的相容性警告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用者可能會採用原始檔控制中的看到數個相容性警告[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。 顯示警告取決於原始檔控制外掛程式的功能，並且可以停用，如此處所示詳細。  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>若要停用警告: 「 若要確保最佳的原始檔控制整合，使用 Visual Studio...」  
  
-   設定下列登錄項目 （如有必要，請新增此值）：  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = dword: 00000001  
  
     這個警告會顯示所有非[!INCLUDE[vsvss](../includes/vsvss-md.md)]外掛程式。  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>若要停用警告: 「 已安裝的原始檔控制提供者不支援所有功能...」  
  
-   設定下列兩個登錄值 （如有必要，請加入的值）：  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = dword:00000000  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = dword: 00000001  
  
     如果原始檔控制外掛程式未明確支援重新進入的多個專案 （也就是如果它可以檢查只有一個檔案和專案中，一次），則會顯示此警告。  
  
     建議您最好支援重新進入 (`SCC_CAP_REENTRANT`功能); 這麼做會移除這個警告。 不過，如果這項支援不可行，就可以設定這些登錄項目。  
  
## <a name="see-also"></a>另請參閱  
 [功能旗標](../extensibility/capability-flags.md)

