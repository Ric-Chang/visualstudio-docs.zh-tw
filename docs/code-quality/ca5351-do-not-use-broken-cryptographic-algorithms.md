---
title: CA5351 不要使用中斷的密碼編譯演算法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: 483f51b3-e186-4433-b48e-5ca24a9a9c94
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab965c8912144350c527517b79de2914e238976e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037712"
---
# <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351 不要使用中斷的密碼編譯演算法

|||
|-|-|
|TypeName|DoNotUseBrokenCryptographicAlgorithms|
|CheckId|CA5351|
|分類|Microsoft.Cryptography|
|中斷變更|非中斷|

> [!NOTE]
> 上次於 2015 年 11 月更新此警告。

## <a name="cause"></a>原因

雜湊函式 (例如 <xref:System.Security.Cryptography.MD5> ) 和加密演算法 (例如 <xref:System.Security.Cryptography.DES> 和 <xref:System.Security.Cryptography.RC2> ) 可以公開重大風險，而且可能會透過一般攻擊技巧 (例如暴力攻擊和雜湊衝突) 而導致公開機密資訊。

下列密碼編譯演算法清單是針對已知的密碼編譯攻擊。 密碼編譯雜湊演算法 <xref:System.Security.Cryptography.MD5> 是針對雜湊衝突攻擊。  根據使用方式，雜湊衝突可能會導致系統上的模擬、竄改或其他類型的攻擊，而系統依賴雜湊函式的唯一密碼編譯輸出。 加密演算法 <xref:System.Security.Cryptography.DES> 和 <xref:System.Security.Cryptography.RC2> 是針對可能會導致非預期加密資料外洩的密碼編譯攻擊。

## <a name="rule-description"></a>規則描述

中斷的密碼編譯演算法較不安全，建議您不要使用它們。 MD5 雜湊演算法容易受到已知的衝突攻擊，但是特定的弱點會因使用的內容而不同。  用來確保資料完整性 （例如，檔案簽章或數位憑證） 的雜湊演算法是特別容易受到攻擊。  在這種情況下，攻擊者可能會產生兩個不同的資料部分，讓良性資料可以取代為惡意資料，而不會變更雜湊值，或讓相關聯的數位簽章失效。

針對加密演算法：

- <xref:System.Security.Cryptography.DES> 加密包含小型的金鑰大小，這可能是少於一天的暴力攻擊。

- <xref:System.Security.Cryptography.RC2> 加密容易受到相關金鑰攻擊，其中，攻擊者會找出所有金鑰值之間的數學關係。

如果在原始程式碼中找到任何上述的密碼編譯函式，並將警告擲回給使用者，則會觸發這個規則。

## <a name="how-to-fix-violations"></a>如何修正違規

使用密碼編譯較強的選項：

- 針對 MD5，使用雜湊[sha-2](/windows/desktop/SecCrypto/hash-and-signature-algorithms)系列 (例如<xref:System.Security.Cryptography.SHA512>， <xref:System.Security.Cryptography.SHA384>， <xref:System.Security.Cryptography.SHA256>)。

- 針對 DES 和 RC2，使用 <xref:System.Security.Cryptography.Aes> 加密。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機

請不要隱藏這個規則的警告，除非密碼編譯專家已檢閱過它。

## <a name="pseudo-code-examples"></a>虛擬程式碼範例

下列虛擬程式碼範例會說明偵測到此規則，並可能替代方案的模式。

### <a name="md5-hashing-violation"></a>MD5 雜湊違規

```csharp
using System.Security.Cryptography;
...
var hashAlg = MD5.Create();
```

解決方案:

```csharp
using System.Security.Cryptography;
...
var hashAlg = SHA256.Create();
```

### <a name="rc2-encryption-violation"></a>RC2 加密違規

```csharp
using System.Security.Cryptography;
...
RC2 encAlg = RC2.Create();
```

解決方案:

```csharp
using System.Security.Cryptography;
...
using (AesManaged encAlg = new AesManaged())
{
  ...
}
```

### <a name="des-encryption-violation"></a>DES 加密違規

```csharp
using System.Security.Cryptography;
...
DES encAlg = DES.Create();
```

解決方案:

```csharp
using System.Security.Cryptography;
...
using (AesManaged encAlg = new AesManaged())
{
  ...
}
```