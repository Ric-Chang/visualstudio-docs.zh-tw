---
title: 將資料儲存至資料庫 （多個資料表） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- updating datasets, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], updating
ms.assetid: 7ebe03da-ce8c-4cbc-bac0-a2fde4ae4d07
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 986df2d58c9a8955c9de9b45edaa5276b2e68bfb
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2018
ms.locfileid: "50218399"
---
# <a name="save-data-to-a-database-multiple-tables"></a>將資料儲存至資料庫 (多個資料表)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
在應用程式的開發過程中，最常見的一個情節是在 Windows 應用程式的表單上顯示資料並編輯資料，以及將更新的資料傳送回資料庫。 此逐步解說會建立表單，以顯示來自兩個關聯資料表的資料，並示範如何編輯記錄，以及將變更儲存回資料庫。 此範例使用 Northwind 範例資料庫的 `Customers` 和 `Orders` 資料表。  
  
 您可以透過呼叫 TableAdapter 的 `Update` 方法，將應用程式的資料存回資料庫。 當您將資料表從**Zdroje dat**視窗拖曳到表單時，必須先儲存資料的程式碼會自動加入。加入至表單的任何其他資料表都需要手動加入此程式碼。 此逐步解說會示範如何加入程式碼，以儲存多個資料表的更新。  
  
> [!NOTE]
>  對話方塊和功能表命令，您會看到，可能會有所不同說明中所述取決於您使用的設定或您使用的版本不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
 這個逐步解說中所述的工作包括：  
  
-   建立新**Windows 應用程式**專案。  
  
