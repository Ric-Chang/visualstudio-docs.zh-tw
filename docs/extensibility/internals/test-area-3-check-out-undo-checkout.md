---
title: 測試區域 3:簽出 / 復原簽出 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, checkout
- source control plug-ins, undo checkout
- source control [Visual Studio SDK], checking out
- source control [Visual Studio SDK], undo checkout
ms.assetid: ce00c5a5-d472-4f45-8776-d77a1fbe9d37
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 51722c39ed5fcf6fc35208c5d3ae73f85ac9be9a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929701"
---
# <a name="test-area-3-check-outundo-checkout"></a>測試區域 3:簽出/復原簽出
此原始檔控制外掛程式的測試區域涵蓋編輯和還原的項目，透過的版本存放區**簽出**並**恢復簽出**命令。  

**請參閱**:標記為版本存放區中的項目簽出，修改為讀取/寫入的本機複本。  

**復原簽出**:標記為版本存放區中的項目已簽入，就會還原本機複本簽出 （取決於選項） 之前的狀態。

## <a name="command-menu-access"></a>命令功能表存取  

下列[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]與測試案例中使用整合式的開發環境功能表路徑。  
  
##### <a name="check-out"></a>請參閱：  
  
-   **檔案**，**原始檔控制**，**查看**。  
  
-   **檔案**，**簽出**。  
  
-   快顯功能表**查看**。  
  
-   復原簽出：**檔案**，**原始檔控制**，**復原簽出**。  
  
## <a name="common-expected-behavior"></a>常見的預期的行為  
  
-   簽出作業中之後, 的目標檔案及/或資料夾會標示為在版本存放區中簽出。  
  
-   版本存放區屬性的正確使用者簽出。  
  
-   簽出的日期與時間正確無誤 （每個使用者的設定）。  
  
## <a name="test-cases"></a>測試案例

以下是簽出/復原簽出測試區域的特定測試案例。  
  
### <a name="case-3a-check-out"></a>案例 3a:簽出

本節著重於簽出命令的作業。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|簽出獨佔 (COE) 用戶端專案|1.建立用戶端專案。<br />2.您可以將方案加入原始檔控制。<br />3.以獨佔方式簽出整個專案 (**檔案**，**簽出**)。|簽出，就會發生。|  
|獨佔簽出 (COE) 檔案系統或本機 IIS Web 專案|1.設定檔案共用中的 Web 伺服器連接**工具**，**選項**，**專案**， **Web 設定**。<br />2.建立 Web 專案。<br />3.您可以將方案加入原始檔控制。<br />4.以獨佔方式簽出整個專案 (**檔案**，**原始檔控制**，**簽出**)。|簽出，就會發生。|  
|簽出方案 （新方法來處理其他檔案） 中的方案項目|1.建立空白方案。<br />2.您可以將方案加入原始檔控制。<br />3.簽出方案。<br />4.加入數個解決方案項目。<br />5.簽入所有新加入的項目。<br />6.選取多個方案項目。<br />7.查看 選取的項目 (快顯功能表**簽出**)。|選取的檔案已簽出。|  
|簽出本機版本 （如果受測試的外掛程式支援這項功能）|1.使用者 1:建立用戶端專案。<br />2.使用者 1:您可以將方案加入原始檔控制。<br />3.使用者 2:從原始檔控制開啟方案，到另一個位置。<br />4.使用者 2:簽出檔案。<br />5.使用者 2:修改檔案。<br />6.使用者 2:簽入檔案。<br />7.使用者 1:簽出本機版本的檔案 (檢查**簽出本機版本**進階選項中的**簽出**對話方塊)。|本機版本的檔案已簽出。<br /><br /> 使用者 2 的修改不會套用至使用者 1 檔案。|  
  
### <a name="case-3b-disconnected-check-out"></a>案例 3b:已中斷連線的簽出

在中斷連線模式中作業可讓使用者某種程度的不直接連結到版本存放區時，持續的原始檔控制支援。 這是藉由在本機快取已登錄的方案和專案相關的所有相關資訊。  
  
