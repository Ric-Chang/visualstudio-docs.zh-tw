---
title: HOW TO：以程式設計方式填入 Word 表格文件屬性
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document properties, inserting in Word tables
- documents [Office development in Visual Studio], document properties
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: cfc5885ffc3c16c937781b991e1d8d83b632bbb6
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2019
ms.locfileid: "54862846"
---
# <a name="how-to-programmatically-populate-word-tables-with-document-properties"></a>HOW TO：以程式設計方式填入 Word 表格文件屬性
  下列範例會在文件的頂端建立 Microsoft Office Word 表格，並用主文件的屬性填入這個表格。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="populate-tables-in-a-document-level-customization"></a>填入文件層級自訂中的資料表  
  
### <a name="to-create-a-table-and-populate-it-with-document-properties"></a>建立表格並且用文件的屬性填入這個表格  
  
1. 將範圍設為文件頂端。  
  
    [!code-vb[Trin_VstcoreWordAutomation#90](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#90)]
    [!code-csharp[Trin_VstcoreWordAutomation#90](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#90)]  
  
2. 插入表格標題並且包含段落標記。  
  
    [!code-vb[Trin_VstcoreWordAutomation#91](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#91)]
    [!code-csharp[Trin_VstcoreWordAutomation#91](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#91)]  
  
3. 在文件的該範圍內加入表格。  
  
    [!code-vb[Trin_VstcoreWordAutomation#92](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#92)]
    [!code-csharp[Trin_VstcoreWordAutomation#92](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#92)]  
  
4. 格式化表格並套用樣式。  
  
    [!code-vb[Trin_VstcoreWordAutomation#93](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#93)]
    [!code-csharp[Trin_VstcoreWordAutomation#93](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#93)]  
  
5. 將文件屬性插入儲存格。  
  
    [!code-vb[Trin_VstcoreWordAutomation#94](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#94)]
    [!code-csharp[Trin_VstcoreWordAutomation#94](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#94)]  
  
   下列範例示範完整的程序。 若要使用此程式碼，請從專案的 `ThisDocument` 類別中執行它。  
  
   [!code-vb[Trin_VstcoreWordAutomation#89](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#89)]
   [!code-csharp[Trin_VstcoreWordAutomation#89](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#89)]  
  
## <a name="populate-tables-in-a-vsto-add-in"></a>在 VSTO 增益集中的資料表中填入  
  
### <a name="to-create-a-table-and-populate-it-with-document-properties"></a>建立表格並且用文件的屬性填入這個表格  
  
1. 將範圍設為文件頂端。  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#90](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#90)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#90](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#90)]  
  
2. 插入表格標題並且包含段落標記。  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#91](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#91)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#91](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#91)]  
  
3. 在文件的該範圍內加入表格。  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#92](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#92)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#92](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#92)]  
  
4. 格式化表格並套用樣式。  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#93](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#93)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#93](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#93)]  
  
5. 將文件屬性插入儲存格。  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#94](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#94)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#94](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#94)]  
  
   下列範例示範完整的程序。 若要使用此程式碼，請從專案的 `ThisAddIn` 類別中執行它。  
  
   [!code-vb[Trin_VstcoreWordAutomationAddIn#89](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#89)]
   [!code-csharp[Trin_VstcoreWordAutomationAddIn#89](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#89)]  
  
## <a name="see-also"></a>另請參閱  
 [如何：以程式設計方式建立 Word 表格](../vsto/how-to-programmatically-create-word-tables.md)   
 [如何：以程式設計方式加入文字和格式在 Word 表格的儲存格](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [如何：以程式設計方式將資料列和資料行加入至 Word 表格](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [Office 方案中的選擇性參數](../vsto/optional-parameters-in-office-solutions.md)  
