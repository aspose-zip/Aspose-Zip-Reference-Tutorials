---
date: 2026-03-02
description: 學習如何使用 Aspose.Zip 在 .NET 中建立受密碼保護的 ZIP 壓縮檔並以密碼壓縮檔案。請跟隨我們的逐步指南。
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 在 .NET 中建立受密碼保護的 ZIP 檔案
url: /zh-hant/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 建立受密碼保護的 ZIP 壓縮檔

## 介紹

當您需要分享機密資料時，**受密碼保護的 zip 壓縮檔** 是最簡單且最有效的保護方式之一。在 .NET 應用程式中，Aspose.Zip 讓 **以密碼壓縮檔案** 變得輕鬆，並為每個檔案提供獨立的加密金鑰。透過本教學，您將學會如何建立此類壓縮檔、了解其重要性，以及在實務專案中的應用情境。

## 快速答覆
- **我應該使用哪個函式庫？** Aspose.Zip for .NET 內建支援每個檔案的密碼與多種加密方式。  
- **程式碼需要多少行？** 大約 30 行，包括設定與儲存壓縮檔的程式碼。  
- **每個檔案可以使用不同的密碼嗎？** 可以 – 您可以為每個條目指派唯一的密碼。  
- **有哪些加密方法可用？** 傳統 ZipCrypto、AES‑128 與 AES‑256。  
- **正式環境需要授權嗎？** 正式使用需購買商業授權；亦提供免費試用版。

## 什麼是受密碼保護的 ZIP 壓縮檔？
受密碼保護的 ZIP 壓縮檔是一種需要密碼才能解壓縮內容的壓縮檔（ZIP）。密碼可以保護整個壓縮檔或個別條目，且現代演算法如 AES‑128/256 提供強大的加密保護。

## 為什麼要使用 Aspose.Zip 以密碼壓縮檔案？
- **細緻的安全性** – 為每個檔案指派不同的密碼，適用於多租戶情境。  
- **多種加密標準** – 可在傳統 ZipCrypto 與強大的 AES 之間選擇。  
- **不需外部工具** – 所有操作皆在 .NET 程式碼中以程式方式完成。  
- **效能** – 使用 Deflate 進行快速壓縮，同時保持壓縮檔體積小。

## 前置條件

開始之前，請確保您已具備：

- **Aspose.Zip for .NET** – 在專案中安裝此函式庫。詳細文件請參考[此處](https://reference.aspose.com/zip/net/)。  
- **下載最新套件**（若尚未下載），請前往[此連結](https://releases.aspose.com/zip/net/)。  
- 包含欲壓縮檔案的資料夾。

## 匯入命名空間

在 C# 檔案的最上方加入必要的命名空間：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 步驟 1：設定資源目錄路徑

將程式碼指向保存來源檔案的資料夾：

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：以個別密碼壓縮檔案

接下來，我們將建立一個 **受密碼保護的 ZIP 壓縮檔**，讓每個檔案使用自己的密碼與加密方式。範例使用三個示例檔案（`alice29.txt`、`asyoulik.txt`、`fields.c`），各自設定不同的密碼。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### 工作原理
- **CreateEntry** 會將檔案加入壓縮檔。  
- 第四個參數（`ArchiveEntrySettings`）可同時設定壓縮（`DeflateCompressionSettings`）與加密（`TraditionalEncryptionSettings` 或 `AesEcryptionSettings`）。  
- 為每個條目傳入不同的密碼字串，即可產生 **受密碼保護的 ZIP 壓縮檔**，每個檔案只能使用其專屬密碼解鎖。

## 常見問題與疑難排解

| 症狀 | 可能原因 | 解決方式 |
|---------|--------------|-----|
| 解壓縮時出現「密碼錯誤」 | 密碼不符或使用了錯誤的加密方式 | 請確認密碼字串完全正確，且解壓縮時使用相同的 `EncryptionMethod`。 |
| 壓縮檔大小超出預期 | 在小型文字檔上使用 AES‑256 會產生額外開銷 | 對於小檔案，使用 AES‑128 可能已足夠，且可產生較小的壓縮檔。 |
| `archive.Save` 時發生執行時例外 | 目標資料夾缺乏寫入權限 | 確保應用程式對 `dataDir` 具有寫入權限，或改用其他輸出路徑。 |

## 常見問答 (FAQs)

### 我可以為每個檔案使用不同的加密方式嗎？
可以，Aspose.Zip for .NET 允許在每個檔案上混用不同的加密方式——傳統 ZipCrypto、AES‑128 與 AES‑256。

### 是否提供試用版？
有，您可以在此取得 Aspose.Zip for .NET 的免費試用版[這裡](https://releases.aspose.com/)。

### 若遇到問題，我該如何取得支援？
請前往[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)尋求社群與 Aspose 官方的協助。

### 哪裡可以找到 Aspose.Zip for .NET 的詳細文件？
文件可在[此處](https://reference.aspose.com/zip/net/)取得。

### 我可以購買臨時授權來測試嗎？
可以，您可在[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-02  
**測試環境：** Aspose.Zip for .NET (latest release)  
**作者：** Aspose