當連接到原始檔控制存放區時，才會發生獨佔簽出作業。 共用的簽出作業可能會發生在任何時候，是否連線或中斷連線。 因此，當與版本存放區時，只中斷連線**簽出共用**(COS) 已啟用命令。 中斷連接，雖然**恢復簽出**停用，因為無法擷取舊的版本，以取代使用者所做的變更。  
  
當使用者重新連接到版本儲存所有已登錄的解決方案的簽出狀態，和專案會同步處理。 這為使用者已執行簽出進行必要的更新，來存放區。 一旦發生同步處理，使用者可繼續如往常一樣 （連接）。  
  
#### <a name="expected-behavior"></a>預期的行為  
  
-   無法使用**獨佔簽出**命令中斷連線的版本存放區時。  
  
-   無法使用**恢復簽出**命令中斷連線的版本存放區時。  
  
-   **簽出共用**命令運作。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|中斷連接，而簽出檔案，則連接同步處理|1.中斷連線的受控制的專案，使用 [變更原始檔控制] 對話方塊中 (**檔案**，**原始檔控制**，**變更原始檔控制**)。<br />2.簽出檔案。<br />3.按一下 簽出 （中斷連線） 在 警告 對話方塊中。<br />4.編輯檔案。<br />5.使用 [變更原始檔控制] 對話方塊中的連接。<br />6.取得最新版本已編輯的檔案。|常見的預期的行為|  
  
### <a name="case-3c-query-editquery-save-qeqs"></a>案例 3 c:查詢編輯/查詢儲存 (QEQS)  
 原始檔控制下的項目會追蹤變更的編輯，並儲存，以幫助使用者輕鬆管理他們的檔案。 當受控制的項目 」 中檢查 」，以編輯 QEQS 攔截嘗試的編輯，並會詢問使用者是否要簽出檔案進行編輯。 取決於**工具**，**選項**設定，使用者是其中一個會強迫檢查出以編輯的檔案，或可能會允許編輯記憶體中的複本，並稍後簽出。 如果使用者的**工具**，**選項**設定不是以顯示簽出對話方塊，並只簽出，則當使用者進行其編輯，該檔案會自動簽出，可能的話。  
  
#### <a name="expected-behavior"></a>預期的行為  
  
-   簽出作業中之後, 的目標檔案及/或資料夾會標示為在版本存放區中簽出。  
  
-   版本存放區屬性的簽出正確的使用者。  
  
-   簽出的日期與時間正確無誤 （每個使用者的設定）。  
  
-   目標檔案或資料夾的本機複本是可寫入的。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|編輯簽入的文字檔|1.建立新的專案包含的文字檔案。<br />2.您可以將方案加入原始檔控制。<br />3.設定**工具**，**選項**，**原始檔控制**，**允許檔案在磁碟上唯讀時，編輯**為未核取。<br />4.設定**工具**，**選項**，**原始檔控制**，**提示，請參閱**中**簽入檔案時已編輯的**下拉式方塊。<br />5.設定**工具**，**選項**，**原始檔控制**，**提示，請參閱**中**時簽入檔案會儲存**下拉式方塊。<br />6.在編輯器中開啟文字檔案，嘗試將輸入檔案中的新文字。 如果這個步驟成功，則會繼續至下一個步驟。<br />7.按一下 [**取消**中**簽出以編輯**] 對話方塊。 如果這個步驟成功，則會繼續至下一個步驟。<br />8.設定**工具**，**選項**，**原始檔控制**，**允許檔案在磁碟上唯讀時，編輯**為已核取。<br />9.在編輯器中開啟專案檔，嘗試在檔案中輸入新的文字。 如果這個步驟成功，則會繼續至下一個步驟。<br />10.按一下 [**編輯**中**簽出以編輯**] 對話方塊。 如果這個步驟成功，則會繼續至下一個步驟。<br />11.編輯文字檔案，並嘗試將它儲存。|`Result of step 6:`<br /><br /> 針對 [編輯] 對話方塊隨即出現，請簽出。<br /><br /> `Result of step 7:`<br /><br /> 檔案是不變。<br /><br /> `Result of step 9:`<br /><br /> 針對 [編輯] 對話方塊隨即出現，請簽出。<br /><br /> `Result of step 10:`<br /><br /> 您可以編輯專案檔，在記憶體中。<br /><br /> `Result of step 11:`<br /><br /> 在儲存、 簽出上的儲存對話方塊會出現。|  
|編輯簽入的方案檔|如先前所述的步驟測試，但除了修改文字檔案，修改的解決方案藉由變更方案屬性重複。|與前一個測試相同|  
|編輯專案檔簽入|如先前所述的步驟測試，但而不需修改文字檔案，請藉由變更專案屬性中修改專案重複。|與前一個測試相同。|  
  
