---
title: 將命令加入至 [方案總管] 工具列 |Microsoft Docs
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
- toolbars [Visual Studio], adding buttons
- buttons [Visual Studio], adding to Solution Explorer
- Solution Explorer, adding buttons
ms.assetid: f6411557-2f4b-4e9f-b02e-fce12a6ac7e9
caps.latest.revision: 40
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 52e963a202d75c29c65521729e70e062a579d479
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51753651"
---
# <a name="adding-a-command-to-the-solution-explorer-toolbar"></a>將命令新增至方案總管工具列
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本逐步解說示範如何加入一個按鈕來**方案總管 中**工具列。  
  
 工具列或功能表上的任何命令會呼叫在 Visual Studio 中的按鈕。 按一下按鈕時，會執行的命令處理常式中的程式碼。 通常，相關的命令會群組在一起以形成一個群組。 功能表或工具列做為容器群組。 優先順序會決定以個別的命令群組中會出現在功能表或工具列上的順序。 您可以防止按鈕不會再顯示工具列或功能表上，藉由控制其可見性。 命令中所列`<VisibilityConstraints>`.vsct 檔的區段只會出現在相關聯的內容。 可見性無法套用到群組。  
  
 如需功能表、 工具列命令和.vsct 檔的詳細資訊，請參閱[命令、 功能表和工具列](../extensibility/internals/commands-menus-and-toolbars.md)。  
  
> [!NOTE]
>  使用 XML 命令表檔案 (.vsct) 而不是命令資料表設定 (.ctc) 檔案，來定義您的 Vspackage 中出現的功能表和命令。 如需詳細資訊，請參閱 [Visual Studio Command Table (.Vsct) Files](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)。  
  
## <a name="prerequisites"></a>必要條件  
 從 Visual Studio 2015 中，從下載中心取得未安裝 Visual Studio SDK。 包含為 Visual Studio 安裝程式的選用功能。 您也可以在稍後安裝 VS SDK。 如需詳細資訊，請參閱 <<c0> [ 安裝 Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md)。  
  
## <a name="creating-an-extension-with-a-menu-command"></a>建立具有功能表命令的延伸模組  
 建立 VSIX 專案，名為`SolutionToolbar`。 加入名為功能表命令項目範本**ToolbarButton**。 如需如何執行這項操作的資訊，請參閱[建立具有功能表命令的擴充](../extensibility/creating-an-extension-with-a-menu-command.md)。  
  
## <a name="adding-a-button-to-the-solution-explorer-toolbar"></a>加入 [方案總管] 工具列按鈕  
 本章節的逐步解說示範如何加入一個按鈕來**方案總管 中**工具列。 當按一下按鈕時，會執行的回呼方法中的程式碼。  
  
1.  在 ToolbarButtonPackage.vsct 檔案中，移至`<Symbols>`一節。 `<GuidSymbol>`節點包含功能表群組和 [套件] 範本所產生的命令。 新增`<IDSymbol>`到這個節點，以宣告會保留您的命令群組的項目。  
  
    ```xml  
    <IDSymbol name="SolutionToolbarGroup" value="0x0190"/>  
    ```  
  
2.  在 [ `<Groups>` ] 區段中之後的現有的群組項目，, 定義您宣告的新群組在上一個步驟。  
  
    ```xml  
    <Group guid="guidToolbarButtonPackageCmdSet"  
           id="SolutionToolbarGroup" priority="0xF000">  
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/>  
          </Group>  
    ```  
  
     若要設定父系 guid: id 配對`guidSHLMainMenu`和`IDM_VS_TOOL_PROJWIN`會將此群組放**方案總管 中**工具列上，並設定高優先順序的值時將它放在其他的命令群組之後。  
  
3.  在 `<Buttons>`區段中，變更所產生的父識別碼`<Button>`項目，以反映您在上一個步驟中定義的群組。 已修改`<Button>`項目應該看起來像這樣：  
  
    ```xml  
    <Button guid="guidToolbarButtonPackageCmdSet" id="ToolbarButtonId" priority="0x0100" type="Button">  
        <Parent guid="guidToolbarButtonPackageCmdSet" id="SolutionToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPicStrikethrough" />  
        <Strings>  
            <ButtonText>Invoke ToolbarButton</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
4.  建置此專案並開始偵錯。 實驗執行個體隨即出現。  
  
     **方案總管] 中**工具列應該會顯示新的命令按鈕右邊的 [現有的按鈕。 按鈕圖示為加刪除線。  
  
5.  按一下 [新增] 按鈕。  
  
     訊息的對話方塊**ToolbarButtonPackage 內 SolutionToolbar.ToolbarButton.MenuItemCallback()** 應該會顯示。  
  
## <a name="controlling-the-visibility-of-a-button"></a>控制按鈕的可見性  
 本章節的逐步解說示範如何控制工具列上按鈕的可見性。 藉由設定內容中的一或多個專案`<VisibilityConstraints>`區段 SolutionToolbar.vsct 檔案中，您可以限制按鈕出現只有一個專案時開啟。  
  
#### <a name="to-display-a-button-when-one-or-more-projects-are-open"></a>若要顯示的按鈕，開啟一或多個專案時  
  
1. 在 `<Buttons>`一節的 ToolbarButtonPackage.vsct，將兩個命令旗標新增至現有`<Button>`項目之間`<Strings>`和`<Icons>`標記。  
  
   ```xml  
   <CommandFlag>DefaultInvisible</CommandFlag>  
   <CommandFlag>DynamicVisibility</CommandFlag>  
   ```  
  
    `DefaultInvisible`並`DynamicVisibility`旗標必須設定操作中的項目`<VisibilityConstraints>`區段才會生效。  
  
2. 建立`<VisibilityConstraints>`區段，其中含有兩個`<VisibilityItem>`項目。 將新的區段之後關閉`</Commands>`標記。  
  
   ```xml  
   <VisibilityConstraints>  
       <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
             id="ToolbarButtonId"  
             context="UICONTEXT_SolutionHasSingleProject" />  
       <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
             id="ToolbarButtonId"  
             context="UICONTEXT_SolutionHasMultipleProjects" />  
   </VisibilityConstraints>  
   ```  
  
    每個可見性項目表示指定的按鈕會顯示在其下的條件。 若要套用多個條件，您必須建立多個項目相同的按鈕。  
  
3. 建置此專案並開始偵錯。 實驗執行個體隨即出現。  
  
    **方案總管 中**工具列不包含刪除線按鈕。  
  
4. 開啟任何包含專案的方案。  
  
    刪除線按鈕會出現在右邊的現有按鈕的工具列。  
  
5. 在 **檔案**功能表上，按一下**關閉方案**。 工具列按鈕就會消失。  
  
   按鈕的可見性由控制[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]直到載入 VSPackage。 VSPackage 載入之後，按鈕的可見性會受到 VSPackage。  如需詳細資訊，請參閱[Menucommand 對比。OleMenuCommands](../misc/menucommands-vs-olemenucommands.md)。  
  
## <a name="see-also"></a>另請參閱  
 [命令、功能表及工具列](../extensibility/internals/commands-menus-and-toolbars.md)

