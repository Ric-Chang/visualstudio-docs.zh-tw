---
title: METADATA_ADDRESS_RETVAL | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- METADATA_ADDRESS_RETVAL
helpviewer_keywords:
- METADATA_ADDRESS_RETVAL structure
ms.assetid: 5b0ec0fb-84b3-4ce7-8e24-becf3d881d7d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89e10bac9db8782c117e114b02e4ff73a3693518
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55006095"
---
# <a name="metadataaddressretval"></a>METADATA_ADDRESS_RETVAL
此結構表示從方法或函式的傳回值。  
  
## <a name="syntax"></a>語法  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_RETVAL {  
   _mdToken tokMethod;  
   DWORD    dwCorType;  
   DWORD    dwSigSize;  
   BYTE     rgSig[10];  
} METADATA_ADDRESS_RETVAL;  
```  
  
```csharp  
public struct METADATA_ADDRESS_RETVAL {  
   public int    tokMethod;  
   public uint   dwCorType;  
   public uint   dwSigSize;  
   public byte[] rgSig;  
}  
```  
  
## <a name="terms"></a>詞彙  
 tokMethod  
 這個傳回值是針對方法的識別碼。  
  
 dwCorType  
 傳回值的基底型別。 這是介於`CorElementType`列舉型別中定義[!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)]SDK corhdr.h 檔案。  
  
 dwSigSize  
 傳回值的簽章的大小 (儲存在`rgSig`)。  
  
 rgSig  
 建構簽章的傳回值的位元組陣列。  
  
## <a name="remarks"></a>備註  
 此結構是中的等位的一部分[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)結構的時機`dwKind`欄位`DEBUG_ADDRESS_UNION`結構設定為`ADDRESS_KIND_RETVAL`(中的值[ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)列舉型別）。  
  
## <a name="requirements"></a>需求  
 標頭： sh.h  
  
 命名空間:Microsoft.VisualStudio.Debugger.Interop  
  
 組件︰Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [結構和等位](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)