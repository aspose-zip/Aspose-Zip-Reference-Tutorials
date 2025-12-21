---
date: 2025-12-21
description: 學習如何在 .NET 中建立受密碼保護的 ZIP 檔案、加密資料夾，以及使用 Aspose.Zip 更改 ZIP 密碼。
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 為 .NET 目錄建立受密碼保護的 zip – Aspose.Zip 教程
url: /zh-hant/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 為 .NET 目錄建立受密碼保護的 zip – Aspose.Zip 教程

在本指南中，您將使用 Aspose.Zip .NET 函式庫 **建立受密碼保護的 zip** 壓縮檔案，針對整個目錄。無論您需要 **加密資料夾**、保護備份檔案，或僅僅限制對敏感資料的存取，此步驟教學將示範如何以乾淨的 C# 程式碼完成。

## 快速解答
- **建議使用哪個函式庫？** Aspose.Zip for .NET  
- **我可以加密整個資料夾嗎？** Yes – just point the API at the folder you want to zip.  
- **支援變更 zip 密碼嗎？** Absolutely, use `TraditionalEncryptionSettings`.  
- **在正式環境需要授權嗎？** A valid Aspose.Zip license is required for commercial use.  
- **支援 .NET Core/5/6 嗎？** Yes, the API is fully compatible with modern .NET runtimes.  

## 什麼是「建立受密碼保護的 zip」？
建立受密碼保護的 zip 意指將檔案或目錄壓縮成 ZIP 壓縮檔，同時套用加密，使得只有使用正確密碼才能開啟該壓縮檔。此舉可防止未授權的存取。

## 為什麼在 .NET 中使用 Aspose.Zip 來對目錄進行密碼保護？
Aspose.Zip 提供簡潔且高效能的 API，支援 **c# zip password protection**、傳統 ZipCrypto 加密以及 AES 加密。它能有效處理大型目錄，且可無縫整合至任何 .NET 專案。

## 先決條件
- 具備 C# 程式設計的基本知識。  
- Visual Studio（任一較新版）。  
- Aspose.Zip for .NET 函式庫 – 前往 **[此處](https://releases.aspose.com/zip/net/)** 下載。  
- 一個您想以密碼保護的磁碟資料夾。  

## 匯入命名空間
在您的 C# 檔案中加入必要的命名空間，讓編譯器能找到 Aspose.Zip 類別。

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 步驟 1：設定資源目錄的路徑
定義指向您欲壓縮並保護的目錄之路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：對目錄設定密碼保護
使用 `TraditionalEncryptionSettings` 來指定密碼並建立加密壓縮檔。這即是 **c# zip password protection** 的核心。

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## 步驟 3：程式碼說明
- **Creating the output file:** `File.Open(..., FileMode.Create)` 開啟（或建立）將保存加密資料的 ZIP 檔案。  
- **Selecting the source folder:** `new DirectoryInfo(".\\CanterburyCorpus")` 告訴 Aspose.Zip 要壓縮哪個目錄。  
- **Applying the password:** `new TraditionalEncryptionSettings("p@s$")` 設定用於保護壓縮檔的密碼。  
- **Adding entries & saving:** `archive.CreateEntries(corpus)` 會將資料夾中的每個檔案加入，`archive.Save(zipFile)` 則將加密的 ZIP 寫入磁碟。  

## 如何之後變更 zip 密碼？
如果您需要 **change zip password**，只要使用包含新密碼的 `TraditionalEncryptionSettings` 重新建立壓縮檔，然後再次儲存即可。

## 常見問題與技巧
- **Large folders:** Aspose.Zip 以串流方式處理資料，即使是巨大的目錄，記憶體使用量仍保持低。  
- **Password complexity:** 使用強密碼（混合字母、數字、符號）以提升安全性。  
- **License errors:** 確認已套用有效的授權檔案；否則函式庫將以評估模式執行，且有功能限制。  

## 常見問答

### Aspose.Zip for .NET 是否適用於大型目錄？
是的，Aspose.Zip for .NET 專為有效處理大型目錄而設計，提供最佳效能。

### 我可以變更已受保護目錄的密碼嗎？
可以，您只需在程式碼中調整 `TraditionalEncryptionSettings` 即可修改密碼。

### 使用 Aspose.Zip for .NET 有任何授權需求嗎？
是的，於正式環境使用 Aspose.Zip for .NET 必須擁有有效授權。您可在 **[此處](https://purchase.aspose.com/buy)** 取得授權。

### 是否提供 Aspose.Zip for .NET 的免費試用？
是的，您可在 **[此處](https://releases.aspose.com/)** 取得免費試用。

### 在哪裡可以找到 Aspose.Zip for .NET 的其他支援？
您可前往 **[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)** 取得支援或諮詢。

---

**最後更新時間：** 2025-12-21  
**測試環境：** Aspose.Zip for .NET (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}