-   建立及設定您的應用程式中的資料來源[資料來源組態精靈](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。  
  
-   設定控制項中項目的[資料來源視窗](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)。 如需詳細資訊，請參閱 <<c0> [ 設定要從資料來源視窗拖曳時要建立的控制項](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)。  
  
-   建立資料繫結控制項中的項目**Zdroje dat**視窗拖曳至表單。  
  
-   修改資料集中的每個資料表中的一些記錄。  
  
-   修改程式碼，以將資料集中更新的資料傳送回資料庫。  
  
## <a name="prerequisites"></a>必要條件  
 若要完成這個逐步解說，您將需要：  
  
-   Northwind 範例資料庫的存取權。  如需詳細資訊，請參閱 <<c0> [ 如何： 安裝範例資料庫](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="create-the-windows-application"></a>建立 Windows 應用程式  
 第一個步驟是建立**Windows 應用程式**。 指派至專案的名稱是在此步驟中，選擇性，但因為我們打算稍後要儲存它將會賦予它名稱。  
  
#### <a name="to-create-the-new-windows-application-project"></a>若要建立新的 Windows 應用程式專案  
  
1.  在 [**檔案**] 功能表中，建立新的專案。  
  
2.  將專案命名為 `UpdateMultipleTablesWalkthrough`。  
  
3.  選取  **Windows 應用程式**，然後選取**確定**。 如需詳細資訊，請參閱 <<c0> [ 用戶端應用程式](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)。  
  
     **UpdateMultipleTablesWalkthrough**建立專案並將其加入至**方案總管 中**。  
  
## <a name="create-the-data-source"></a>建立資料來源  
 這個步驟會建立從 Northwind 資料庫使用的資料來源**資料來源組態精靈**。 您必須具有 Northwind 範例資料庫的存取權，才能建立連接。 如需設定 Northwind 範例資料庫的詳細資訊，請參閱[如何： 安裝範例資料庫](../data-tools/how-to-install-sample-databases.md)。  
  
#### <a name="to-create-the-data-source"></a>若要建立資料來源  
  
1.  在 **資料**功能表上，選取**顯示資料來源**。  
  
2.  在 **資料來源**視窗中，選取**加入新的資料來源**來啟動**資料來源組態精靈**。  
  
3.  在 [**選擇資料來源類型**畫面上，選取**資料庫**，然後選取**下一步]**。  
  
4.  在 **選擇您的資料連接**畫面執行下列其中一項：  
  
    -   如果下拉式清單中有提供 Northwind 範例資料庫的資料連接，請選取這個資料連接。  
  
         -或-  
  
    -   選取 [**新的連線**以開啟**加入/修改連接**] 對話方塊。  
  
5.  如果您的資料庫需要密碼，請選取選項來加入敏感性資料，然後選取**下一步**。  
  
6.  在 [**將連接字串儲存到應用程式組態檔**，選取**下一步]**。  
  
7.  在 **選擇您的資料庫物件**畫面上，展開**資料表**節點。  
  
8.  選取 **客戶**並**訂單**資料表，然後選取**完成**。  
  
     **NorthwindDataSet**新增至您的專案，且資料表會出現在**Zdroje dat**視窗。  
  
## <a name="set-the-controls-to-be-created"></a>設定要建立的控制項  
 在這個逐步解說中的資料`Customers`資料表存在於**詳細資料**其中資料會顯示在個別控制項的版面配置。 將資料從`Orders`資料表存在於**格線**版面配置中顯示<xref:System.Windows.Forms.DataGridView>控制項。  
  
#### <a name="to-set-the-drop-type-for-the-items-in-the-data-sources-window"></a>在資料來源視窗中設定項目的卸除類型  
  
1.  在 [**資料來源**] 視窗中，展開**客戶**節點。  
  
2.  在上**客戶**節點中，選取**詳細資料**若要變更的控制項的控制項清單**客戶**為個別控制項的資料表。 如需詳細資訊，請參閱 <<c0> [ 設定要從資料來源視窗拖曳時要建立的控制項](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)。  
  
## <a name="create-the-data-bound-form"></a>建立資料繫結表單  
 您可以建立資料繫結控制項項目從**Zdroje dat**視窗拖曳至表單。  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>在表單上建立資料繫結控制項  
  
1.  主**客戶**從節點**Zdroje dat**  視窗拖曳到**Form1**。  
  
     會在表單上顯示具有描述性標籤的資料繫結控制項，以及巡覽記錄的工具區域 (<xref:System.Windows.Forms.BindingNavigator>)。 A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)， [CustomersTableAdapter](../data-tools/tableadapter-overview.md)， <xref:System.Windows.Forms.BindingSource>，和<xref:System.Windows.Forms.BindingNavigator>會出現在元件匣。  
  
2.  將相關**訂單**從節點**Zdroje dat**  視窗拖曳到**Form1**。  
  
    > [!NOTE]
    >  相關**訂單**節點下方**傳真**資料行，且為的子節點**客戶**節點。  
  
     <xref:System.Windows.Forms.DataGridView> 控制項以及用於巡覽記錄的工具區域 (<xref:System.Windows.Forms.BindingNavigator>) 會出現在表單上。 [OrdersTableAdapter](../data-tools/tableadapter-overview.md)和<xref:System.Windows.Forms.BindingSource>會出現在元件匣。  
  
## <a name="addcode-to-update-the-database"></a>若要更新資料庫 Addcode  
 您可以藉由呼叫來更新資料庫`Update`方法**客戶**並**訂單**TableAdapters。 根據預設，事件處理常式**儲存**按鈕<xref:System.Windows.Forms.BindingNavigator>新增至表單的程式碼，以將更新傳送至資料庫。 此程序修改程式碼，以將更新傳送正確的順序。這會排除參考完整性錯誤提高的可能性。 程式碼也會藉由將 try-catch 區塊中的更新呼叫換行，以實作錯誤處理。 您可以修改程式碼，使其符合應用程式的需求。  
  
> [!NOTE]
>  為了清楚起見，本逐步解說中所使用的交易。不過，如果您正在更新兩個或多個相關資料表，包含在交易內的所有更新邏輯。 交易是確保對資料庫的所有相關的變更都成功，認可任何變更之前的程序。 如需詳細資訊，請參閱 <<c0> [ 異動和並行存取](http://msdn.microsoft.com/library/f46570de-9e50-4fe6-8710-a8c31fa8569b)。  
  
#### <a name="to-add-update-logic-to-the-application"></a>將更新邏輯加入至應用程式  
  
1.  選取 **儲存**按鈕<xref:System.Windows.Forms.BindingNavigator>。這會開啟程式碼編輯器`bindingNavigatorSaveItem_Click`事件處理常式。  
  
2.  替換事件處理常式中的程式碼，以呼叫相關 TableAdapters 的 `Update` 方法。 下列程式碼會先建立三個暫存資料表，以保留 <xref:System.Data.DataRowState> (<xref:System.Data.DataRowState>、<xref:System.Data.DataRowState> 及 <xref:System.Data.DataRowState>) 的更新資訊。 然後更新會以正確的順序執行。 程式碼看起來應該如下所示：  
  
     [!code-csharp[VbRaddataSaving#10](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form4.cs#10)]
     [!code-vb[VbRaddataSaving#10](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form4.vb#10)]  
  
## <a name="test-the-application"></a>測試應用程式  
  
#### <a name="to-test-the-application"></a>若要測試應用程式  
  
1.  選取  **F5**。  
  
2.  在每個資料表中，變更一個或多個記錄的資料。  
  
3.  選取 [**儲存**] 按鈕。  
  
4.  檢查資料庫中的值，確認已儲存變更。  
  
## <a name="next-steps"></a>後續步驟  
 根據您的應用程式的需求，有幾個步驟，您可能想要在 Windows 應用程式中建立資料繫結表單之後執行。 一些您可以加強這個逐步解說的部分包括：  
  
-   將搜尋功能加入至表單。 如需詳細資訊，請參閱 <<c0> [ 如何： 將參數化查詢加入至 Windows Forms 應用程式](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)。  
  
-   編輯資料來源，以加入或移除資料庫物件。 如需詳細資訊，請參閱 <<c0> [ 如何： 編輯資料集](http://msdn.microsoft.com/library/f2dade5f-9c7a-4ddb-96a8-e0a39e50bfd3)。  
  
## <a name="see-also"></a>另請參閱  
 [將資料儲存回資料庫](../data-tools/save-data-back-to-the-database.md)

