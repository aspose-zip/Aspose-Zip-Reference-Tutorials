---
date: 2026-11-18
description: 學習如何使用 Aspose.Zip for .NET 建立 tar 檔案並壓縮為 TarZ – 一步一步的指南，協助您有效處理 .NET
  檔案。
keywords:
- how to create tar
- add files to tar
- add directory to tar
- archive files to tar
- compress files .net
lastmod: 2026-11-18
linktitle: 壓縮為 TarZ
og_description: 學習如何使用 Aspose.Zip for .NET 建立 tar 檔案並壓縮為 TarZ。本指南將帶您逐步新增檔案、目錄，並高效壓縮。
og_image_alt: 'Guide: create tar and compress to TarZ using Aspose.Zip for .NET'
og_title: 如何使用 Aspose.Zip for .NET 建立 tar 並壓縮為 TarZ
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to create tar archives and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: How to create tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/),
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: 如何使用 Aspose.Zip for .NET 建立 tar 並壓縮為 TarZ
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將檔案加入 tar 並以 Aspose.Zip for .NET 壓縮為 TarZ

## 介紹

如果您需要 **add files to tar** 並將壓縮檔案轉為 TarZ 格式，Aspose.Zip for .NET 讓整個過程變得輕鬆無憂。在本教學中，我們將逐步說明——從設定專案、建立 tar 壓縮檔、加入檔案，到最後儲存為 .tar.z 壓縮檔。完成後，您將擁有可重複使用的程式碼片段，可直接嵌入任何 .NET 應用程式，無論是處理少量設定檔還是整個目錄樹。

## 快速解答
- **什麼程式庫負責建立 tar？** Aspose.Zip for .NET  
- **程式碼行數多少？** 約 15 行（不含註解）  
- **測試是否需要授權？** 提供免費試用；正式環境需授權。  
- **支援的 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10  
- **我可以壓縮資料夾，而不只是檔案嗎？** 可以 – 您可以使用迴圈加入整個目錄。

## 什麼是 **add files to tar**？

**Add files to tar** 是將選取的檔案打包成單一未壓縮的 tar 容器，同時保留目錄層級與中繼資料的過程。tar 格式會產生一個確定性、跨平台的套件，之後的壓縮演算法可以有效處理，這使其成為跨平台發佈的理想選擇。

## 如何使用 Aspose.Zip for .NET 建立 tar 壓縮檔？

`TarArchive` 類別代表一個可容納多個檔案項目的 tar 容器。載入來源目錄、實例化 `TarArchive`、加入每個檔案（或整個子目錄），最後以 TarZ 壓縮旗標呼叫 `Save`。此流程簡單明瞭，只需少量程式碼，且在所有支援的 .NET 執行環境（包括 .NET Framework 與 .NET Core）中皆能一致運作。

`TarArchive` 類別是 Aspose.Zip 的核心物件，代表可加入項目的 tar 容器。使用它可在記憶體中完整產生 tar 檔案、直接串流至回應，或寫入磁碟而不需暫存 zip 檔案。

## 為什麼在壓縮為 TarZ 前先加入檔案至 tar？

先建立 tar 容器可將打包與壓縮分離，帶來三項可量化的好處。透過將這兩個階段分開，您可取得可預測、可重複的壓縮檔，並能獨立壓縮，方便評估壓縮比率，且可將相同的 tar 用於不同的壓縮演算法。

1. **可移植性** – `.tar` 檔案可在任何類 Unix 系統上解壓，無需額外函式庫。  
2. **速度** – Tar 的建立本質上是串流複製操作；隨後的 Z 壓縮僅專注於縮小尺寸，通常可減少原始資料 **30‑70 %**。  
3. **相容性** – 許多舊版工具（例如 `tar`、`gzip`）在套用 gzip 類型壓縮前都需要 `.tar`，這正是 `.tar.z` 副檔名所代表的。

### 為何這對 .NET 開發者很重要
使用 tar 容器可讓您的 .NET 程式碼保持簡潔且具決定性。您可以在記憶體中產生壓縮檔、直接串流至回應，或寫入磁碟而不必處理暫存 zip 檔案。此模式特別適用於建置管線、日誌彙總，或需要將一組設定檔傳送至 Linux 服務的情境。

## 前置條件

在深入程式碼之前，請確保您已：

