---
date: 2026-07-18
description: 了解如何使用 Aspose.Zip for .NET 建立受密碼保護的 zip 檔案、為 zip 資料夾設定密碼保護，以及變更 zip 密碼。
keywords:
- create password protected zip
- zip folder with password
- how to encrypt zip
- password protect zip folder
- encrypt zip archive c#
lastmod: 2026-07-18
linktitle: 目錄密碼保護
og_description: 使用 Aspose.Zip 為 .NET 目錄建立受密碼保護的 zip 壓縮檔。本分步教學示範如何加密資料夾、變更密碼，以及運用 AES
  加密。
og_image_alt: 'Developer guide: Create password protected zip for .NET directories
  with Aspose.Zip'
og_title: 建立受密碼保護的 zip – Aspose.Zip .NET 指南
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to create password protected zip files, password protect
    zip folder, and change zip password using Aspose.Zip for .NET.
  headline: Create password protected zip for .NET directories – Aspose.Zip Tutorial
  type: TechArticle
- questions:
  - answer: Use `TraditionalEncryptionSettings` when creating the `Archive` object,
      then call `CreateEntries` on the target folder.
    question: How do I encrypt a folder with zip using Aspose.Zip?
  - answer: No, the password must be defined at creation time; to change it, recreate
      the archive with a new password.
    question: Can I set a zip folder password after the archive is created?
  - answer: '`AesEncryptionSettings` configures AES‑256 encryption for a ZIP archive.
      Yes, you can switch to `AesEncryptionSettings` for AES‑256 encryption instead
      of the traditional ZipCrypto.'
    question: Does Aspose.Zip support AES encryption for stronger security?
  - answer: Absolutely – the current release works with all modern .NET runtimes.
    question: Is the library compatible with .NET 6 and .NET 7?
  - answer: Aspose.Zip will throw a `PasswordRequiredException`, prompting you to
      supply the correct password.
    question: What happens if I try to open a password‑protected zip without a password?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip encryption
- Aspose.Zip
- .NET compression
- password protected archive
title: 為 .NET 目錄建立受密碼保護的 zip – Aspose.Zip 教學
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 為 .NET 目錄建立受密碼保護的 zip – Aspose.Zip 教程

在本教學中，您將 **建立受密碼保護的 zip** 壓縮檔，將整個目錄使用 Aspose.Zip 函式庫（.NET 版）進行加密。無論是 **加密資料夾**、保護備份檔案，或是僅限制對敏感資料的存取，本步驟指南都會示範如何以乾淨的 C# 程式碼完成。完成後，您將了解如何保護目錄、切換加密模式，以及在現有壓縮檔上變更密碼。

## 快速答案
- **推薦的函式庫是什麼？** Aspose.Zip for .NET  
- **可以加密整個資料夾嗎？** 可以，只要將 API 指向您想壓縮的資料夾即可。  
- **支援變更 zip 密碼嗎？** 當然，使用 `TraditionalEncryptionSettings`。  
- **商業環境需要授權嗎？** 需要有效的 Aspose.Zip 授權才能在生產環境使用。  
- **支援 .NET Core/5/6 嗎？** 支援，API 完全相容於現代 .NET 執行環境。  

## 什麼是「建立受密碼保護的 zip」？

建立受密碼保護的 zip 意指將檔案或目錄壓縮成 ZIP 壓縮檔，同時套用加密，使得只有輸入正確密碼才能開啟。此方式可防止未授權存取，並符合多項資料保護法規的要求。

## 如何為目錄建立受密碼保護的 zip

載入目標資料夾、使用 `TraditionalEncryptionSettings` 設定密碼，然後將資料串流至新 ZIP 檔——只需幾行簡潔程式碼。API 會直接將每個項目寫入輸出串流，即使是多 GB 的目錄也能以最小記憶體開銷處理。

## 為何在 .NET 使用 Aspose.Zip 來保護目錄？

Aspose.Zip 支援 **30 多種壓縮與加密演算法**，可處理超過 **10 GB** 的資料夾而不需將整個壓縮檔載入記憶體，並提供傳統 ZipCrypto 與現代 AES‑256 加密。函式庫完全執行緒安全，支援 **.NET Framework 4.6+**、**.NET Core 3.1+** 與 **.NET 6/7**，且內建詳細日誌，協助您快速排除問題。

## 常見使用情境
- **備份保護：** 將每日備份資料夾壓縮並以強密碼鎖定。  
- **安全檔案交換：** 將 zip 資料夾的密碼傳給客戶，避免內容外洩。  
- **法規遵循：** 將個人可識別資訊 (PII) 存放於加密 zip 壓縮檔，以符合資料保護標準。  

## 先決條件
在開始之前，請確保您已具備：

