---
title: 類別檢視和物件瀏覽器圖示
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- icons, in Object Browser
- signal icons
- Class View tool, symbols
- graphic symbols
- IntelliSense, icons
- icons, IntelliSense
- symbols, Object Browser icons
- Object Browser, icons in Class View
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3791c6b94f4c229efe843b463cb51a64998e5b6f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958247"
---
# <a name="class-view-and-object-browser-icons"></a>類別檢視和物件瀏覽器圖示

[類別檢視] 和 [物件瀏覽器] 會顯示代表程式碼實體 (例如，命名空間、類別、函式和變數) 的圖示。 下表說明並描述圖示。

|圖示|說明|圖示|說明|
|----------|-----------------|----------|-----------------|
|![命名空間符號](../ide/media/vxnamespace_icon.gif)|命名空間|![宣告符號](../ide/media/vxmethod_icon.gif)|方法或函式|
|![類別圖示](../ide/media/vxclass_icon.gif)|類別|![運算子符號](../ide/media/vxoperator_icon.gif)|運算子|
|![棒棒糖介面符號](../ide/media/vxinterface_icon.gif)|介面|![屬性符號](../ide/media/vxproperty_icon.gif)|屬性|
|![結構符號](../ide/media/vxstruct_icon.gif)|結構|![欄位圖示](../ide/media/vxfield_icon.gif)|欄位或變數|
|![等位符號](../ide/media/vxunion_icon.gif)|聯集|![事件符號](../ide/media/vxevent_icon.gif)|Event - 事件|
|![列舉項目符號](../ide/media/vxenum_icon.gif)|列舉|![常數圖示](../ide/media/vxconstant_icon.gif)|常數|
|![類型定義符號](../ide/media/vxtypedef_icon.gif)|Typedef|![列舉項目符號](../ide/media/vxenumitem_icon.gif)|列舉項目|
|![Visual Studio 模組符號](../ide/media/vxmodule_icon.gif)|Module|![對應項目符號](../ide/media/vxmapitem_icon.gif)|對應項目|
|![擴充方法符號](../ide/media/extensionmethod.gif)|擴充方法|![宣告符號](../ide/media/vxmethod_icon.gif)|外部宣告|
|![委派符號](../ide/media/vxdelegate_icon.gif)|Delegate - 委派|![[類別檢視] 和 [物件瀏覽器] 的錯誤圖示](../ide/media/erroricon.gif)|錯誤|
|![例外狀況符號](../ide/media/vxexception_icon.gif)|例外|![範本符號](../ide/media/vxtemplate_icon.gif)|範本|
|![對應符號](../ide/media/vxmap_icon.gif)|對應|![錯誤驚嘆號符號](../ide/media/vxerror_icon.gif)|不明|
|![類型轉送符號](../ide/media/ob_type_forward.gif)|類型轉送|||

## <a name="signal-icons"></a>訊號圖示

下列訊號圖示套用至所有先前的圖示，並指出其存取範圍。

|圖示|說明|
|----------|-----------------|
|\<無訊號圖示>|公用。 可從此元件中的任何位置以及任何參考它的元件存取。|
|![指示 Protected 符號](../ide/media/vxsignal_icon_key.gif)|受保護。 可從包含類別或類型存取，或從衍生自包含類別或類型的包含類別或類型存取。|
|![指示 Private 符號](../ide/media/vxsignal_icon_lock.gif)|私用。 只能在包含類別或類型中存取。|
|![指示 Sealed 符號](../ide/media/vxsignal_icon_envelope.gif)|密封。|
|![指示 Friend&#47;Internal 符號](../ide/media/vxsignal_icon_diamond.gif)|Friend/內部。 只能從專案存取。|
|![指示圖示箭頭](../ide/media/vxsignal_icon_arrow.gif)|捷徑。 物件的捷徑。|

> [!NOTE]
> 如果您的專案包含在原始檔控制資料庫中，則可能會顯示其他訊號圖示以指出原始檔控制狀態 (例如存回或取出)。

## <a name="see-also"></a>另請參閱

- [檢視程式碼的結構](../ide/viewing-the-structure-of-code.md)