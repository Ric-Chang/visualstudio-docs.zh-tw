---
title: IDiaDataSource |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 837372903dd1435c9cc5603805a85ce608481fc9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 01/02/2019
ms.locfileid: "53904253"
---
# <a name="idiadatasource"></a>IDiaDataSource
起始的存取權的偵錯符號的來源。  
  
## <a name="syntax"></a>語法  
  
```  
IDiaDataSource : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 下表顯示的方法`IDiaDataSource`。  
  
|方法|說明|  
|------------|-----------------|  
|[IDiaDataSource::get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|擷取最後一個載入錯誤的檔案名稱。|  
|[IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|隨即開啟，並準備做為偵錯資料來源的程式資料庫 (.pdb) 檔。|  
|[IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|會開啟，並驗證程式資料庫 (.pdb) 檔案符合簽章資訊提供;準備的.pdb 檔做為偵錯資料來源。|  
|[IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|隨即開啟，並準備.exe/.dll 檔案相關聯的偵錯資料。|  
|[IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|準備透過記憶體中資料流存取程式資料庫 (.pdb) 檔案中儲存的偵錯資料。|  
|[IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|開啟查詢符號的工作階段。|  
  
## <a name="remarks"></a>備註  
 其中一個 load 方法的呼叫`IDiaDataSource`介面開啟符號來源。 在成功呼叫[idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)方法會傳回[IDiaSession](../../debugger/debug-interface-access/idiasession.md)支援查詢資料來源的介面。 如果 load 方法傳回的檔案相關的錯誤則[idiadatasource:: Get_lasterror](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)方法傳回值，包含與錯誤相關聯的檔案名稱。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 這個介面由呼叫`CoCreateInstance`函式的類別識別項`CLSID_DiaSource`而介面 ID 的`IID_IDiaDataSource`。 此範例會示範如何取得這個介面。  
  
## <a name="example"></a>範例  
  
```C++  
  
      IDiaDataSource* pSource;  
HRESULT hr = CoCreateInstance(CLSID_DiaSource,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaDataSource,  
                              (void**) &pSource);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>需求  
 標頭：dia2.h  
  
 程式庫： diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>請參閱  
 [介面 (偵錯介面存取 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)