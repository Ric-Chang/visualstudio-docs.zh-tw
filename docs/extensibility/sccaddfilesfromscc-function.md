---
title: SccAddFilesFromSCC 函式 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccAddFilesFromSCC
helpviewer_keywords:
- SccAddFilesFromSCC function
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e3837ea9773d9deba089da2f7d9ef2541fdc3c31
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55026928"
---
# <a name="sccaddfilesfromscc-function"></a>SccAddFilesFromSCC 函式
此函式會將一份檔案從原始檔控制加入至目前開啟的專案。  
  
## <a name="syntax"></a>語法  
  
```cpp  
SCCRTN SccAddFilesFromSCC(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LPSTR   lpUser,  
   LPSTR   lpAuxProjPath,  
   LONG    cFiles,  
   LPCSTR* lpFilePaths,  
   LPCSTR  lpDestination,  
   LPCSTR  lpComment,  
   LPBOOL  pbResults  
);  
```  
  
### <a name="parameters"></a>參數  
 pContext  
 [in]原始檔控制外掛程式的內容指標。  
  
 hWnd  
 [in]原始檔控制外掛程式時，可以使用當做父代上，它會提供任何對話方塊 IDE 視窗的控制代碼。  
  
 lpUser  
 [in、 out]（最多 SCC_USER_SIZE，包括 null 結束字元) 使用者名稱。  
  
 lpAuxProjPath  
 [in、 out]識別專案的輔助字串 (最多`SCC_PRJPATH_`大小，包括 null 結束字元)。  
  
 cFiles  
 [in]所指定的檔案數目`lpFilePaths`。  
  
 lpFilePaths  
 [in、 out]將加入至目前專案的檔案名稱的陣列。  
  
 lpDestination  
 [in]其中的檔案已寫入目的地路徑。  
  
 lpComment  
 [in]要套用至每個檔案要加入的註解。  
  
 pbResults  
 [in、 out]設定為表示作業成功 （非零值或 TRUE） 或失敗的旗標的陣列 （「 零 」 或 「 FALSE 」） 針對每個檔案 (陣列的大小必須至少是`cFiles`長)。  
  
## <a name="return-value"></a>傳回值  
 此函式的原始檔控制外掛程式實作應該會傳回下列值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_E_PROJNOTOPEN|無法開啟專案。|  
|SCC_E_OPNOTPERFORMED|不連接到與所指定相同的專案 `lpAuxProjPath.`|  
|SCC_E_NOTAUTHORIZED|使用者未獲授權可更新資料庫。|  
|SCC_E_NONSPECIFICERROR|未知的錯誤。|  
|SCC_I_RELOADFILE|必須重新載入檔案或專案。|  
  
## <a name="see-also"></a>另請參閱  
 [原始檔控制外掛程式 API 函式](../extensibility/source-control-plug-in-api-functions.md)