---
title: ButtonText 元素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 57d6c62add9b48d0119ac411d6aa7d6b96878ba5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028997"
---
# <a name="buttontext-element"></a>ButtonText 元素
此欄位可讓您指定各種功能表所顯示的文字。 根據預設，`ButtonText`元素會出現在功能表控制站。 `ButtonText`項目也會成為預設值，如果其他的文字欄位為空白。 `ButtonText`元素不可為空白，即使指定的其他文字欄位。  
  
## <a name="syntax"></a>語法  
  
```xml  
<ButtonText>My Command</ButtonText>  
```  
  
## <a name="attributes-and-elements"></a>屬性和元素  
 下列章節說明屬性、子元素和父元素。  
  
### <a name="attributes"></a>屬性  
 無。  
  
### <a name="child-elements"></a>子元素  
 無。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[Strings 元素](../extensibility/strings-element.md)|群組文字項目，例如`ButtonText`和`CommandName`。|  
  
## <a name="text-value"></a>文字值  
 文字值`ButtonText`項目提供為功能表項目、 combos 和其他可見文字的使用者介面 (UI) 項目顯示的文字。  
  
## <a name="see-also"></a>另請參閱  
 [Visual Studio 命令表檔案 (.vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)