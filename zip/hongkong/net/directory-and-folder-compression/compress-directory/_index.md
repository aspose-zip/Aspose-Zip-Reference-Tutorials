---
date: 2026-05-30
description: 了解如何使用 Aspose.Zip for .NET 壓縮資料夾、高效建立 zip 壓縮檔，以及在 .NET 應用程式中減少儲存空間。
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: 如何壓縮資料夾
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮資料夾
url: /zh-hant/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮資料夾

在本教學中，您將快速且可靠地學會 **如何壓縮資料夾**，使用 Aspose.Zip for .NET。無論您是在開發桌面工具、雲端服務，或是自動備份腳本，將資料夾壓縮成 ZIP 檔案都能大幅減少儲存需求並加快網路傳輸速度。我們將逐步說明每一行程式碼的意義，並指出常見的陷阱，讓您能自信地應用此技巧。

## 快速回答
- **Aspose.Zip 的功能是什麼？** 它提供一套簡易的 .NET API，讓您在不依賴外部套件的情況下建立與解壓 ZIP 檔案。  
- **實作需要多久時間？** 基本的資料夾壓縮通常在 10 分鐘以內完成。  
- **支援哪些 .NET 版本？** .NET Framework 2.0‑4.8.1、.NET Core 2.0‑3.1，以及 .NET 5‑10。  
- **生產環境需要授權嗎？** 需要，商業授權是生產使用的前提。  
- **可以一次壓縮多個資料夾嗎？** 當然可以——對任何 `DirectoryInfo` 集合使用 `CreateEntries` 方法，即可在一次執行中 **壓縮多個資料夾**。  

`CreateEntries` 會將目錄中的所有檔案加入壓縮檔。

## 什麼是「如何壓縮資料夾」？

壓縮資料夾是指將指定目錄下的所有檔案與子資料夾打包成單一的 ZIP 檔案。這樣不僅能減少整體大小，還能保留原始層級結構，方便傳輸或儲存。產生的 ZIP 可在任何平台上開啟，且在解壓縮時會完整還原原始目錄結構。

## 為什麼要使用 Aspose.Zip 來完成此任務？

Aspose.Zip 讓您 **直接在 .NET 程式碼中建立 zip 檔案**，且在所有支援的執行環境中提供一致的 API。只要載入 `Archive` 類別、加入條目、設定 `CompressionLevel`，必要時再指定密碼，最後呼叫 `Save` 即可。此函式庫在一般硬體上能在一秒內處理含數千檔案的資料夾，並支援超過 50 種壓縮格式與加密演算法。

## 前置條件

- **Aspose.Zip for .NET** – 於此處下載 [here](https://releases.aspose.com/zip/net/) 或 [here](https://releases.aspose.com/zip/net)。  
- **開發環境** – Visual Studio、Rider，或任何支援 C# 的 IDE。  
- **文件目錄** – 將程式碼中的 `"Your Document Directory"` 替換為您欲壓縮的資料夾路徑。  
- **參考文件** – 請參閱官方說明文件 [here](https://reference.aspose.com/zip/net/)。  

## 匯入命名空間

先匯入必要的命名空間，以取得核心壓縮類別。

```csharp
using Aspose.Zip;
using System.IO;
```

## 使用 Aspose.Zip 壓縮資料夾

以下是一個直接示範 **如何壓縮資料夾** 內容的範例。相同的模式亦可延伸至 **壓縮多個檔案 .net** 或建立自訂的壓縮結構。

### 步驟 1：初始化您的文件目錄

將變數 `dataDir` 設為您要壓縮的目錄路徑。

```csharp
string dataDir = "Your Document Directory";
```

### 步驟 2：建立輸出 ZIP 檔案

開啟兩個 `FileStream` 物件作為輸出 ZIP 檔案。此示例說明如何從同一來源產生多個壓縮檔，適用於版本備份等情境。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### 步驟 3：壓縮目錄

`Archive` 類別代表一個 ZIP 壓縮檔，提供加入條目與儲存檔案的方法。使用它即可將目標資料夾的每個條目加入。範例使用名為 **CanterburyCorpus** 的示範資料夾，您可自行指向任何目錄。

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **專業提示：** 若需以特定壓縮等級 **建立 zip archive .net**，請在呼叫 `Save` 前設定 `archive.CompressionLevel`。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 空的 ZIP 檔案 | `dataDir` 指向錯誤的資料夾或缺少結尾斜線 | 核對路徑，並確保資料夾內有檔案 |
| `UnauthorizedAccessException` | 程式缺乏檔案系統存取權限 | 以系統管理員身分執行 Visual Studio，或授予讀寫權限 |
| 大型目錄導致記憶體使用過高 | 一次將所有條目載入記憶體 | 在迴圈中使用 `Archive.CreateEntryFromFile` 逐一串流檔案 |

## 常見問答（補充）

**Q: 可以為 ZIP 檔案設定密碼嗎？**  
A: 可以。於呼叫 `Save` 前設定 `archive.Password = "yourPassword";`。

**Q: 如何只包含特定類型的檔案？**  
A: 在呼叫 `CreateEntries` 前，使用 `DirectoryInfo` 集合的 `GetFiles("*.txt")` 或類似方式過濾。

**Q: 有沒有辦法在不重新建立的情況下更新既有 ZIP？**  
A: Aspose.Zip 支援透過 `Archive.UpdateEntry` 進行增量更新。

## 常見問答

### Q1: Aspose.Zip for .NET 可以同時用於商業與個人專案嗎？

A1: 可以，Aspose.Zip for .NET 同時提供商業與個人使用授權。

### Q2: 有提供免費試用嗎？

A2: 有，您可於此處取得免費試用 [here](https://releases.aspose.com/zip/net)。

### Q3: 如何取得 Aspose.Zip for .NET 的支援？

A3: 前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 取得社群支援，或考慮購買 [臨時授權](https://purchase.aspose.com/temporary-license/) 以獲得專屬協助。

### Q4: 是否有其他範例與教學可供參考？

A4: 有，請參閱 [文件說明](https://reference.aspose.com/zip/net/) 中的完整範例與教學。

### Q5: 如何購買 Aspose.Zip for .NET？

A5: 您可以在此處直接購買 [here](https://purchase.aspose.com/buy)。

## 結論

您現在已掌握使用 Aspose.Zip for .NET **壓縮資料夾** 的完整、生產環境可用範例。透過 `Archive` 類別，您可以 **建立 zip archive** 檔案、設定自訂的 `CompressionLevel`、加入密碼保護，甚至在一次執行中 **壓縮多個資料夾**，非常適合自動化資料夾備份工作。可自行嘗試加入加密、分割壓縮檔或直接串流至雲端儲存，打造任何 .NET 壓縮需求的強大解決方案。

---

**最後更新：** 2026-05-30  
**測試版本：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
