---
title: 若為 VB 專案設定偵錯組態 |Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vbProjectPropertiesDebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- debugging [Visual Basic], debugger settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debug configurations, Visual Basic
ms.assetid: 72a8483a-af0b-4403-8b0d-ee9ad71ee435
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e2f8315717b91a257d09b5de671698796f732543
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55004730"
---
# <a name="project-settings-for-a-visual-basic-debug-configuration"></a>Project Settings for a Visual Basic Debug Configuration
您可以在 [屬性頁] 視窗中使用[偵錯和發行組態](../debugger/how-to-set-debug-and-release-configurations.md)中所討論的方法，變更 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 偵錯組態的專案設定。 下表顯示 [屬性頁] 視窗中，偵錯工具相關設定的位置。  
  
> [!WARNING]
>  本主題不適用於 UWP 應用程式。 請參閱[啟動偵錯工作階段 (VB、 C#，c + + 和 XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
### <a name="debug-tab"></a>偵錯索引標籤  
  
| 設定 | 說明 |
|------------------------------| - |
| **組態** | 設定應用程式的編譯模式。 請選擇 [現用 (偵錯)]、[偵錯]、[發行] 或 [所有組態] 其中之一。 |
| **起始動作** | 這個控制項群組會指定當您從 [偵錯] 功能表選擇 [啟動] 時會發生的動作。<br /><br /> -   [起始專案] 是預設動作，並且會啟動用於偵錯的啟始專案。 <br />-   [啟動外部程式] 讓您可以啟動並附加至不屬於 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 專案一部分的程式。 如需詳細資訊，請參閱 <<c0> [ 附加至執行的處理序](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。<br />-   [以 URL 啟動瀏覽器] 可讓您偵錯 Web 應用程式。 |
| **命令列引數** | 指定要偵錯的程式之命令列引數。 命令名稱是在 [啟動外部程式] 指定的程式名稱。 如果將 [啟動動作] 設為 [起始 URL]，便會忽略命令列引數。 |
| **工作目錄** | 指定為程式偵錯時的工作目錄。 在 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 中，工作目錄為啟動應用程式的目錄。 預設工作目錄為 \bin\Debug 或 \bin\Release，視目前組態而定。 |
| **使用遠端電腦** | 選取核取方塊時，即啟用遠端偵錯。 在文字方塊中，您可以鍵入應用程式要在其中進行偵錯的遠端機器名稱，或鍵入 [Msvsmon 伺服器名稱](../debugger/remote-debugging.md)。 遠端機器上的 EXE 位置可在 [建置] 索引標籤的 [輸出路徑] 屬性中指定。其位置必須是遠端電腦上的可共用目錄。 |
| **非受控程式碼偵錯** | 讓您可以從 Managed 應用程式偵錯原生 (Unmanaged) Win32 程式碼的呼叫。 這個動作與在 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 專案中選取 [偵錯工具類型的混合模式] 具有相同效果。 |
| **SQL Server 偵錯** | 允許 SQL Server 資料庫物件偵錯。 |
  
### <a name="compile-tab-press-advanced-compile-options-button"></a>編譯索引標籤：按下進階編譯選項按鈕  
  
| 設定 | 說明 |
|---------------------------| - |
| **啟用最佳化** | 一定要取消勾選這個選項。 最佳化會讓實際執行的程式碼，與 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中所見的原始程式碼不同，導致偵錯更加困難。 如果對程式碼進行最佳化，則使用 Just My Code 進行偵錯時，預設為不載入符號。 |
| **產生偵錯資訊** | 預設已定義在偵錯版本和發行版本中，此設定 (相當於 /debug 編譯器選項) 會在建置期間建立偵錯資訊。 偵錯工具會在偵錯時，使用這份資訊以有用的格式顯示變數名稱和其他資訊。 如果您沒有用這份資訊來編譯程式，偵錯工具的功能便會有所侷限。 如需詳細資訊，請參閱 [/debug](/dotnet/visual-basic/reference/command-line-compiler/debug)。 |
| **定義 DEBUG 常數** | 定義這個符號可以啟用對來自 [Debug 類別](/dotnet/api/system.diagnostics.debug)的輸出函式進行條件式編譯。 完成這個符號定義之後，Debug 類別方法會在[輸出視窗](../ide/reference/output-window.md)產生輸出。 如果沒有這個符號，Debug 類別方法便不會編譯，也不會產生輸出。 這個符號應該會定義在偵錯版本，且不會定義在發行版本中。 在發行版本定義這個符號會建立減慢程式速度的無用程式碼。 |
| **定義 TRACE 常數** | 定義這個符號可以啟用對來自 [Trace 類別](/dotnet/api/system.diagnostics.trace)的輸出函式進行條件式編譯。 完成這個符號定義之後，Trace 類別方法會在[輸出視窗](../ide/reference/output-window.md)產生輸出。 如果沒有這個符號，Trace 類別方法便不會編譯，且不會產生輸出。 根據預設，這個符號已定義於偵錯版本和發行版本中。 |
  
## <a name="see-also"></a>請參閱  
 [偵錯設定和準備](../debugger/debugger-settings-and-preparation.md)