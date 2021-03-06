---
title: 將控制項繫結至 Visual Studio 中的資料 |Microsoft Docs
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
- data, displaying
- data sources, displaying data
- Data Sources window
- dislaying data
ms.assetid: be8b6623-86a6-493e-ab7a-050de4661fd6
caps.latest.revision: 42
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3a4143777e51a03867e94f1d4ebdd9c8182a5401
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49291568"
---
# <a name="bind-controls-to-data-in-visual-studio"></a>將控制項繫結至 Visual Studio 中的資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
您可以透過將資料繫結至控制項，對應用程式的使用者顯示資料。 您可以建立這些資料繫結控制項項目從**Zdroje dat**視窗拖曳到設計介面或在 Visual Studio 中的介面上的控制項。  
  
 這個主題描述可用來建立資料繫結控制項的資料來源。 此外，也描述與資料繫結相關的一些一般工作。 如需如何建立資料繫結控制項更具體的詳細資訊，請參閱[繫結 Windows Form 控制項加入 Visual Studio 中的資料](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)並[繫結 WPF 控制項新增至 Visual Studio 中的資料](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)。  
  
## <a name="data-sources"></a>資料來源  
 在資料繫結內容中，資料來源代表可繫結至您的使用者介面的記憶體中的資料。 實際上，資料來源可以是 Entity Framework 類別、 資料集、 封裝.NET proxy 物件、 LINQ to SQL 類別，或任何.NET 物件或集合中的服務端點。 某些資料來源可讓您建立資料繫結控制項中的項目**Zdroje dat**  視窗中，而不是其他資料來源。 下表顯示支援的資料來源。  
  
|資料來源|中的拖放支援**Windows Form 設計工具**|中的拖放支援**WPF 設計工具**|中的拖放支援**Silverlight 設計工具**|  
|-----------------|---------------------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------|  
|資料集|是|是|否|  
|實體資料模型|是<sup>1</sup>|是|是|  
|LINQ to SQL 類別|否<sup>2</sup>|否<sup>2</sup>|否<sup>2</sup>|  
|服務 (包括[!INCLUDE[ssAstoria](../includes/ssastoria-md.md)]，WCF 服務和 web 服務)|是|是|是|  
|Object|是|是|是|  
|SharePoint|是|是|是|  
  
 1. 產生模型使用**Entity Data Model**精靈，然後將這些物件拖曳至設計工具。  
  
 2. LINQ to SQL 類別不會出現在**Zdroje dat**視窗。 不過，您可以根據 LINQ to SQL 類別加入新的物件資料來源，然後將這些物件拖曳至設計工具，來建立資料繫結控制項。 如需詳細資訊，請參閱 <<c0> [ 逐步解說： 建立的 LINQ to SQL 類別 （O-R 設計工具）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)。  
  
## <a name="data-sources-window"></a>資料來源視窗  
 資料來源中的項目可供您的專案**Zdroje dat**視窗。 此視窗是可見的或可從**檢視**功能表上，當表單的設計介面是在您的專案使用中視窗。 您可以從建立控制項繫結至基礎資料，這個視窗拖曳項目，您也可以設定資料來源，以滑鼠右鍵按一下。  
  
 ![資料來源視窗](../data-tools/media/raddata-data-sources-window.png "raddata 資料來源 視窗")  
  
 會出現在每種資料類型**Zdroje dat**  視窗中，預設會建立控制項時，您將項目拖曳至設計工具。 拖曳的項目之前**Zdroje dat**  視窗中，您可以變更將建立的控制項。 如需詳細資訊，請參閱 <<c0> [ 設定要從資料來源視窗拖曳時要建立的控制項](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)。  
  
## <a name="tasks-involved-in-binding-controls-to-data"></a>控制項繫結至資料相關的工作  
 下表列出一些最常見的工作，您執行將控制項繫結至資料。  
  
|工作|詳細資訊|  
|----------|----------------------|  
|開啟**Zdroje dat**視窗。|在編輯器中開啟的設計介面，然後選擇**檢視** > **Zdroje dat**。|  
|將資料來源新增至您的專案。|[新增資料來源](../data-tools/add-new-data-sources.md)|  
|設定當您拖曳的項目時建立的控制項**Zdroje dat**至設計工具 視窗。|[設定從資料來源視窗拖曳時要建立的控制項](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)|  
|修改清單中的項目相關聯的控制項**Zdroje dat**視窗。|[將自訂控制項新增至資料來源視窗](../data-tools/add-custom-controls-to-the-data-sources-window.md)|  
|建立資料繫結控制項。|[將 Windows Forms 控制項繫結至 Visual Studio 中的資料](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)<br /><br /> [將 WPF 控制項繫結至 Visual Studio 中的資料](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)|  
|繫結至物件或集合。|[Visual Studio 中的物件繫結](../data-tools/bind-objects-in-visual-studio.md)|  
|篩選 UI 中顯示的資料。|[在 Windows Forms 應用程式中篩選和排序資料](../data-tools/filter-and-sort-data-in-a-windows-forms-application.md)|  
|自訂控制項的標題。|[自訂 Visual Studio 為資料繫結的控制項建立標題的方式](../data-tools/customize-how-visual-studio-creates-captions-for-data-bound-controls.md)|  
  
## <a name="see-also"></a>另請參閱  
 [適用於 .NET 的 Visual Studio Data Tools](../data-tools/visual-studio-data-tools-for-dotnet.md)   
 [Windows Forms 資料繫結](http://msdn.microsoft.com/library/c3826d8e-ea25-4ad4-a669-45bfb19192aa)

