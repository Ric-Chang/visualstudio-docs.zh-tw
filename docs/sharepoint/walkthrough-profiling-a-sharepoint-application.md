---
title: 逐步解說：剖析 SharePoint 應用程式 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, profiling
- performance testing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, performance testing
- profiling [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4cb4e2ac95a17adc918be50fa351a35174f128b1
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2019
ms.locfileid: "54867516"
---
# <a name="walkthrough-profile-a-sharepoint-application"></a>逐步解說：分析 SharePoint 應用程式
  本逐步解說將示範如何使用 Visual Studio 中的程式碼剖析工具最佳化 SharePoint 應用程式的效能。 範例應用程式是 SharePoint 功能事件接收器，內含的閒置迴圈會降低功能事件接收器的效能。 Visual Studio 分析工具可讓您尋找並消除成本最高 （最慢執行） 專案的一部分，也稱為*最忙碌路徑*。  
  
 本逐步解說將示範下列工作：  
  
- [新增功能和功能事件接收器](#BKMK_AddFtrandFtrEvntReceiver)。  
  
- [設定和部署 SharePoint 應用程式](#BKMK_ConfigSharePointApp)。  
  
- [執行 SharePoint 應用程式](#BKMK_RunSPApp)。  
  
- [檢視和解譯分析結果](#BKMK_ViewResults)。  
  
  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>必要條件  
 您需要下列元件才能完成此逐步解說：  
  
-   支援的 Microsoft Windows 和 SharePoint 版本。
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
## <a name="create-a-sharepoint-project"></a>建立 SharePoint 專案
 首先，建立 SharePoint 專案。  
  
#### <a name="to-create-a-sharepoint-project"></a>若要建立 SharePoint 專案  
  
1. 在功能表列上選擇 [**檔案** > **新增** > **專案**顯示**新專案**] 對話方塊。  
  
2. 依序展開**SharePoint**節點之下**Visual C#** 或**Visual Basic**，然後選擇**2010年**節點。  
  
3. 在 [範本] 窗格中，選擇**SharePoint 2010 專案**範本。  
  
4. 在 [**名稱**方塊中，輸入**ProfileTest**，然後選擇 **[確定]** ] 按鈕。  
  
    **SharePoint 自訂精靈**隨即出現。  
  
5. 在 **指定偵錯的網站和安全性層級**頁面上，輸入您要偵錯網站定義中，SharePoint 伺服器網站的 URL，或使用預設位置 (http://<em>系統名稱</em>/).  
  
6. 在 **此 SharePoint 方案的信任層級為何？** 區段中，選擇**部署為伺服陣列方案**選項按鈕。  
  
    目前您只能分析陣列方案。 如需有關沙箱化方案與伺服器陣列方案的詳細資訊，請參閱[沙箱化方案考量](../sharepoint/sandboxed-solution-considerations.md)。  
  
7. 選擇**完成** 按鈕。 專案會出現在**方案總管 中**。  
  
## <a name="add-a-feature-and-feature-event-receiver"></a>新增功能和功能事件接收器
 接下來，在專案中加入功能與功能的事件接收器。 這個事件接收器會包含要分析的程式碼。  
  
#### <a name="to-add-a-feature-and-feature-event-receiver"></a>若要加入功能和功能事件接收器  
  
1.  在**方案總管 中**，開啟捷徑功能表**功能**節點，選擇**新增功能**，並將名稱保留預設值， **Feature1**.  
  
2.  在 **方案總管 中**，開啟捷徑功能表**Feature1**，然後選擇 **加入事件接收器**。  
  
     這樣會將程式碼檔案加入至具有多個標記為註解之事件處理常式的功能，並開啟檔案進行編輯。  
  
3.  在事件接收器類別中，加入下列變數宣告。  
  
    ```vb  
    ' SharePoint site/subsite.  
    Private siteUrl As String = "http://localhost"  
    Private webUrl As String = "/"  
    ```  
  
    ```csharp  
    // SharePoint site/subsite.  
    private string siteUrl = "http://localhost";  
    private string webUrl = "/";  
    ```  
  
4.  使用下列程式碼取代 `FeatureActivated` 程序。  
  
    ```vb  
    Public Overrides Sub FeatureActivated(properties As SPFeatureReceiverProperties)  
        Try  
            Using site As New SPSite(siteUrl)  
                Using web As SPWeb = site.OpenWeb(webUrl)  
                    ' Reference the lists.  
                    Dim announcementsList As SPList = web.Lists("Announcements")  
  
                    ' Add a new announcement to the Announcements list.  
                    Dim listItem As SPListItem = announcementsList.Items.Add()  
                    listItem("Title") = "Activated Feature: " & Convert.ToString(properties.Definition.DisplayName)  
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was activated on: " & DateTime.Now.ToString()  
                    ' Waste some time.  
                    TimeCounter()  
                    ' Update the list.  
                    listItem.Update()  
                End Using  
            End Using  
  
        Catch e As Exception  
            Console.WriteLine("Error: " & e.ToString())  
        End Try  
    End Sub  
    ```  
  
    ```csharp  
    public override void FeatureActivated(SPFeatureReceiverProperties properties)  
    {  
        try  
        {  
            using (SPSite site = new SPSite(siteUrl))  
            {  
                using (SPWeb web = site.OpenWeb(webUrl))  
                {  
                    // Reference the lists.  
                    SPList announcementsList = web.Lists["Announcements"];  
  
                    // Add a new announcement to the Announcements list.  
                    SPListItem listItem = announcementsList.Items.Add();  
                    listItem["Title"] = "Activated Feature: " + properties.Definition.DisplayName;  
                    listItem["Body"] = properties.Definition.DisplayName + " was activated on: " +   
    DateTime.Now.ToString();  
                    // Waste some time.  
                    TimeCounter();  
                    // Update the list.  
                    listItem.Update();                          
                }  
            }  
        }  
  
        catch (Exception e)  
        {  
            Console.WriteLine("Error: " + e.ToString());  
        }  
    }  
    ```  
  
5.  加入下列程序下方`FeatureActivated`程序。  
  
    ```vb  
  
    Public Sub TimeCounter()  
        Dim result As Integer  
        For i As Integer = 0 To 99999  
            For j As Integer = 0 To 9999  
                result = i * j  
            Next j  
        Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void TimeCounter()  
    {  
        for (int i = 0; i < 100000; i++)  
        {  
            for (int j = 0; j < 10000; j++)  
            {  
                int result = i * j;  
            }  
        }  
    }  
    ```  
  
6.  在 [**方案總管] 中**，開啟專案的捷徑功能表 (**ProfileTest**)，然後選擇**屬性**。  
  
7.  在 [**屬性**對話方塊方塊中，選擇**SharePoint** ] 索引標籤。  
  
8.  在 **現用部署組態**清單中，選擇**無啟用**。  
  
     選取這個部署組態可讓您之後在 SharePoint 中手動啟用這個功能。  
  
9. 儲存專案。  
  
## <a name="configure-and-deploy-the-sharepoint-application"></a>設定和部署 SharePoint 應用程式
 現在 SharePoint 專案已就緒，請設定它並將它部署至 SharePoint 伺服器。  
  
#### <a name="to-configure-and-deploy-the-sharepoint-application"></a>若要設定和部署 SharePoint 應用程式  
  
1.  在 **分析**功能表上，選擇**啟動效能精靈**。  
  
2.  第一頁上**效能精靈**，將保留做為程式碼剖析方法**CPU 取樣**，然後選擇 **下一步**  按鈕。  
  
     其他程式碼剖析方法可在進階的程式碼剖析情況下使用。 如需詳細資訊，請參閱[了解效能收集方法](/visualstudio/profiling/understanding-performance-collection-methods)。  
  
3.  在頁面上的兩個**效能精靈**，保留其設定檔目標**ProfileTest** ，然後選擇 **下一步**  按鈕。  
  
     如果方案中有多個專案，這些專案都會出現在這個清單中。  
  
4.  在頁面上的三種**效能精靈**，清除**啟用階層互動分析**核取方塊，，然後選擇**下一步**  按鈕。  
  
     [階層互動分析] (TIP) 功能對於測量查詢資料庫之應用程式的效能，以及顯示網頁的要求次數來說很有用。 不過，這個範例中不需要這項資料，因此我們將不會啟用這個功能。  
  
5.  在頁面上的四個**效能精靈**，保留**完成精靈後啟動分析**核取方塊選取，然後選擇 [**完成**] 按鈕。  
  
     此精靈可讓您在伺服器上的應用程式程式碼剖析，會顯示**效能總管**  視窗中，然後建置、 部署和執行 SharePoint 應用程式。  
  
## <a name="run-the-sharepoint-application"></a>執行 SharePoint 應用程式
 啟用 SharePoint 中的功能，觸發 `FeatureActivation` 事件程式碼使其執行。  
  
#### <a name="to-run-the-sharepoint-application"></a>若要執行 SharePoint 應用程式  
  
1.  在 SharePoint 中，開啟**網站動作**功能表，然後選擇**站台設定**。  
  
2.  在 **站台動作**清單中，選擇**管理網站功能**連結。  
  
3.  在 **功能**清單中，選擇**Activate**旁**ProfileTest Feature1**。  
  
     由於會在 `FeatureActivated` 函式中呼叫閒置迴圈，因此當您執行這項操作時會暫停。  
  
4.  在 **快速啟動**列上，選擇**列出**，然後在**列出**清單中，選擇**公告**。  
  
     您會發現清單中已加入一項新公告，說明功能已啟動。  
  
5.  關閉 SharePoint 網站。  
  
     關閉 SharePoint 之後，分析工具會建立和顯示樣本分析報告並將它儲存在以.vsp 檔形式**ProfileTest**專案的資料夾。  
  
## <a name="view-and-interpret-the-profile-results"></a>檢視和解譯的設定檔結果
 現在您已執行並分析 SharePoint 應用程式，接下來要檢視測試結果。  
  
#### <a name="to-view-and-interpret-the-profile-results"></a>若要檢視和解譯的設定檔結果
  
1.  在 **執行最多個別工作的函式**一節的範例程式碼剖析報表，請注意，`TimeCounter`會靠近清單的頂端。  
  
     這個位置指出 `TimeCounter` 是其中一個擁有最多樣本數目的函式，表示它是應用程式中最大的效能瓶頸之一。 不過，這種情形並不意外，因為它是為了方便示範而刻意設計成這樣。  
  
2.  在 **執行最多個別工作的函式**區段中，選擇`ProcessRequest`連結可顯示的成本分配`ProcessRequest`函式。  
  
     在 **呼叫的函式**一節`ProcessRequest`，請注意， **FeatureActiviated**函式會列出最耗費資源呼叫的函式。  
  
3.  在 [**呼叫的函式**區段中，選擇**FeatureActivated** ] 按鈕。  
  
     在 **呼叫的函式**一節**FeatureActivated**，`TimeCounter`函式會列出最耗費資源呼叫的函式。 在 **函式程式碼檢視**窗格中，反白顯示的程式碼 (`TimeCounter`) 是作用點，並指出需要更正的位置。  
  
4.  關閉樣本分析報告。  
  
     若要隨時再次檢視報表，請開啟 [.vsp 檔案中的**效能總管]** 視窗。  
  
## <a name="fix-the-code-and-reprofile-the-application"></a>修正程式碼，並重新分析應用程式
 現在已找出 SharePoint 應用程式中的作用點函式，加下來要進行修正。  
  
#### <a name="to-fix-the-code-and-reprofile-the-application"></a>若要修正程式碼並重新分析應用程式  
  
1.  在功能事件接收器程式碼中，將 `TimeCounter` 中的 `FeatureActivated` 方法呼叫標記為註解，以防止呼叫它。  
  
2.  儲存專案。  
  
3.  在 **效能總管**，開啟 目標 資料夾，然後選擇**ProfileTest**節點。  
  
4.  在上**效能總管**工具列，請在**動作**索引標籤上，選擇 **啟動程式碼剖析** 按鈕。  
  
     如果您想要變更任何程式碼剖析的屬性之前重新分析應用程式，請選擇**啟動效能精靈**按鈕。  
  
5.  請依照下列中的指示**執行 SharePoint 應用程式**區段中的，先前在本主題中。  
  
     現在功能啟動的速度應該加快許多，因為已消除呼叫閒置迴圈。 樣本分析報告應該會反映這種情況。  
  
## <a name="see-also"></a>另請參閱
 [效能總管](/visualstudio/profiling/performance-explorer)   
 [效能工作階段概觀](/visualstudio/profiling/performance-session-overview)   
 [效能分析的初級開發人員指南](/visualstudio/profiling/beginners-guide-to-performance-profiling)   
 [尋找與 Visual Studio Profiler 的應用程式瓶頸](http://go.microsoft.com/fwlink/?LinkID=137266)  