### <a name="case-3d-silent-check-out"></a>案例 3d:立即簽出  
 此案例的子區域涵蓋檢查其中**簽出**每位使用者的似乎不到對話方塊**工具**，**選項**，**原始檔控制設定**.  
  
#### <a name="expected-behavior"></a>預期的行為  
  
-   簽出作業中之後, 的目標檔案及/或資料夾會標示為在版本存放區中簽出。  
  
-   版本存放區屬性的簽出正確的使用者。  
  
-   簽出的日期與時間正確無誤 （每個使用者的設定）。  
  
-   目標檔案或資料夾的本機複本是可寫入的。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|無訊息的簽出檔案|1.設定**工具**，**選項**，**原始檔控制**至**在編輯時自動簽出檔案**。<br />2.建立新的專案檔案。<br />3.您可以將方案加入原始檔控制。<br />4.簽出檔案。|檔案會以無訊息方式簽出 (無 UI)。|  
|無訊息的簽出專案|1.設定**工具**，**選項**，**原始檔控制**至**在編輯時自動簽出檔案**。<br />2.建立新的專案。<br />3.您可以將方案加入原始檔控制。<br />4.簽出專案。|檔案會以無訊息方式簽出 (無 UI)。|  
  
### <a name="case-3e-undo-check-out"></a>案例 3e:復原簽出  
 **復原簽出**用來取消檔案的簽出狀態，並避免簽入檔案所做的變更。  
  
#### <a name="expected-behavior"></a>預期的行為  
  
-   預設值以使用者為基礎**簽出本機版本**設定。 如果使用者已選擇要簽出本機版本，則復原簽出的預設值是隨時回復簽出的版本。  
  
-   於復原中的圖示接受**方案總管**會更新受影響的檔案和項目會從移除**暫止簽入**視窗。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|復原簽出以獨佔方式簽出的單一檔案|1.建立用戶端專案。<br />2.您可以將方案加入原始檔控制。<br />3.以獨佔方式簽出檔案。<br />4.修改檔案。<br />5.復原簽出 (**檔案**，**原始檔控制**，**復原簽出**)。|常見的預期的行為。|  
|復原簽出共用的單一檔案的簽出|1.建立用戶端專案。<br />2.您可以將方案加入原始檔控制。<br />3.簽出的檔案共用。<br />4.修改檔案。<br />5.復原簽出 (**檔案**，**原始檔控制**，**復原簽出**)。|常見的預期的行為。|  
|復原簽出專案的檔案加入專案之後|1.建立新的專案，並將它新增至原始檔控制。<br />2.簽出專案。<br />3.將檔案加入專案。<br />4.復原簽出專案。|加入的檔案會從 [方案總管] 中的專案中移除。<br /><br /> 專案不會再取出。|  
|從專案刪除檔案後復原簽出的專案|1.建立新的專案，並將它新增至原始檔控制。<br />2.簽出專案。<br />3.從專案刪除檔案。<br />4.復原簽出專案。|已刪除的檔案會出現在 [方案總管] 中專案底下。<br /><br /> 專案不會再取出。|  
  
## <a name="see-also"></a>另請參閱  
 [原始檔控制外掛程式測試指南](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
