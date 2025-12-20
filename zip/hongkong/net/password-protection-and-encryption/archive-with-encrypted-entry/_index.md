---
date: 2025-12-20
description: 學習如何在 .NET 中使用 Aspose.Zip 建立具備 AES 加密的 7z 壓縮檔。安全壓縮、zip 密碼保護，以及加密的 7z
  輕鬆上手。
linktitle: Archive with Encrypted Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 .NET 中使用 AES 加密建立 7z 檔案
url: /zh-hant/net/password-protection-and-encryption/archive-with-encrypted-entry/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中使用 AES 加密建立 7z 檔案

## 簡介

在 .NET 應用程式中保護敏感資料時，建立具強大 AES 加密的 **7z** 壓縮檔是一項常見需求。本教學將示範如何使用 Aspose.Zip 函式庫安全地 **建立 7z** 檔案，內容涵蓋從專案設定到加入加密項目。完成後，您將了解 **secure archiving .NET** 為何重要、**aes zip encryption** 的運作原理，以及如何僅用幾行 C# 程式碼實作 **zip password protection**。

## 快速回答
- **「7z」是什麼意思？** 它是使用 7‑Zip 格式建立的壓縮檔的副檔名，支援高壓縮比與強加密。  
- **哪種演算法提供最佳安全性？** AES‑256，可透過 Aspose.Zip 的 `SevenZipAESEncryptionSettings` 取得。  
- **開發時需要授權嗎？** 可取得臨時授權供測試使用；正式上線需購買完整授權。  
- **可以加密多個項目嗎？** 可以——對每個要保護的檔案重複呼叫 `CreateEntry`。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6 以上。

## 什麼是 7z 檔案以及為何要加密？

**7z** 檔案是一種可容納多個檔案與目錄的壓縮容器。由於支援 AES 加密，它非常適合資料機密性極高的情境，例如傳輸機密報告、備份專有程式碼或儲存個人資訊。使用 **encrypted seven zip** 壓縮檔可協助您符合合規要求，並防止未授權存取。

## 先決條件

- **開發環境：** Visual Studio 2022 或任何相容 .NET 的 IDE。  
- **Aspose.Zip for .NET：** 安裝此函式庫。相關文件可於 [here](https://reference.aspose.com/zip/net/) 取得。  
- **下載：** 從 [download link](https://releases.aspose.com/zip/net/) 取得 Aspose.Zip for .NET 函式庫。  
- **基礎知識：** 熟悉 C# 與 .NET 專案結構。

## 匯入命名空間

在 C# 專案中，匯入必要的命名空間，以便使用 Aspose.Zip API：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## 步驟 1：設定資源目錄路徑

定義包含欲壓縮檔案的資料夾。此路徑稍後會在讀取資料寫入壓縮檔時使用。

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory";
```

## 步驟 2：建立具 AES 加密的 Seven Zip 檔案

現在我們將建立 **7z** 壓縮檔並加入加密項目。範例使用簡單的位元組陣列，您也可以改為任何串流（例如檔案串流）。

```csharp
//ExStart: ArchiveWithEncryptedEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", 
            new MemoryStream(new byte[] { 0x00, 0xFF }), 
            new SevenZipEntrySettings(new SevenZipLZMACompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.Save(sevenZipFile);
    }
}
//ExEnd: ArchiveWithEncryptedEntry
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

**說明：**  
- `SevenZipArchive` 會建立新的 7z 容器。  
- `CreateEntry` 新增名為 `entry1.bin` 的檔案。  
- `SevenZipAESEncryptionSettings("test1")` 以密碼 *test1* 套用 **aes zip encryption**。  
- 如需額外檔案，可再次呼叫 `CreateEntry`，並視需要設定各自的加密參數。

## 為何在 .NET 中使用 Aspose.Zip 進行安全壓縮？

- **完整 .NET 支援：** 可在 .NET Framework、.NET Core 以及 .NET 5/6 上運作。  
- **高效能壓縮：** LZMA 演算法提供極佳的壓縮比。  
- **強大加密：** AES‑256 加密確保壓縮檔免受暴力破解攻擊。  
- **無外部相依性：** 所有功能皆內建於 Aspose.Zip DLL 中。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **「Invalid password」錯誤在開啟壓縮檔時** | 密碼不匹配或使用了錯誤的加密設定。 | 確認傳遞給 `SevenZipAESEncryptionSettings` 的密碼與解壓縮時使用的密碼相同。 |
| **壓縮檔顯示為空** | `CreateEntry` 在 `Save` 之前未被呼叫。 | 在呼叫 `archive.Save` 前，確保已加入至少一個項目。 |
| **大型檔案導致效能下降** | 將整個檔案讀入記憶體。 | 對每個項目使用 `FileStream` 而非 `MemoryStream`，直接串流資料。 |

## 常見問答

### 我可以在非商業專案中使用 Aspose.Zip for .NET 嗎？
可以，Aspose.Zip for .NET 可用於商業與非商業專案。

### 如何取得 Aspose.Zip for .NET 的臨時授權？
可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### 是否有社群支援可供 Aspose.Zip for .NET 使用？
有，請前往 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 取得社群支援。

### 除了 LZMA，還支援其他壓縮演算法嗎？
Aspose.Zip for .NET 支援多種壓縮演算法，詳情請參考文件。

### 我可以進一步自訂加密設定嗎？
當然可以！請參考文件了解進階的加密自訂選項。

## 結論

您現在已掌握如何使用 Aspose.Zip 在 .NET 中 **建立 7z** 壓縮檔並套用 AES 加密。此方式讓您能細緻控制壓縮與安全性，適用於任何需要 **zip password protection** 或 **encrypted seven zip** 檔案的情境。歡迎自行嘗試多項目、不同壓縮等級與自訂密碼，以符合專案需求。

---

**最後更新：** 2025-12-20  
**測試版本：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}