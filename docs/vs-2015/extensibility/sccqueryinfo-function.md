---
title: SccQueryInfo 函式 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccQueryInfo
helpviewer_keywords:
- SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a7093f712ab520502e36094ec571c0ee1a3ded18
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51785075"
---
# <a name="sccqueryinfo-function"></a>SccQueryInfo 函式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

此函式會取得一組選取的檔案，在 原始檔控制下的狀態資訊。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
SCCRTN SccQueryInfo(  
   LPVOID  pvContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>參數  
 pvContext  
 [in]原始檔控制外掛程式的內容結構。  
  
 nFiles  
 [in]中指定的檔案數目`lpFileNames`陣列和長度`lpStatus`陣列。  
  
 lpFileNames  
 [in]要查詢的檔案名稱的陣列。  
  
 lpStatus  
 [in、 out]陣列，其中的原始檔控制外掛程式傳回每個檔案的狀態旗標。 如需詳細資訊，請參閱 <<c0> [ 檔案狀態碼](../extensibility/file-status-code-enumerator.md)。  
  
## <a name="return-value"></a>傳回值  
 此函式的原始檔控制外掛程式實作應該會傳回下列值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|查詢成功。|  
|SCC_E_ACCESSFAILURE|發生問題，以存取原始檔控制系統，可能因網路或競爭問題。 建議使用重試。|  
|SCC_E_PROJNOTOPEN|無法開啟原始檔控制下的專案。|  
|SCC_E_NONSPECIFICERROR|不明確的失敗。|  
  
## <a name="remarks"></a>備註  
 如果`lpFileName`為空字串，目前沒有要更新的狀態資訊。 否則，它是可能的狀態資訊已變更之檔案的完整路徑名稱。  
  
 傳回陣列可以是位元遮罩`SCC_STATUS_xxxx`位元。 如需詳細資訊，請參閱 <<c0> [ 檔案狀態碼](../extensibility/file-status-code-enumerator.md)。 原始檔控制系統可能不支援所有的位元類型。 例如，如果`SCC_STATUS_OUTOFDATE`不提供，只是無法設定位元。  
  
 當使用此函式簽出檔案，請注意下列`MSSCCI`狀態需求：  
  
-   `SCC_STATUS_OUTBYUSER` 目前的使用者已簽出檔案時設定。  
  
-   `SCC_STATUS_CHECKEDOUT` 無法設定，除非`SCC_STATUS_OUTBYUSER`設定。  
  
-   `SCC_STATUS_CHECKEDOUT` 時才會設定檔案已簽出到指定的工作目錄。  
  
-   如果檔案已簽出目前的使用者以外的工作目錄的目錄`SCC_STATUS_OUTBYUSER`設定，但`SCC_STATUS_CHECKEDOUT`不是。  
  
## <a name="see-also"></a>另請參閱  
 [原始檔控制外掛程式 API 函式](../extensibility/source-control-plug-in-api-functions.md)   
 [檔案狀態碼](../extensibility/file-status-code-enumerator.md)

