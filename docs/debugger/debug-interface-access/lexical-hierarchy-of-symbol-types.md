---
title: 符號類型的語彙階層架構 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], type hierarchies
ms.assetid: 912da653-ddfe-45a4-84aa-64281283739a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47c32bdeee62216c17c7557d6651e608953b73b3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54928980"
---
# <a name="lexical-hierarchy-of-symbol-types"></a>符號類型的語彙階層架構
下表顯示的符號類型的語彙階層架構中。  
  
## <a name="symbol-types"></a>符號類型  
  
|符號類型|說明|  
|-----------------|-----------------|  
|[註釋](../../debugger/debug-interface-access/annotation.md)|程式碼中指定的註解式的位置。|  
|[區塊](../../debugger/debug-interface-access/block.md)|您可以指定巢狀的範圍中函式。|  
|`Compiland`|指定`compiland`連結至.exe 檔案。|  
|[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)|指定編譯模組可能需要載入其他的編譯模組的詳細資料，並因此會產生執行階段額外負荷，要擷取的資料。|  
|[CompilandEnv](../../debugger/debug-interface-access/compilandenv.md)|指定的編譯模組編譯為任何其他環境變數。|  
|[Custom (偵錯介面存取 SDK)](../../debugger/debug-interface-access/custom-debug-interface-access-sdk.md)|指定使用者定義的符號。|  
|[資料 (偵錯介面存取 SDK)](../../debugger/debug-interface-access/data-debug-interface-access-sdk.md)|指定這類變數做為參數、 區域變數、 全域變數和類別成員。|  
|[Exe](../../debugger/debug-interface-access/exe.md)|指定全域範圍的資料;對應至整個.exe 或.dll 檔案。|  
|[FuncDebugEnd](../../debugger/debug-interface-access/funcdebugend.md)|指定已定義的時間點的函式的偵錯時結束。|  
|[FuncDebugStart](../../debugger/debug-interface-access/funcdebugstart.md)|指定已定義的時間點的函式的偵錯時開始。|  
|[函式 (偵錯介面存取 SDK)](../../debugger/debug-interface-access/function-debug-interface-access-sdk.md)|指定的函式。|  
|[標籤 (偵錯介面存取 SDK)](../../debugger/debug-interface-access/label-debug-interface-access-sdk.md)|程式碼中指定的位置。|  
|[PublicSymbol](../../debugger/debug-interface-access/publicsymbol.md)|指定當建置可執行程式時所顯示的外部符號。|  
|[Thunk](../../debugger/debug-interface-access/thunk.md)|指定`thunk`。|  
|[UsingNameSpace](../../debugger/debug-interface-access/usingnamespace.md)|指定`namespace`識別項。|  
  
> [!NOTE]
>  其他符號屬性可根據符號類型。 在個別的符號主題中列出了這些屬性。  
  
## <a name="see-also"></a>請參閱  
 [符號類型的類別階層](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)   
 [符號和符號標記](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [SymTagEnum 列舉](../../debugger/debug-interface-access/symtagenum.md)