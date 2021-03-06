---
title: '&lt;組件&gt;項目 （ClickOnce 應用程式） |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce application manifest]
ms.assetid: 51410569-10f9-4c0a-96b5-d39185edbefc
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 44437c0ff78c5f957a0d774530e8911513ba0fd6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49191772"
---
# <a name="ltassemblygt-element-clickonce-application"></a>&lt;組件&gt;項目 （ClickOnce 應用程式）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

應用程式資訊清單最上層項目。  
  
## <a name="syntax"></a>語法  
  
```  
  
      <assembly  
   manifestVersion  
/>  
```  
  
## <a name="elements-and-attributes"></a>項目和屬性  
 `assembly`元素是根項目，且需要。 必須是其第一個包含的項目`assemblyIdentity`項目。 資訊清單的項目必須位於下列命名空間的其中一個：  
  
 `urn:schemas-microsoft-com:asm.v1`  
  
 `urn:schemas-microsoft-com:asm.v2`  
  
 `http://www.w3.org/2000/09/xmldsig#`  
  
 組件的子項目也必須是這些命名空間，繼承或標記。  
  
 `assembly` 項目具有下列屬性。  
  
|屬性|描述|  
|---------------|-----------------|  
|`manifestVersion`|必要。 `manifestVersion`屬性必須設為`1.0`。|  
  
## <a name="example"></a>範例  
 下列程式碼範例說明`assembly`的應用程式資訊清單中的項目[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]應用程式。 此程式碼範例是中提供之較大範例的一部分[Ndptecclick](../deployment/clickonce-application-manifest.md)。  
  
```  
<asmv1:assembly   
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"   
  manifestVersion="1.0"   
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">  
```  
  
## <a name="see-also"></a>另請參閱  
 [ClickOnce 應用程式資訊清單](../deployment/clickonce-application-manifest.md)   
 [\<組件 > 項目](../deployment/assembly-element-clickonce-deployment.md)



