---
title: HOW TO：以程式設計方式在搜尋後還原選取範圍
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- searches, restoring selection after
- documents [Office development in Visual Studio], restoring selections
- selections, restoring after a search
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 684c373204c5cfadd3cfcd705993aaa7a40bce5f
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875204"
---
# <a name="how-to-programmatically-restore-selections-after-searches"></a>HOW TO：以程式設計方式在搜尋後還原選取範圍
  如果您尋找和取代文件中，您可能想要搜尋完成後，還原使用者的原始選取項目。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 此範例程序中的程式碼會使用兩個<xref:Microsoft.Office.Interop.Word.Range>物件。 其中一個存放區目前<xref:Microsoft.Office.Interop.Word.Selection>，和其中一位將整份文件来做的搜尋範圍。  
  
## <a name="to-restore-the-users-original-selection-after-a-search"></a>若要還原使用者的搜尋之後的原始選取項目  
  
1. 建立<xref:Microsoft.Office.Interop.Word.Range>文件和目前的選取範圍的物件。  
  
    [!code-vb[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#83)]
    [!code-csharp[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#83)]  
  
2. 執行搜尋和取代作業。  
  
    [!code-vb[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#84)]
    [!code-csharp[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#84)]  
  
3. 選取 還原使用者的原始選取項目開始範圍。  
  
    [!code-vb[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#85)]
    [!code-csharp[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#85)]  
  
   下列範例示範完整的方法：  
  
## <a name="example"></a>範例  
 [!code-vb[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#82)]
 [!code-csharp[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#82)]  
  
## <a name="see-also"></a>另請參閱  
 [如何：以程式設計方式搜尋和取代文件中的文字](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [如何：以程式設計方式在 Word 中設定搜尋選項](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [如何：以程式設計方式在文件中找到項目執行迴圈](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Office 方案中的選擇性參數](../vsto/optional-parameters-in-office-solutions.md)  
