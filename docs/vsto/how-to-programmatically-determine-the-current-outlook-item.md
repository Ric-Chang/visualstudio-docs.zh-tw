---
title: HOW TO：以程式設計方式判斷目前的 Outlook 項目
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e72928c6244ba15a96bdedd7aba6b59c1e50e708
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875091"
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>HOW TO：以程式設計方式判斷目前的 Outlook 項目
  這個範例會使用`Explorer.SelectionChange`事件，以顯示目前的資料夾，然後選取的項目的一些資訊的名稱。 程式碼接著會顯示選取的項目。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>範例  
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]  
  
## <a name="compile-the-code"></a>編譯程式碼  
 這個範例需要：  
  
-   約會、 連絡人及電子郵件在 Microsoft Office Outlook 中的項目。  
  
## <a name="see-also"></a>另請參閱  
 [Outlook 物件模型概觀](../vsto/outlook-object-model-overview.md)   
 [如何：以程式設計方式依名稱擷取資料夾](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [如何：以程式設計方式搜尋特定的連絡人](../vsto/how-to-programmatically-search-for-a-specific-contact.md)  
