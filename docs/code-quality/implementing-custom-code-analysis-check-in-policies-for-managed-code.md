---
title: 為 Managed 程式碼實作自訂程式碼分析簽入原則
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.code.analysis.selecttfsrulesets
- vs.code.analysis.browsefortfsruleset
- vs.code.analysis.policyeditor
ms.assetid: fd029003-5671-4b24-8b6f-032e0a98b2e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 194f8dcc20abb4f0c64cc2c9f6c49470ab014b4d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55005499"
---
# <a name="implement-custom-code-analysis-check-in-policies-for-managed-code"></a>為受控碼實作自訂程式碼分析簽入原則

程式碼分析簽入原則會指定一組簽入至版本控制之前，Azure DevOps 專案的成員必須在原始碼執行的規則。 Microsoft 提供一組標準*規則集*該群組的程式碼分析規則到功能區域。 *自訂簽入原則的規則集*指定一組專屬於專案的程式碼分析規則。 規則集儲存在.ruleset 檔案。

簽入原則會在 Azure DevOps 專案層級設定，並指定版本的控制項樹狀結構中的.ruleset 檔案的位置。 沒有任何限制小組原則自訂規則集的版本控制位置。

程式碼分析已針對每個專案的 [屬性] 視窗中的個別程式碼專案。 自訂規則集的程式碼專案是由本機電腦上的.ruleset 檔案的實體位置指定。 位於程式碼專案的相同磁碟機上指定的.ruleset 檔案時，Visual Studio 會使用專案組態中的檔案相對路徑。

建立專案的自訂規則集是用來儲存到不屬於任何程式碼專案的特定資料夾中的簽入原則.ruleset 檔案 Azure DevOps 建議的做法。 如果您將檔案儲存在專用的資料夾，您可以套用權限，以限制可以編輯規則檔案，而且您可以輕鬆地移動的目錄結構，就會包含到另一個目錄或電腦的專案。

## <a name="create-the-project-custom-check-in-rule-set"></a>建立專案的自訂簽入規則集

若要建立自訂規則集 Azure DevOps 專案，您先建立簽入原則中的規則集的特殊資料夾**原始檔控制總管**。 然後您會建立規則集檔案，並將檔案加入至版本控制。 最後，您可以指定為程式碼分析簽入原則專案設定的規則。

> [!NOTE]
> Azure DevOps 專案中建立資料夾，您首先必須對應專案根目錄到本機電腦上的位置。

### <a name="to-create-the-version-control-folder-for-the-check-in-policy-rule-set"></a>若要建立簽入原則規則集的版本控制資料夾

1. 在 Team Explorer 中，展開專案節點，然後**原始檔控制**。

2. 在 [**資料夾**] 窗格中，以滑鼠右鍵按一下專案，然後按一下**新資料夾**。

3. 在主要的原始檔控制 窗格中，以滑鼠右鍵按一下**新的資料夾**，按一下**重新命名**，並輸入此規則設定資料夾的名稱。

### <a name="to-create-the-check-in-policy-rule-set"></a>若要建立簽入原則規則集

1. 在上**檔案**功能表上，指向**新增**，然後按一下**檔案**。

2. 在 **分類**清單中，按一下**一般**。

3. 在 **範本**清單中，按兩下**程式碼分析規則集**。

4. [指定的規則](../code-quality/how-to-create-a-custom-rule-set.md)来包含在規則集中，然後儲存規則集檔案至您所建立的規則集資料夾。

### <a name="to-add-the-rule-set-file-to-version-control"></a>若要將規則新增設定檔至版本控制

1. 在 **原始檔控制總管**，以滑鼠右鍵按一下新的資料夾，然後按一下**新增至資料夾的項目**。

     如需詳細資訊，請參閱 < [Git 和 Azure 儲存機制](/azure/devops/repos/git/overview?view=vsts)。

2. 按一下此規則設定您所建立的檔案，然後按一下**完成**。

     檔案會加入原始檔控制，並簽出給您。

3. 在 **原始檔控制總管**詳細資料 視窗中，以滑鼠右鍵按一下 檔案名稱，然後按一下**簽入暫止的變更**。

4. 在 [**簽入時**] 對話方塊中，您可以選擇新增註解，然後按一下**簽入**。

    > [!NOTE]
    > 如果您已經為您的 Azure DevOps 專案設定程式碼分析簽入原則，而且您已選取**簽入使其僅包含屬於目前方案的檔案強制執行**，您將會觸發原則失敗警告。 在原則失敗 對話方塊中，選取**覆寫原則失敗，並繼續簽入**。 新增必要的註解，然後再按**確定**。

### <a name="to-specify-the-rule-set-file-as-the-check-in-policy"></a>若要指定規則集檔案為簽入原則

1. 在上**Team**功能表上，指向**專案設定**，然後按一下**原始檔控制**。

2. 按一下 **簽入原則**，然後按一下**新增**。

3. 在 **簽入原則**清單中，按兩下**程式碼分析**，並確定**強制執行 Managed 程式碼的程式碼分析**選取核取方塊。

4. 在 **執行此規則集**清單中，按一下**\<從原始檔控制選取規則集 >**。

5. 在版本控制中，輸入簽入原則的規則集檔案的路徑。

     路徑必須符合下列語法：

     **$/** `TeamProjectName` **/** `VersionControlPath`

    > [!NOTE]
    > 您可以使用下列程序，在其中複製路徑**原始檔控制總管**:

    - 在 **資料夾** 窗格中，按一下 規則集檔案所在的資料夾。 複製資料夾中所顯示的版本控制路徑**來源**方塊，然後以手動方式輸入規則集檔案的名稱。

    - 在詳細資料視窗中，規則集檔案，以滑鼠右鍵按一下，然後按一下**屬性**。 在 **一般**索引標籤上，複製 中的 值**伺服器名稱**。

## <a name="synchronize-code-projects-to-the-check-in-policy-rule-set"></a>同步處理至簽入原則規則集的程式碼專案

您指定的專案簽入原則規則設定為程式碼專案組態中的程式碼專案的 [屬性] 對話方塊中的程式碼分析規則集。 如果規則集位於相同的磁碟機的程式碼專案，相對路徑會使用指定的規則集，從 [檔案] 對話方塊中選取的路徑時。 相對路徑可讓專案屬性設定，可以移植到其他電腦是否使用類似的本機版本控制結構。

### <a name="to-specify-a-project-rule-set-as-the-rule-set-of-a-code-project"></a>若要指定專案的規則設定為在程式碼專案規則集

1. 如有必要，請從版本控制中擷取的簽入原則規則集資料夾和檔案。

   您可以執行此步驟中的**原始檔控制總管**以滑鼠右鍵按一下此規則會設定資料夾，然後按一下**取得最新版本**。

2. 在 **方案總管**，以滑鼠右鍵按一下程式碼專案，然後按一下 **屬性**。

3. **按一下 程式碼分析**。

4. 如有必要，按一下適當的選項，在**組態**並**平台**列出。

5. 若要執行程式碼分析程式碼專案使用指定的組態建置每次，請選取**啟用建置程式碼分析 （定義 CODE_ANALYSIS 常數）** 核取方塊。

6. 若要忽略來自其他公司元件中的程式碼，請選取**隱藏所產生的程式碼的結果** 核取方塊。

7. 在 [**執行此規則集**清單中，按一下**\<瀏覽] >**。

8. 指定簽入原則的規則集檔案的本機版本。