- **Aspose.Zip for .NET** 已安裝。從官方網站[此處](https://releases.aspose.com/zip/net/)下載。  
- 機器上有一個資料夾包含您想要壓縮的檔案。請將佔位路徑替換為實際目錄。

## 匯入命名空間

在 C# 檔案的頂部加入所需的 `using` 陳述式：

```csharp
using System;
using Aspose.Zip.Tar;
```

> **小技巧：** 若需要動態組合路徑，請使用 `Path.Combine`；它可避免在不同作業系統上遺漏路徑分隔符。

## 如何使用 Aspose.Zip for .NET 將檔案加入 tar？

`CreateEntry` 方法可將新檔案項目加入 tar 壓縮檔，並指定名稱與內容串流。載入來源目錄、建立 `TarArchive` 實例、加入每個檔案（或整個子目錄），最後以 TarZ 壓縮旗標呼叫 `Save`。此工作流程簡潔，通常不超過 20 行，且在所有支援的 .NET 執行環境中皆能運作，提供可靠的資料打包與壓縮方式。

`Save` 方法將壓縮檔寫入磁碟，並可選擇性地套用壓縮。

### 定義錨點
`TarArchive` 類別是 Aspose.Zip 的核心物件，代表可加入項目的 tar 容器。

### 步驟說明

#### 步驟 1：定義文件目錄

```csharp
string dataDir = "Your Document Directory";
```

> **為何此步驟重要：** `dataDir` 作為所有要加入檔案的基礎位置。將其放在單一變數中，可使程式碼易於維護，且能在多個壓縮檔間重複使用。

#### 步驟 2：建立 Tar 壓縮檔並加入檔案

##### 2.1：建立 Tar 壓縮檔實例

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> `using` 區塊確保 `TarArchive` 物件能正確釋放，釋放任何檔案句柄或記憶體緩衝區。

##### 2.2：將檔案加入壓縮檔  

`CreateEntry` 會將檔案加入 tar 壓縮檔，指定其名稱與內容串流。  

在 `using` 區塊內，加入您想要包含的每個檔案：

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

您可以根據需要重複呼叫 `CreateEntry` 以加入任意數量的檔案，或以迴圈方式程式化加入目錄中的檔案。例如，`foreach (var file in Directory.GetFiles(dataDir))` 迴圈可在保留相對路徑的同時處理任意數量的檔案。

##### 2.3：儲存壓縮的 TarZ 檔案  

`Save` 方法將壓縮檔寫入磁碟，並套用選擇的壓縮格式。  

加入所有項目後，將 tar 壓縮檔壓縮為 `.tar.z` 格式：

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

產生的 `archive.tar.z` 檔案會位於您在 `dataDir` 中指定的同一資料夾。現在您可以將這個單一的壓縮套件傳送至任何支援 TarZ 的系統。

## 常見問題與解決方案

| Issue | Reason | Fix |
|-------|--------|-----|
| **找不到檔案** | 路徑錯誤或缺少檔案副檔名 | 確認 `dataDir` 以路徑分隔符結尾，且檔名正確。 |
| **存取被拒** | 目標資料夾權限不足 | 以適當權限執行應用程式，或選擇可寫入的資料夾。 |
| **壓縮檔比預期更大** | 原始檔案已經壓縮（例如圖片、影片） | TarZ 最適合文字或日誌檔案；考慮保留已壓縮的檔案不再壓縮。 |

### 常見陷阱須留意
- **缺少結尾斜線** – 若 `dataDir` 未以 `\` 或 `/` 結尾，字串串接會產生無效路徑。  
- **大型目錄** – 加入上千個檔案可能會消耗記憶體；考慮串流項目或使用直接寫入檔案串流的 `TarArchive` 重載。  
- **編碼問題** – 非 ASCII 檔名可能需要明確的編碼處理；Aspose.Zip 預設支援 UTF‑8，但請在目標平台上驗證。

## 常見問答

**Q: 我可以使用 Aspose.Zip for .NET 壓縮整個資料夾嗎？**  
A: 當然可以。使用 `Directory.GetFiles` 迴圈，對每個檔案呼叫 `CreateEntry`，保留相對路徑。

**Q: 是否提供 Aspose.Zip for .NET 的試用版？**  
A: 有的，您可透過下載免費試用版[此處](https://releases.aspose.com/) 來探索 Aspose.Zip for .NET 的功能。

**Q: 我在哪裡可以找到 Aspose.Zip for .NET 的完整文件？**  
A: 文件可於[此處](https://reference.aspose.com/zip/net/)取得，提供關於函式庫功能與使用方式的詳細說明。

**Q: 我該如何取得 Aspose.Zip for .NET 的支援？**  
A: 前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 尋求協助、分享經驗，並與社群互動。

**Q: 我可以取得 Aspose.Zip for .NET 的臨時授權嗎？**  
A: 可以，若需要臨時授權，請於[此處](https://purchase.aspose.com/temporary-license/)取得。

## 結論

您現在已學會如何 **add files to tar** 並使用 Aspose.Zip for .NET 將結果壓縮為 TarZ 壓縮檔。此方法提供乾淨且可移植的套件，便於傳輸、儲存或進一步處理。歡迎將此程式碼片段套用於批次處理目錄、整合至建置管線，或與其他 Aspose 元件結合，以建立更豐富的文件工作流程。

---

**Last Updated:** 2026-11-18  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## 相關教學

- [將多個檔案加入 tar 並建立 tar.gz 壓縮檔，使用 Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [如何使用 Aspose.Zip for .NET 壓縮多個檔案為 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [檔案解壓與格式](/zip/net/archive-extraction-and-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}