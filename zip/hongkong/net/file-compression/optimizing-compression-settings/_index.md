---
date: 2026-06-09
description: 了解如何使用 Aspose.Zip for .NET 為 zip 添加密碼並建立 LZMA zip 壓縮檔。本教學涵蓋 Bzip2、LZMA（字典大小）、PPMd、增強型
  Deflate、Store 壓縮，以及 ASP.NET 大檔案的檔案壓縮。
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: 優化壓縮設定
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 為 zip 添加密碼並建立 LZMA 壓縮檔
url: /zh-hant/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 為 ZIP 添加密碼並使用 Aspose.Zip for .NET 建立 LZMA 壓縮檔案

在現代 .NET 應用程式中，**add password to zip** 同時建立高壓縮比的 LZMA ZIP 壓縮檔，可保護敏感資料，同時提供最佳的壓縮效果。無論您是構建 ASP.NET 檔案壓縮服務、處理多 GB 檔案的桌面工具，或是雲端工作流程，本教學將逐步說明如何使用 Aspose.Zip for .NET 來保護與壓縮檔案。

## 快速回答
- **LZMA 壓縮的主要好處是什麼？** 大多數檔案類型在合理速度下提供最高的壓縮比。  
- **哪種方法在不壓縮的情況下儲存檔案？** Store compression（亦稱 “store compression zip”）。  
- **我可以在 ASP.NET 應用程式中使用這些設定嗎？** 可以——只需在專案中引用 Aspose.Zip 並呼叫相同的 API。  
- **生產環境需要授權嗎？** 需要商業授權才能在生產環境使用；亦提供免費試用版。  
- **支援哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10。

## Aspose.Zip 中的 “add password to zip” 是什麼？
**加入 ZIP 密碼會加密 ZIP 壓縮檔內的每個條目，只有知道密碼的使用者才能解壓縮檔案。** Aspose.Zip 同時支援傳統的 ZipCrypto 加密與 AES 加密（128、192 或 256 位元）。加密設定在建立 `Archive` 時作為第二個參數傳遞給 `ArchiveEntrySettings`；沒有單獨的 `SetPassword` 方法。

## 為什麼使用 Aspose.Zip 進行 .NET 檔案壓縮？
Aspose.Zip 提供單一且一致的 API，涵蓋多種演算法，同時提供高效能與低記憶體使用量。它讓開發人員能針對不同情境選擇最佳的壓縮方式，並在同一步驟中套用加密，簡化程式碼並降低維護負擔。

- **統一 API** – 為 Bzip2、LZMA、PPMd、Enhanced Deflate 與 Store 提供一致的介面。  
- **效能優化** – 經過最佳化的原生實作可處理 **高達 10 GB 檔案**，且不需將整個檔案載入記憶體。  
- **ASP.NET 友好** – 可在 Web 專案、背景服務與 Azure Functions 中無縫運作。  
- **細緻控制** – 只需一次建構子呼叫即可調整字典大小、壓縮等級與加密方式。  
- **支援 10 種以上壓縮演算法** – 覆蓋企業資料管線中最常見的使用情境。

