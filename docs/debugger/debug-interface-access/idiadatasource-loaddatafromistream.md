---
title: 'Idiadatasource:: Loaddatafromistream |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromIStream method
ms.assetid: 8fe33eea-1457-4b8c-ae19-f1ede5578483
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0af18b58ed509d2fc5f0b962b9a94ce7bdc1b820
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031392"
---
# <a name="idiadatasourceloaddatafromistream"></a>IDiaDataSource::loadDataFromIStream
準備透過記憶體中資料流存取程式資料庫 (.pdb) 檔案中儲存的偵錯資料。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT loadDataFromIStream (   
   IStream* pIStream  
);  
```  
  
#### <a name="parameters"></a>參數  
 pIStream  
 [in]<xref:IStream>物件，表示要使用的資料流。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。 下表顯示可能的傳回值，這個方法。  
  
|值|說明|  
|-----------|-----------------|  
|E_PDB_FORMAT|嘗試存取已過時的格式的檔案。|  
|E_INVALIDARG|無效的參數。|  
|E_UNEXPECTED|資料來源已準備好了。|  
  
## <a name="remarks"></a>備註  
 這個方法可讓以取得從透過的記憶體可執行檔的偵錯資料<xref:IStream>物件。  
  
 若要載入的.pdb 檔不需要驗證，使用[idiadatasource:: Loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)方法。  
  
 若要驗證對特定準則的.pdb 檔，請使用[idiadatasource:: Loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)方法。  
  
 若要存取的資料載入程序 （透過回呼的機制），請使用[idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)方法。  
  
## <a name="see-also"></a>請參閱  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)