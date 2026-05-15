---
date: 2026-03-08
description: 學習如何使用 Aspose.Zip for .NET 建立受密碼保護的 ZIP 檔案、為 ZIP 資料夾設定密碼，以及變更 ZIP 密碼。
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 為 .NET 目錄建立受密碼保護的 ZIP 檔 – Aspose.Zip 教學
url: /zh-hant/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 為 .NET 目錄建立受密碼保護的 zip – Aspose.Zip 教程

在本指南中，您將使用 Aspose.Zip for .NET 函式庫**建立受密碼保護的 zip**壓縮檔，針對整個目錄。無論您需要**加密資料夾**、保護備份檔案，或僅僅限制對敏感資料的存取，本步驟教學將示範如何以簡潔的 C# 程式碼完成。

## 快速解答
- **建議使用哪個函式庫？** Aspose.Zip for .NET  
- **我可以加密整個資料夾嗎？** Yes – just point the API at the folder you want to zip.  
- **支援變更 zip 密碼嗎？** Absolutely, use `TraditionalEncryptionSettings`.  
- **在正式環境需要授權嗎？** A valid Aspose.Zip license is required for commercial use.  
- **支援 .NET Core/5/6 嗎？** Yes, the API is fully compatible with modern .NET runtimes.  

## 什麼是「建立受密碼保護的 zip」？
建立受密碼保護的 zip 意指將檔案或目錄壓縮成 ZIP 壓縮檔，同時套用加密，使得只有輸入正確密碼才能開啟該壓縮檔。此舉可防止未授權的存取。

## 如何為目錄建立受密碼保護的 zip
以下提供完整且易於閱讀的操作步驟，涵蓋從專案設定到之後變更密碼的全部流程。

## 為何在 .NET 中使用 Aspose.Zip 來保護目錄密碼？
Aspose.Zip 提供直觀且高效能的 API，支援 **c# zip 密碼保護**、傳統 ZipCrypto 加密以及 AES 加密。它能有效處理大型目錄，且可無縫整合至任何 .NET 專案。

## 常見使用情境
- **備份保護：** 將每日備份資料夾壓縮並以強密碼鎖定。  
- **安全檔案交換：** 將 zip 資料夾的密碼傳給客戶，而不洩露內容。  
- **符合法規要求：** 將個人可識別資訊 (PII) 存放於加密的 zip 壓縮檔，以符合資料保護標準。  

## 前置條件
在開始之前，請確保您具備：

- 具備 C# 程式設計的基礎知識。  
- Visual Studio（任意較新版）。  
- Aspose.Zip for .NET 函式庫 – 前往 **[此處](https://releases.aspose.com/zip/net/)** 下載。  
- 磁碟上欲以密碼保護的資料夾。  

## 匯入命名空間
在 C# 檔案中加入必要的命名空間，讓編譯器能找到 Aspose.Zip 類別。

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 步驟 1：設定資源目錄的路徑
定義指向欲壓縮並保護之目錄的路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：為目錄設定密碼保護
使用 `TraditionalEncryptionSettings` 來指定密碼並建立加密壓縮檔。這即是 **c# zip 密碼保護** 的核心。

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
- **建立輸出檔案：** `File.Open(..., FileMode.Create)` 會開啟（或建立）用來存放加密資料的 ZIP 檔案。  
- **選取來源資料夾：** `new DirectoryInfo(".\\CanterburyCorpus")` 告訴 Aspose.Zip 要壓縮哪個目錄。  
- **套用密碼：** `new TraditionalEncryptionSettings("p@s$")` 設定保護壓縮檔的密碼。  
- **加入項目並儲存：** `archive.CreateEntries(corpus)` 會將資料夾內的所有檔案加入，`archive.Save(zipFile)` 則將加密的 ZIP 寫入磁碟。  

## 如何之後變更 zip 密碼？
若需**變更 zip 密碼**，只要使用包含新密碼的 `TraditionalEncryptionSettings` 重新建立壓縮檔，然後再次儲存。此方式同樣適用於想要從已存在的資料夾**建立加密 zip 壓縮檔**且使用不同密碼的情況。

## 強化 zip 資料夾密碼的建議
- 使用大小寫字母、數字與符號混合。  
- 目標長度至少 12 個字元；較長的密碼破解難度指數提升。  
- 避免使用常見詞彙或模式；可考慮使用密語。  

## 常見問題與建議
- **大型資料夾：** Aspose.Zip 以串流方式處理資料，即使是巨大的目錄，記憶體使用量亦保持低位。  
- **密碼複雜度：** 使用強密碼（混合字母、數字、符號）以提升安全性。  
- **授權錯誤：** 確保已套用有效的授權檔案；否則函式庫會以受限制的評估模式執行。  
- **zip 資料夾密碼未被識別：** 確認在開啟壓縮檔時使用相同的加密方式（`TraditionalEncryptionSettings`）。  

## 常見問答

### Aspose.Zip for .NET 是否適用於大型目錄？
是的，Aspose.Zip for .NET 專為有效處理大型目錄而設計，提供最佳效能。

### 我可以變更已受保護目錄的密碼嗎？
可以，您只需在程式碼中調整 `TraditionalEncryptionSettings` 即可修改密碼。

### 使用 Aspose.Zip for .NET 有授權需求嗎？
是的，於正式環境使用 Aspose.Zip for .NET 必須擁有有效授權。您可於 **[此處](https://purchase.aspose.com/buy)** 取得授權。

### 是否提供 Aspose.Zip for .NET 的免費試用？
是的，您可前往 **[此處](https://releases.aspose.com/)** 取得免費試用。

### 我可以在哪裡取得 Aspose.Zip for .NET 的其他支援？
您可前往 **[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)** 取得支援或提問。

## 快速問答（AI 友好）

**Q: 如何使用 Aspose.Zip 以 zip 加密資料夾？**  
A: 在建立 `Archive` 物件時使用 `TraditionalEncryptionSettings`，然後對目標資料夾呼叫 `CreateEntries`。

**Q: 壓縮檔建立後，我可以再設定 zip 資料夾密碼嗎？**  
A: 不行，密碼必須在建立時即設定；若要變更，需以新密碼重新建立壓縮檔。

**Q: Aspose.Zip 是否支援 AES 加密以提升安全性？**  
A: 有的，您可以改用 `AesEncryptionSettings` 以 AES‑256 加密取代傳統的 ZipCrypto。

**Q: 此函式庫相容於 .NET 6 與 .NET 7 嗎？**  
A: 完全相容——目前的版本支援所有現代 .NET 執行環境。

**Q: 若嘗試在未提供密碼的情況下開啟受密碼保護的 zip，會發生什麼？**  
A: Aspose.Zip 會拋出 `PasswordRequiredException`，要求提供正確的密碼。

---

**最後更新：** 2026-03-08  
**測試環境：** Aspose.Zip for .NET (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}