## 前置條件
- **Aspose.Zip for .NET Library** – 從 [Aspose documentation](https://reference.aspose.com/zip/net/) 下載並安裝。  
- **範例文字檔** – 準備一個範例檔案（例如 `sample.txt`），將用於壓縮。  
- **.NET 開發環境** – Visual Studio 2022 或任何相容的 IDE。  

## 匯入命名空間

`Archive`、`ArchiveEntrySettings` 與加密類別位於 `Aspose.Zip` 命名空間。請在檔案開頭匯入它們：

- `Archive` 代表 ZIP 壓縮檔容器。  
- `ArchiveEntrySettings` 保存每個條目的壓縮與加密選項。  
- 加密類別（例如 `AesEncryptionSettings`）定義資料的加密方式。

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

現在讓我們探索每個壓縮設定，並了解在適當情況下如何 **add password to zip**。

## 使用 Bzip2 壓縮設定

### 步驟 1：使用傳統加密初始化 Bzip2 壓縮

`Bzip2CompressionSettings` 設定 Bzip2 演算法（區塊大小等）。  
`TraditionalEncryptionSettings` 為條目套用傳統的 ZipCrypto 加密。

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*密碼保護是透過直接傳遞給 `ArchiveEntrySettings` 的 `TraditionalEncryptionSettings` 來實作的。*

## 如何使用 Aspose.Zip for .NET 為 ZIP 加入密碼

載入來源檔案，使用條目設定建立 `Archive`，並將檔案加入壓縮檔。加密會自動套用，因為在建立 `ArchiveEntrySettings` 實例時已提供加密設定。

**直接答案（40‑70 字）：**  
建立一個 `ArchiveEntrySettings` 物件，內含所需的壓縮設定以及 `TraditionalEncryptionSettings` 或 `AesEncryptionSettings` 之一。然後將此物件傳遞給 `Archive` 建構子，並使用 `AddEntry` 加入檔案。壓縮檔在寫入時已內嵌密碼，無需在建立後額外設定。

`ArchiveEntrySettings` 是配置持有者，告訴 Aspose.Zip 每個條目應如何壓縮與加密。  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## 如何使用 Aspose.Zip 建立 LZMA ZIP 壓縮檔

### 步驟 1：使用 AES256 加密初始化 LZMA 壓縮

`LzmaCompressionSettings` 控制 LZMA 特有的參數，如字典大小與 fast bytes。  
`AesEncryptionSettings` 為壓縮檔條目提供 AES‑256 加密。

**直接答案（40‑70 字）：**  
建立帶有指定 `DictionarySize` 的 `LzmaCompressionSettings`，再以密碼與 `EncryptionMethod.AES256` 建立 `AesEncryptionSettings` 物件，將兩者組合成 `ArchiveEntrySettings`。將此設定傳遞給 `Archive` 建構子並加入檔案；最終的 ZIP 會以 LZMA 壓縮且以 AES 保護，一次完成。

`LzmaCompressionSettings` 是控制 LZMA 特定參數（如字典大小與 fast bytes）的類別。  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **提示：** LZMA 提供可設定的 **LZMA 字典大小**，會影響壓縮比與記憶體使用量。若需針對極大檔案進行微調，可透過 `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` 來設定。

## 使用 PPMd 壓縮設定

### 步驟 1：使用 AES256 加密初始化 PPMd 壓縮

`PpmdCompressionSettings` 定義 PPMd 演算法的階序與記憶體使用量。  
`AesEncryptionSettings` 為壓縮檔條目提供 AES‑256 加密。

**直接答案（40‑70 字）：**  
建立 `PpmdCompressionSettings` 實例，與包含密碼的 `AesEncryptionSettings` 物件結合，並將兩者傳入 `ArchiveEntrySettings`。在建構 `Archive` 時使用此設定物件；最終的 ZIP 會以 PPMd 壓縮且已設定密碼保護，無需額外呼叫。

`PpmdCompressionSettings` 定義 PPMd 演算法的階序與記憶體使用量。  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## 使用 Enhanced Deflate 壓縮設定

### 步驟 1：使用 AES256 加密初始化 Enhanced Deflate 壓縮

`EnhancedDeflateCompressionSettings` 讓您指定在速度與大小之間取得平衡的壓縮等級。  
`AesEncryptionSettings` 為壓縮檔條目提供 AES‑256 加密。

**直接答案（40‑70 字）：**  
以您想要的等級（0‑9）建立 `EnhancedDeflateCompressionSettings`，再與 `AesEncryptionSettings` 結合，包裝成 `ArchiveEntrySettings`。將此設定傳遞給 `Archive` 建構子並加入檔案；壓縮檔將以 Enhanced Deflate 壓縮且使用 AES‑256 密碼保護，一次完成。

`EnhancedDeflateCompressionSettings` 讓您指定在速度與大小之間取得平衡的壓縮等級。  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## 使用 Store 壓縮設定（store compression zip）

### 步驟 1：使用傳統加密初始化 Store 壓縮

`StoreCompressionSettings` 告訴 Aspose.Zip 完全跳過壓縮，保留原始檔案的每個位元。  
`TraditionalEncryptionSettings` 套用傳統的 ZipCrypto 加密。

**直接答案（40‑70 字）：**  
建立 `StoreCompressionSettings` 實例（不執行壓縮），再與包含密碼的 `TraditionalEncryptionSettings` 結合，包裝成 `ArchiveEntrySettings`。將此設定傳遞給 `Archive` 建構子；最終的 ZIP 會保留原始檔案未壓縮，同時具備密碼保護。

`StoreCompressionSettings` 告訴 Aspose.Zip 完全跳過壓縮，保留原始檔案的每個位元。  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **專業提示：** 調整 `dataDir` 變數指向實際的工作目錄，若需將多個檔案加入同一壓縮檔，請重複使用相同的 `Archive` 實例。

## 常見問題與解決方案
- **「找不到檔案」錯誤** – 確認 `dataDir` 以路徑分隔符（`\` 或 `/`）結尾，且 `sample.txt` 確實存在。  
- **大型檔案的記憶體消耗** – 使用 `ArchiveEntrySettings` 啟用串流模式，直接將資料寫入輸出串流。  
- **不相容的壓縮等級** – 某些演算法（如 LZMA）提供額外屬性如 `DictionarySize`。若需更細緻的控制，請參考 API 文件。  
- **密碼未套用** – 確保在建構 `ArchiveEntrySettings` 時將加密設定物件作為第二個參數傳入，而非在壓縮檔建立後再設定。  

## 常見問答

**Q: 我可以將 Aspose.Zip for .NET 與其他壓縮函式庫一起使用嗎？**  
A: Aspose.Zip 設計為使用其內建演算法。雖然可以整合第三方函式庫，但需要在 Aspose API 之外自行處理。

**Q: 如何為使用 Aspose.Zip 建立的 ZIP 加入密碼保護？**  
A: 在建構 `Archive` 時，將 `TraditionalEncryptionSettings` 或 `AesEncryptionSettings` 作為第二個參數傳遞給 `ArchiveEntrySettings`。完整範例請參閱 [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)。

**Q: 有可供測試的試用版嗎？**  
A: 有，您可在 [here](https://releases.aspose.com/) 取得試用版。

**Q: 我可以在哪裡取得社群協助或提問？**  
A: 請前往 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 參與支援與社群討論。

**Q: 我可以取得暫時授權以供評估嗎？**  
A: 可以，請在 [here](https://purchase.aspose.com/temporary-license/) 取得暫時授權。

**Q: 這對 ASP.NET 檔案壓縮有何幫助？**  
A: 只要在 ASP.NET 控制器或中介軟體中呼叫相同的 API，即可在傳送給客戶端前即時壓縮檔案，降低頻寬需求並提升感知效能。

**Q: 有效壓縮大型檔案的最佳方法是什麼？**  
A: 結合串流模式與 LZMA 壓縮，並設定適當的 `DictionarySize`。此方式在記憶體使用量與壓縮比之間取得平衡，適用於龐大資料集。

---

**最後更新：** 2026-06-09  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Aspose.Zip for .NET - 密碼保護 ZIP 壓縮檔並在不壓縮的情況下儲存多個檔案](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [為 .NET 目錄建立受密碼保護的 ZIP – Aspose.Zip 教學](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [一次壓縮多個檔案 C# – 使用 Aspose.Zip for .NET 輕鬆壓縮](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}