---
title: 教學課程：開始使用 C# 主控台應用程式
description: 了解如何逐步在 Visual Studio 中建立 C# 主控台應用程式。
ms.custom: seodec18, get-started
ms.date: 01/10/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-dev15
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6114910f8c4cbeebc0301cc0c2167a49742823a5
ms.sourcegitcommit: 59c48e1e42b48ad25a4e198af670faa4d8dae370
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2019
ms.locfileid: "54204427"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>教學課程：Visual Studio 中的 C# 主控台應用程式入門

在 C# 的這個教學課程中，您將使用 Visual Studio 建立並執行主控台應用程式，並在這樣做的同時探索 [Visual Studio 整合式開發環境 (IDE)](../visual-studio-ide.md) 的一些功能。

如果您尚未安裝 Visual Studio，請前往 [Visual Studio 下載](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)頁面免費進行安裝。

## <a name="create-a-project"></a>建立專案

首先，我們將建立 C# 應用程式專案。 在您新增任何項目之前，專案類型會隨附您需要的所有範本檔案！

1. 開啟 Visual Studio 2017。

2. 從頂端功能表列中，選擇 [檔案] > [新增] > [專案]。

3. 在 [新增專案] 對話方塊的左窗格中，展開 [C#]，然後選擇 [.NET Core]。 在中間窗格中，選擇 [主控台應用程式 (.NET Core)]。 接著，將檔案命名為 *Calculator*。

   ![Visual Studio IDE 的 [新增專案] 對話方塊中的主控台應用程式 (.NET Core) 專案範本](./media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>新增工作群組 (選擇性)

如果您看不到 [主控台應用程式] 專案範本，則其取得方式是新增 [.NET Core 跨平台開發] 工作負載。 若要了解如何執行這項操作，請參閱常見問題集中的「[什麼是工作負載？如何新增？](#workload)」 一節。

## <a name="create-the-app"></a>建立應用程式

首先，我們將新增程式碼來建立基本的計算機。 接下來，我們會調校程式碼以新增功能。 然後，我們會對應用程式進行偵錯以找出錯誤，將其修正。 最後，我們會精簡程式碼，讓其更有效率。

現在我們先將基本計算機程式碼新增至您的專案。

1. 在程式碼編輯器中，刪除預設 "Hello World" 程式碼。

    ![從新的計算機應用程式中刪除預設 Hello World 程式碼](./media/csharp-console-calculator-deletehelloworld.png)

   具體來說，刪除您在程式碼編輯器中看到的所有程式碼。

1. 在程式碼編輯器中輸入或貼上下列新程式碼：

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then initialize to zero
                int num1 = 0; int num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to choose an option
                Console.WriteLine("Choose an option from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                // Use a switch statement to do the math
                switch (Console.ReadLine())
                {
                    case "a":
                        Console.WriteLine($"Your result: {num1} + {num2} = " + (num1 + num2));
                        break;
                    case "s":
                        Console.WriteLine($"Your result: {num1} - {num2} = " + (num1 - num2));
                        break;
                    case "m":
                        Console.WriteLine($"Your result: {num1} * {num2} = " + (num1 * num2));
                        break;
                    case "d":
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```
1. 選擇 [Calculator] 來執行您的程式 (或按 **F5**)。

   ![選擇 [Calculator] 按鈕以從工具列執行應用程式](./media/csharp-console-calculator-button.png)

   主控台視窗隨即開啟。

1. 在主控台視窗中檢視您的應用程式，然後遵循提示來新增數字 **42** 和 **119**。

   您的應用程式看起來應該類似下列螢幕擷取畫面：

    ![主控台視窗顯示計算機應用程式，並包含要採取之動作的提示](./media/csharp-console-calculator.png)

### <a name="add-decimals"></a>新增小數

目前，計算機應用程式會接受並傳回整數。 但如果我們新增可允許小數的程式碼，會讓其更精確。

如下列螢幕擷取畫面所示，如果您執行應用程式，將數字 42 除以數字 119，結果會是 0 (零)，並不正確。

![主控台視窗顯示計算機應用程式不會在結果中傳回小數](./media/csharp-console-calculator-nodecimal.png)

讓我們修正程式碼來處理小數。

1. 按 **Ctrl** + **F** 以開啟 [尋找和取代] 控制項。

1. 將 `int` 變數的每個執行個體變更為 `float`。

    ![顯示如何將 int 變數變更為 float 的 [尋找和取代] 控制項動畫](./media/find-replace-control-animation.gif)

1. 再次執行您的計算機應用程式，將數字 **42** 除以數字 **119**。

   您會看到應用程式現在會傳回小數，而不是零。

    ![主控台視窗顯示計算機應用程式現在會在結果中傳回小數](./media/csharp-console-calculator-decimal.png)

不過，應用程式僅會產生小數結果。 讓我們進一步調校程式碼，讓應用程式也可以計算小數。

1. 使用 [尋找和取代] 控制項 (**Ctrl** + **F**)，將 `float` 變數的每個執行個體變更為 `double`，以及將 `Convert.ToInt32` 方法的每個執行個體變更為 `Convert.ToDouble`。

1. 執行您的計算機應用程式，將數字 **42.5** 除以數字 **119.75**。

   您會看到應用程式現在接受小數值，並會在結果中傳回較長的小數數字。

    ![主控台視窗顯示計算機應用程式現在接受小數數字並在結果中傳回小數數字](./media/csharp-console-calculator-usedecimals.png)

    (我們將在[修改程式碼](#revise-the-code)一節中修正小數位數數字。)

## <a name="debug-the-app"></a>偵錯應用程式

我們已改善基本計算機應用程式，但還不具備處理例外狀況的保險方式，例如使用者輸入錯誤。

例如，如果您嘗試將數字除以零，或在應用程式僅接受數字字元時輸入英文字元 (反之亦然)，則應用程式會停止運作並傳回錯誤。

讓我們逐步解說一些常見的使用者輸入錯誤，在[偵錯工具](../../debugger/debugger-feature-tour.md)將其找出，並在程式碼中修正。

### <a name="fix-the-divide-by-zero-error"></a>修正「除以零」錯誤

當您嘗試將數字除以零時，主控台應用程式會凍結。 Visual Studio 接著會顯示程式碼編輯器中的錯誤。

   ![Visual Studio 程式碼編輯器顯示「除以零」錯誤](./media/csharp-console-calculator-dividebyzero-error.png)

讓我們變更程式碼來處理此錯誤。

1. 刪除直接出現在 `case "d":` 和指出 `// Wait for the user to respond before closing` 之註解間的程式碼。

1. 使用下列程式碼將其取代：

   ```csharp
            // Ask the user to enter a non-zero divisor until they do so
                while (num2 == 0)
                {
                    Console.WriteLine("Enter a non-zero divisor: ");
                    num2 = Convert.ToInt32(Console.ReadLine());
                }
                Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                break;
        }
    ```

   新增程式碼後，具有 `switch` 陳述式的區段看起來會類似下列螢幕擷取畫面：

   ![Visual Studio 程式碼編輯器中經修改的「切換」區段](./media/csharp-console-calculator-switch-code.png)

現在，當您將任何數字除以零時，應用程式會要求輸入其他數字。 不只是如此：應用程式會持續要求直到您提供非零的數字。

   ![Visual Studio 程式碼編輯器顯示「除以零」錯誤](./media/csharp-console-calculator-dividebyzero.png)

### <a name="fix-the-format-error"></a>修正「格式」錯誤

如果應用程式僅接受數字字元，而您輸入了英文字元 (反之亦然)，則主控台應用程式會凍結。 Visual Studio 接著會顯示程式碼編輯器中的錯誤。

   ![Visual Studio 程式碼編輯器顯示格式錯誤](./media/csharp-console-calculator-format-error.png)

若要修正此錯誤，我們必須重構先前輸入的程式碼。

#### <a name="revise-the-code"></a>修改程式碼

我們將應用程式分為兩類：`calculator` 和 `program`，而不依賴 `program` 類別來處理所有程式碼。  

`calculator` 類別會處理大量計算工作，`program` 類別會處理使用者介面和錯誤擷取工作。

我們現在就開始吧。

1. 刪除下列程式碼區塊「之後」的所有項目：

    ```csharp

    using System;

    namespace Calculator
    {

    ```

1. 接下來，新增 `calculator` 類別，如下所示：

    ```csharp
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    ```

1. 然後，新增 `program` 類別，如下所示：

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
    ```
1. 選擇 [Calculator] 來執行您的程式 (或按 **F5**)。

1. 遵循提示，將數字 **42** 除以數字 **119**。 應用程式看起來應類似下圖：

    ![主控台視窗顯示重構的應用程式，包含要採取那些動作和處理不正確輸入的提示](./media/csharp-console-calculator-refactored.png)

    請注意，在您關閉主控台應用程式前，您可以選擇輸入其他方程式。 此外，我們也減少了結果中的小數位數。

## <a name="close-the-app"></a>關閉應用程式

1. 如果您尚未這麼做，請關閉計算機應用程式。

1. 關閉 Visual Studio 中的 [輸出] 窗格。

   ![關閉 Visual Studio 中的 [輸出] 窗格](./media/csharp-calculator-close-output-pane.png)

1. 在 Visual Studio 中，按 **Ctrl**+**S** 來儲存您的應用程式。

1. 關閉 Visual Studio。

## <a name="code-complete"></a>程式碼完成

在此教學課程中，我們對計算機應用程式進行了許多變更。 應用程式現在會更有效率處理運算資源，並處理大部分的使用者輸入錯誤。

以下是完整程式碼總整理：

```csharp

using System;

namespace Calculator
{
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
}

```

## <a name="quick-answers-faq"></a>常見問題集快問快答

以下提供常見問題集的快問快答，來強調幾個重要概念。 常見問題集也包含您遵循本教學課程的程序時，可能出現之問題的解答。

### <a name="what-is-c"></a>什麼是 C#?

C# 是在 NET Framework 與 .NET Core 上執行的型別安全程式設計語言。 使用 C#，您可以建立 Windows 應用程式、主從式應用程式、資料庫應用程式、XML Web Service、分散式元件等等。

### <a name="what-is-visual-studio"></a>什麼是 Visual Studio？

Visual Studio 是開發人員生產力工具的整合式開發套件。 請將它視為可用來建立程式和應用程式的程式。

### <a name="what-is-a-console-app"></a>什麼是主控台應用程式？

主控台應用程式會接受輸入，並在命令列視窗 (也稱為 主控台) 中顯示輸出。

### <a name="what-is-net-core"></a>什麼是 .NET Core？

.NET Core 是 .NET Framework 的下一個進化步驟。 如果 .NET Framework 可讓您跨程式設計語言來共用程式碼，則 .NET Core 會新增跨平台共用程式碼的能力。 更好的是，它是開放原始碼 

(.NET Framework 與 .NET Core 都包含預先建置功能的程式庫。 它們也包含通用語言執行平台 (CLR)，它會作為執行您程式碼的虛擬機器。)

### <a id="workload"></a>什麼是工作負載？如何新增？

Visual Studio 中的工作負載，代表一組您可用來自訂 Visual Studio 安裝的程式設計選項和範本。 工作負載僅會安裝所選程式設計語言和平台所需的工具。 以下是其安裝方式。

#### <a name="option-1-use-the-new-project-dialog-box"></a>選項 1：使用 [新增專案] 對話方塊

1. 選擇 [新增專案] 對話方塊左窗格中的 [開啟 Visual Studio 安裝程式] 連結。

   ![從 [新增專案] 對話方塊選擇 [開啟 Visual Studio 安裝程式] 連結](./media/csharp-open-visual-studio-installer-generic-dark.png)

1. Visual Studio 安裝程式即會啟動。 選擇 [.NET Core 跨平台開發] 工作負載，然後選擇 [修改]。

   ![Visual Studio 安裝程式中的 .NET Core 跨平台開發工作負載](./media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>選項 2：使用 [工具] 功能表列

1. 請取消 [新專案] 對話方塊，然後從頂端功能表列中選擇 [工具] > [取得工具和功能]。

1. Visual Studio 安裝程式即會啟動。 選擇 [.NET Core 跨平台開發] 工作負載，然後選擇 [修改]。

## <a name="next-steps"></a>後續步驟

恭喜您完成此教學課程！ 若要更深入了解，請繼續下列教學課程。

> [!div class="nextstepaction"]
> [C# 教學課程](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>另請參閱

* [適合無基礎新手參加的 C# 基礎影片課程](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)