- 基本的 C# 程式設計知識。  
- Visual Studio（任何近期版本）。  
- Aspose.Zip for .NET 函式庫 – 前往 **[此處](https://releases.aspose.com/zip/net/)** 下載。  
- 一個欲以密碼保護的磁碟資料夾。

## 匯入命名空間
在 C# 檔案中加入必要的命名空間，讓編譯器能找到 Aspose.Zip 類別。

## 步驟 1：設定資源目錄路徑
定義指向您要壓縮並保護的目錄之路徑。

## 步驟 2：為目錄設定密碼保護
`TraditionalEncryptionSettings` 定義 ZIP 壓縮檔的密碼與加密演算法。  
在建立 `Archive` 實例時使用此設定物件，即可套用 ZipCrypto 保護。

## 步驟 3：程式碼說明
`Archive` 代表一個 ZIP 壓縮檔，提供加入項目與儲存壓縮檔的方法。

- **建立輸出檔案：** `File.Open(..., FileMode.Create)` 會開啟（或建立）用來存放加密資料的 ZIP 檔。  
- **選取來源資料夾：** `new DirectoryInfo(".\\CanterburyCorpus")` 告訴 Aspose.Zip 要壓縮哪個目錄。  
- **套用密碼：** `new TraditionalEncryptionSettings("p@s$")` 設定保護壓縮檔的密碼。  
- **加入項目並儲存：** `archive.CreateEntries(corpus)` 會將資料夾內的每個檔案加入，`archive.Save(zipFile)` 則將加密後的 ZIP 寫入磁碟。  

## 如何稍後變更 zip 密碼？

若要變更密碼，必須重新建立壓縮檔，因為密碼儲存在中央目錄標頭中。建立一個新的 `TraditionalEncryptionSettings`（使用新密碼），開啟現有壓縮檔，將其項目複製到使用新設定的 `Archive` 實例，最後儲存新壓縮檔。此流程會以新密碼重新加密所有項目。

## 強密碼的提示
- 結合大寫、小寫、數字與符號。  
- 至少 12 個字元；密碼越長破解難度呈指數級提升。  
- 避免使用常見詞彙或模式；可考慮使用密語 (passphrase)。  

## 常見問題與提示
- **大型資料夾：** Aspose.Zip 以串流方式處理資料，即使是 5 GB 的目錄，記憶體使用量仍低於 **150 MB**。  
- **密碼複雜度：** 使用混合字母、數字與符號的強密碼，以提升安全性。  
- **授權錯誤：** 確認已套用有效的授權檔；否則函式庫會以評估模式執行，功能受限。  
- **zip 資料夾密碼無法辨識：** 開啟壓縮檔時，請確保使用相同的加密方法（`TraditionalEncryptionSettings`）。  

## 常見問與答

### Aspose.Zip for .NET 是否適用於大型目錄？
是，Aspose.Zip for .NET 專為有效處理大型目錄而設計，提供最佳效能。

### 我可以變更已受保護目錄的密碼嗎？
可以，透過在程式碼中調整 `TraditionalEncryptionSettings` 即可修改密碼。

### 使用 Aspose.Zip for .NET 有授權需求嗎？
有，需要有效的授權才能在生產環境中使用 Aspose.Zip for .NET。您可在 **[此處](https://purchase.aspose.com/buy)** 取得授權。

### 有免費試用版嗎？
有，您可在 **[此處](https://releases.aspose.com/)** 取得免費試用版。

### 哪裡可以取得 Aspose.Zip for .NET 的其他支援？
您可以前往 **[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)** 取得支援或提問。

## 快速問答（AI 友好）

**Q: 如何使用 Aspose.Zip 加密資料夾？**  
A: 在建立 `Archive` 物件時使用 `TraditionalEncryptionSettings`，然後對目標資料夾呼叫 `CreateEntries`。

**Q: 可以在壓縮檔建立後再設定 zip 資料夾密碼嗎？**  
A: 不行，密碼必須在建立時指定；若要變更密碼，需重新建立壓縮檔並使用新密碼。

**Q: Aspose.Zip 是否支援 AES 加密以提升安全性？**  
A: `AesEncryptionSettings` 可設定 AES‑256 加密。是的，您可以改用 `AesEncryptionSettings` 以取代傳統的 ZipCrypto。

**Q: 此函式庫相容於 .NET 6 與 .NET 7 嗎？**  
A: 完全相容，最新版本支援所有現代 .NET 執行環境。

**Q: 若未提供密碼就嘗試開啟受密碼保護的 zip 會發生什麼？**  
A: Aspose.Zip 會拋出 `PasswordRequiredException`，要求提供正確的密碼。

---

**Last Updated:** 2026-07-18  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

```csharp
string dataDir = "Your Document Directory";
```

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

## 相關教學

- [Create Password Protected ZIP with Aspose.Zip for .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Create Password Protected ZIP Files with AES Encryption using Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Aspose.Zip for .NET - Password Protect Zip Archive & Store Multiple Files Without Compression](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}