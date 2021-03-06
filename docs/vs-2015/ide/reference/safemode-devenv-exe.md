---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4c1cd4b15c3ce3462d6d49eca39fedbc64c744c7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767298"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
以安全模式啟動 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，並且只載入預設環境和服務。  
  
## <a name="syntax"></a>語法  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>備註  
 此參數會在啟動 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 時防止載入所有協力廠商 VSPackages，因而確保穩定執行。  
  
## <a name="description"></a>說明  
 下列範例會以安全模式啟動 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。  
  
## <a name="code"></a>程式碼  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>請參閱  
 [Devenv 命令列參數](../../ide/reference/devenv-command-line-switches.md)
