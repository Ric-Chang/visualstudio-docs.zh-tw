---
title: HOW TO：變更 DataContext 方法的傳回型別 (O-R 設計工具)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 297f4df8c34f7289cb39dfaf2b5d1d9c8c88314e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55004704"
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>HOW TO：變更 DataContext 方法的傳回型別 (O/R 設計工具)
傳回型別<xref:System.Data.Linq.DataContext>（根據預存程序或函式建立） 的方法有所不同卸除預存程序或函式中的地方**O/R Designer**。 如果將項目直接放入現有的實體類別，且預存程序或函式所傳回資料的結構描述符合實體類別的型態，則建立的 <xref:System.Data.Linq.DataContext> 方法會具有該實體類別的傳回型別。 如果您將項目放的空白區域**O/R Designer**、<xref:System.Data.Linq.DataContext>建立方法會傳回自動產生的型別。 您可以在將 <xref:System.Data.Linq.DataContext> 方法加入至方法窗格後，變更方法的傳回型別。 若要檢查或變更 <xref:System.Data.Linq.DataContext> 方法的傳回型別，請選取該方法，然後按一下 [屬性] 視窗中的 [傳回型別] 屬性。

> [!NOTE]
>  您無法使用 [屬性] 視窗，將傳回型別設定為實體類別的 <xref:System.Data.Linq.DataContext> 方法還原成傳回自動產生的型別。 若要將 <xref:System.Data.Linq.DataContext> 方法還原成傳回自動產生的類型，則必須再次將原始資料庫物件拖曳至 **O/R 設計工具**。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>若要將 DataContext 方法的傳回型別從自動產生的型別變更為實體類別

1.  選取方法窗格中的 <xref:System.Data.Linq.DataContext> 方法。

2.  選取 [屬性] 視窗中的 [傳回型別]，然後在 [傳回型別] 清單中選取可用的實體類別。 如果所需的實體類別不在清單中，將它新增至或建立中**O/R Designer**將它新增至清單。

3.  儲存 *.dbml* 檔案。

## <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>若要將 DataContext 方法的傳回型別從實體類別變更為自動產生的型別

1.  選取 [方法] 窗格中的 <xref:System.Data.Linq.DataContext> 方法，並予以刪除。

2.  將資料庫物件從**伺服器總管**或**資料庫總管**上的空白區域**O/R Designer**。

3.  儲存 *.dbml* 檔案。

## <a name="see-also"></a>另請參閱

- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [DataContext 方法 (O/R 設計工具)](../data-tools/datacontext-methods-o-r-designer.md)
- [如何：建立對應至預存程序和函式的 DataContext 方法 (O/R 設計工具)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)