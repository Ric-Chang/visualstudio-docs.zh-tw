---
title: HOW TO：使用活動記錄檔 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b23dd6ffa0e856ef5d5fb14227953cb22dce65e8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929348"
---
# <a name="how-to-use-the-activity-log"></a>HOW TO：使用活動記錄
Vspackage 可以將訊息寫入活動記錄檔。 這項功能是對於在零售環境中偵錯 Vspackage 特別有用。  
  
> [!TIP]
>  永遠開啟活動記錄檔。 Visual Studio 會保留最近 100 個項目，以及具有一般的設定資訊的前 10 個項目一個循環緩衝區。  
  
## <a name="to-write-an-entry-to-the-activity-log"></a>若要將項目寫入活動記錄檔  
  
1.  插入這個程式碼的<xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>方法或任何其他方法，就只是 VSPackage 建構函式：  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     這個程式碼取得<xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog>服務，並將它轉換成<xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>介面。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> 寫入至活動記錄使用目前的文化特性內容的參考項目。  
  
2.  當載入 VSPackage 時 （通常當叫用命令，或在開啟的視窗） 時，活動記錄檔寫入文字。  
  
## <a name="to-examine-the-activity-log"></a>若要查看活動記錄檔  
  
1. 執行使用 Visual Studio [/log](../ide/reference/log-devenv-exe.md) ActivityLog.xml 寫入磁碟，在您的工作階段期間的命令列參數。

2. 之後關閉 Visual Studio，尋找活動記錄檔的子資料夾中的 Visual Studio 的資料：  <em>*%appdata%</em>\Microsoft\VisualStudio\15.0\ActivityLog.xml*。  
  
3. 使用任何文字編輯器中開啟活動記錄檔。 以下是典型的項目：  
  
   ```  
   Called for: Company.MyApp.MyAppPackage ...  
   ```  
  
## <a name="robust-programming"></a>穩固程式設計  
 活動記錄檔是一項服務，因為活動記錄檔是 VSPackage 的建構函式中無法使用。  
  
 您應該取得活動記錄檔之前對其寫入。 不要快取或儲存活動記錄檔，以供日後使用。  
  
## <a name="see-also"></a>另請參閱
 [/Log (devenv.exe)](../ide/reference/log-devenv-exe.md)   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [針對 Vspackage 進行疑難排解](../extensibility/troubleshooting-vspackages.md)   
 [VSPackage](../extensibility/internals/vspackages.md)
