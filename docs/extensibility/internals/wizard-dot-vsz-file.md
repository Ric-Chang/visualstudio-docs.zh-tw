---
title: 精靈 (。在 Vsz) 檔案 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .vsz files
- vsz files
- wizards, files
ms.assetid: 72e1d0f3-eef1-455e-b803-96827f030f50
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b1bd68e9d647f9a44eaa8b975995f2d7de3d9640
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013983"
---
# <a name="wizard-vsz-file"></a>精靈檔 (.Vsz)

整合式的開發環境 (IDE) 使用.vsz 檔案以啟動精靈。 這些.vsz 檔案包含 IDE 用來判斷要呼叫哪一個精靈的資訊和要傳遞給精靈的資訊。

.Vsz 檔案是沒有區段.ini 格式的文字檔案的版本。 Ide 的已知的資訊會儲存在檔案開頭。 這會提供 IDE 呼叫 「 精靈 」 與所要傳遞至 IDE.vsz 檔案中的參數之間的連結。 檔案的其餘部分會提供特定的精靈和，要收集的 IDE，而傳遞至特定的精靈參數。

下列範例顯示.vsz 檔案的內容。

```
VSWizard 8.0
Wizard=VsWizard.CBlankSiteWizard -or- {123-1234556-123334}
Param="WIZARDNAME = Wizard One"
Param="WIZARDUI = FALSE"
```

以下是.vsz 檔案中的組件。

|組件|描述|
|----------|-----------------|
|VSWizard|在檔案中的第一個參數是範本的檔案格式的版本號碼。 6.0、 7.0、 7.1 或 8.0，必須是此版本號碼。 其他數字無法啟動，而且會導致不正確的格式錯誤。|
|精靈|此欄位會包含 OLE ProgID 的精靈中，或者 cocreated ide 在精靈的 CLSID 的 GUID 字串表示。|
|參數|這些組件是選擇性的。 您可以新增所需數目。|

參數可讓將額外的自訂參數傳遞給精靈.vsz 檔案。 每個值被當做 variant 的陣列中的字串項目精靈。 如需詳細資訊，請參閱 <<c0> [ 自訂參數](../../extensibility/internals/custom-parameters.md)。

若要加入.vsz 檔案中的預設地區設定識別碼，請指定`FALLBACK_LCID`= 的 xxxx，其中 xxxx 會是地區設定識別碼，例如，1033，代表英文。 當`FALLBACK_LCID`參數定義中，精靈會使用提供的後援地區設定識別碼，如果找不到目前的識別碼。

## <a name="see-also"></a>另請參閱

- [自訂參數](../../extensibility/internals/custom-parameters.md)
- [精靈](../../extensibility/internals/wizards.md)
- [範本目錄描述檔 (.Vsdir)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)