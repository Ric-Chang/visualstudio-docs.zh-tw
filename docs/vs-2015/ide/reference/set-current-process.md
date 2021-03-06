---
title: 設定目前處理序 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: be451ee1a0b4361e44c8be96713872ca0ee3bd76
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2019
ms.locfileid: "54768844"
---
# <a name="set-current-process"></a>設定目前處理序
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
將指定的處理序設為偵錯工具中的使用中處理序。  
  
## <a name="syntax"></a>語法  
  
```  
Debug.SetCurrentProcess index  
```  
  
## <a name="arguments"></a>引數  
 `index`  
 必要項。 處理序的索引。  
  
## <a name="remarks"></a>備註  
 進行偵錯時，您可以附加至多個處理序，但是無論在任何時間，偵錯工具一次只能有一個使用中處理序。 您可以使用 `SetCurrentProcess` 命令設定使用中處理序。  
  
## <a name="example"></a>範例  
  
```  
>Debug.SetCurrentProcess 1  
```  
  
## <a name="see-also"></a>請參閱  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [命令視窗](../../ide/reference/command-window.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
