---
title: IActiveScriptDebug 介面 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptDebug interface
ms.assetid: e3e28cba-ee08-4a52-973a-b74be488c348
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0e21f4c99da886bc4907acf8b0934e1b46d57689
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344573"
---
# <a name="iactivescriptdebug-interface"></a>IActiveScriptDebug 介面
指令碼引擎來實作該支援偵錯。 一般而言，該物件會實作`IActiveScriptDebug`介面也會實作`IActiveScript`介面。 如果發生這種情況，呼叫`IActiveScript::QueryInterface`方法，以取得`IActiveScriptDebug`介面。  
  
 `IActiveScriptDebug`介面提供的方法：  
  
- 取得文件管理的智慧主機。  
  
- 同步處理的多個指令碼引擎偵錯的處理序偵錯管理員。  
  
  除了繼承自方法`IUnknown`，則`IActiveScriptDebug`介面會公開下列方法。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)|傳回指令碼文字的任意區塊的文字屬性。|  
|[IActiveScriptDebug::GetScriptletTextAttributes](../../winscript/reference/iactivescriptdebug-getscriptlettextattributes.md)|傳回任意程式碼片段的文字屬性。|  
|[IActiveScriptDebug::EnumCodeContextsOfPosition](../../winscript/reference/iactivescriptdebug-enumcodecontextsofposition.md)|委派給`IDebugDocumentContext::EnumCodeContexts`。|