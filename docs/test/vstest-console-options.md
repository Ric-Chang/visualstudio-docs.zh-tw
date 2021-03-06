---
title: VSTest.Console.exe 命令列選項
ms.date: 07/12/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- vstest.console.exe
- command-line tests
ms.author: gewarren
author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4bd901ad2a57570a11f7a4a9995c30b44d476d3c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54924012"
---
# <a name="vstestconsoleexe-command-line-options"></a>VSTest.Console.exe 命令列選項

*VSTest.Console.exe* 是用來執行測試的命令列工具。 您可以依照任何順序在命令列中指定數個選項。 這些選項列在[一般命令列選項](#general-command-line-options)中。

> [!NOTE]
> 基於相容性，Visual Studio 的 MSTest 配接器也可以在舊版模式下運作 (相當於使用 *mstest.exe* 執行測試)。 但在舊版模式下，它無法利用 TestCaseFilter 功能。 已指定 *testsettings* 檔案、*runsettings* 檔案中的 **forcelegacymode** 設定為 **true**，或使用如 **HostType** 等屬性時，配接器可以切換到舊版模式。
>
> 若要在 ARM 架構電腦上執行自動化測試，您必須使用 *VSTest.Console.exe*。

## <a name="general-command-line-options"></a>一般命令列選項

下表列出 *VSTest.Console.exe* 的所有選項，以及選項的簡短描述。 在命令列鍵入 `VSTest.Console/?` 也能看到類似的摘要。

| 選項 | 說明 |
|---|---|
|**[*test file names*]**|從指定的檔案執行測試。 以空格分隔多個測試檔案名稱。<br />範例：`mytestproject.dll`、`mytestproject.dll myothertestproject.exe`|
|**/Settings:[*file name*]**|使用像資料收集器之類的其他設定執行測試。<br />範例：`/Settings:Local.RunSettings`|
|**/Tests:[*test name*]**|執行測試，其名稱包含所提供的值。 若要提供多個值，請使用逗號來區隔。<br />範例：`/Tests:TestMethod1,testMethod2`<br />**/Tests** 命令列選項無法與 **/TestCaseFilter** 命令列選項搭配使用。|
|**/Parallel**|指定以平行方式執行測試。 根據預設，最多可以使用電腦上所有可用的核心。 使用設定檔可設定要使用的核心數目。|
|**/Enablecodecoverage**|在測試回合中啟用資料診斷配接器 CodeCoverage。<br />如果沒有使用設定檔來指定，則使用預設設定。|
|**/InIsolation**|在獨立的處理序中執行測試。<br />這種隔離會降低 *vstest.console.exe* 處理序在測試中錯誤處停止的可能性，但是測試的速度可能會比較慢。|
|**/UseVsixExtensions**|此選項可讓 *vstest.console.exe* 處理序使用或略過測試回合中已安裝的 VSIX 延伸模組 (若有的話)。<br />即將淘汰此選項。 從 Visual Studio 的下一個主要版本開始，就可能會移除這個選項。 移至以 NuGet 套件形式提供的取用延伸模組。<br />範例：`/UseVsixExtensions:true`|
|**/TestAdapterPath:[*path*]**|強制 *vstest.console.exe* 處理序在測試回合中使用來自指定路徑 (若有的話) 的自訂測試配接器。<br />範例：`/TestAdapterPath:[pathToCustomAdapters]`|
|**/Platform:[*platform type*]**|要用於測試執行的目標平台架構。<br />有效值為 x86、x64 和 ARM。|
|**/Framework: [*framework version*]**|要用於測試執行的目標 .NET Framework 版本。<br />有效值為 Framework35、Framework40、Framework45 和 FrameworkUap10。<br />如果目標 Framework 指定為 **Framework35**，則會在 CLR 4.0 的「相容性模式」中執行測試。<br />範例：`/Framework:framework40`|
|**/TestCaseFilter:[*expression*]**|執行符合指定之運算式的測試。<br /><Expression\> 的格式為 <property\>=<value\>[\|<Expression\>]。<br />範例：`/TestCaseFilter:"Priority=1"`<br />範例：`/TestCaseFilter:"TestCategory=Nightly|FullyQualifiedName=Namespace.ClassName.MethodName"`<br />**/TestCaseFilter** 命令列選項無法與 **/Tests** 命令列選項搭配使用。 <br />如需建立和使用運算式的資訊，請參閱 [ 篩選](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)。|
|**/?**|顯示使用方式資訊。|
|**/Logger:[*uri/friendlyname*]**|指定測試結果的記錄器。<br />範例：若要將結果記錄到 Visual Studio 測試結果檔案 (TRX)，請使用 **/Logger:trx**。<br />範例：若要將測試結果發佈到 Team Foundation Server，請使用 TfsPublisher：<br />**/logger:TfsPublisher;**<br />**Collection=<project url\>;**<br />**BuildName=<build name\>;**<br />**TeamProject=<project name\>;**<br />**[;Platform=<Defaults to "Any CPU">]**<br />**[;Flavor=<Defaults to "Debug">]**<br />**[;RunTitle=<title\>]**|
|**/ListTests:[*file name*]**|列出從指定之測試容器探索到的測試。|
|**/ListDiscoverers**|列出已安裝的測試探索程式。|
|**/ListExecutors**|列出已安裝的測試執行程式。|
|**/ListLoggers**|列出已安裝的測試記錄器。|
|**/ListSettingsProviders**|列出已安裝的測試設定提供者。|
|**/Blame**|在執行測試時追蹤測試，如果測試主機處理序損毀，則會以其執行順序發出測試名稱，最多包含損毀時執行的特定測試。 此輸出可讓您更輕鬆地找出有問題的測試，並進一步診斷。 [詳細資訊](https://github.com/Microsoft/vstest-docs/blob/master/docs/extensions/blame-datacollector.md)。|
|**/Diag:[*file name*]**|將診斷追蹤記錄寫入至指定的檔案。|
|**/ResultsDirectory:[*path*]**|如果測試結果目錄不存在，則會在指定的路徑中建立該目錄。<br />範例：`/ResultsDirectory:<pathToResultsDirectory>`|
|**/ParentProcessId:[*parentProcessId*]**|父處理序的處理序識別碼，該父處理序負責啟動目前處理序。|
|**/Port:[*port*]**|通訊端連線和接收事件訊息的連接埠。|
|**/Collect:[*dataCollector friendlyName*]**|測試回合啟用資料收集器。 [詳細資訊](https://aka.ms/vstest-collect)。|

> [!TIP]
> 選項和值不區分大小寫。

## <a name="examples"></a>範例

執行 *VSTest.Console.exe* 的語法如下：

`Vstest.console.exe [TestFileNames] [Options]`

下列命令會針對測試程式庫 **myTestProject.dll** 執行 *VSTest.Console.exe*：

```cmd
vstest.console.exe myTestProject.dll
```

下列命令會搭配多個測試檔案執行 *VSTest.Console.exe*。 以空格分隔測試檔案名稱：

```cmd
Vstest.console.exe myTestFile.dll myOtherTestFile.dll
```

下列命令會搭配數個選項執行 *VSTest.Console.exe*。 它會以隔離的處理序執行 *myTestFile.dll* 檔案中的測試，並使用 *Local.RunSettings* 檔案中指定的設定。 此外，它只會執行標記為 "Priority=1" 的測試，並將結果記錄到 *.trx* 檔案中。

```cmd
vstest.console.exe  myTestFile.dll /Settings:Local.RunSettings /InIsolation /TestCaseFilter:"Priority=1" /Logger:trx
```
