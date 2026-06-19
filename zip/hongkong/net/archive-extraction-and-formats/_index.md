---
date: 2026-06-19
description: 了解如何使用 Aspose.Zip for .NET 壓縮 tar 檔案、建立 targz 壓縮檔，並解壓受密碼保護的 zip 檔案——提升儲存效能與安全性。
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: 檔案解壓與格式
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮 Tar 檔案
url: /zh-hant/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮 Tar 檔案

## 介紹

在本指南中，您將了解 **如何壓縮 tar** 檔案，使用 Aspose.Zip for .NET，學習建立 TarGz 壓縮檔，並了解如何解壓受密碼保護的 zip 壓縮檔。有效的壓縮檔處理是現代 .NET 開發人員的核心技能——無論您是構建備份服務、雲端儲存客戶端，或是資料處理管線，熟悉這些格式都能降低儲存成本、加快傳輸速度，並確保敏感資料安全。

## 快速回答
- **什麼是 TarBz2？** 結合 TAR 打包與 BZIP2 壓縮的壓縮檔，具備高壓縮比。  
- **為什麼選擇 Aspose.Zip for .NET？** 它提供單一、流暢的 API，能在不依賴外部套件的情況下建立與解壓多種壓縮檔格式。  
- **我可以建立 TarGz 壓縮檔嗎？** 可以——Aspose.Zip 支援 TarGz、TarLz、TarXz、TarZ 等多種格式。  
- **如何解壓受密碼保護的 zip 壓縮檔？** 在解壓時使用 `ArchiveEntry` 物件的 `Password` 屬性。  
- **生產環境需要授權嗎？** 生產環境需要商業授權；可使用免費試用版進行評估。

## 什麼是 Tar 壓縮？
Tar（磁帶檔案）是一種容器格式，可將多個檔案與目錄打包成單一資料流，且不進行壓縮。當您套用 BZIP2、GZip、LZMA 或 XZ 等壓縮演算法時，結果會成為 **基於 tar 的壓縮檔**，如 `.tar.bz2`、`.tar.gz`、`.tar.lz` 等。這些格式在 Linux、macOS 與 Windows 上皆得到廣泛支援，因而成為跨平台資料交換的理想選擇。

## 為什麼使用 Aspose.Zip for .NET 處理這些格式？
Aspose.Zip 提供 **統一、無相依性的 API**，支援超過 50 種壓縮與封存格式，包括 TarBz2、TarGz、TarLz、TarXz 與 TarZ。它可在 Windows、Linux 與 macOS 上執行，其基於串流的架構即使面對數百 MB 的壓縮檔，也能將記憶體使用量控制在 10 MB 以下。內建密碼保護，允許對單一條目加密，無需額外函式庫。

## 前置條件
- .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，或 .NET 5–10。  
- 已安裝 Aspose.Zip for .NET NuGet 套件 (`Install-Package Aspose.Zip`)。  
- 具備 C# 檔案 I/O 與 .NET 專案系統的基本知識。

## 步驟指南

### 如何壓縮 Tar 檔案 – 直接答案
`Archive` 代表一個壓縮檔案，並提供加入條目與儲存的功能。  
建立 `Archive` 實例，加入欲打包的檔案，設定 `CompressionType.BZip2`，然後以 `ArchiveFormat.TarBz2` 呼叫 `Save`。函式庫會在單一次串流過程中寫入 TAR 容器並完成壓縮，因而不會將整個壓縮檔載入記憶體。

### 步驟 1：選擇所需的壓縮檔格式
決定哪種基於 tar 的格式最符合您的壓縮速度與大小取捨：

- **TarBz2** – 最高壓縮比（約比 TarGz 小 30 %），但速度較慢。  
- **TarGz** – 在速度與大小之間取得良好平衡；適用於大多數雲端儲存情境。  
- **TarLz / TarXz** – 壓縮率極高且速度適中，適合歸檔儲存。  
- **TarZ** – 傳統格式，用於相容較舊的 Unix 工具。

### 步驟 2：建立新的 `Archive` 實例
`Archive` 是代表記憶體中單一壓縮檔的頂層物件。  
`Archive` 類別管理打包與壓縮工作流程，提供加入條目與寫入最終檔案的方法。

### 步驟 3：加入檔案與資料夾
您可以使用 `AddAll` 加入整個目錄樹，或使用 `AddFile` 加入單一檔案。只要傳入基礎目錄路徑，即可保留原始的資料夾層級結構。

### 步驟 4：設定所需的壓縮類型
`CompressionType` 列舉了支援的演算法。  
`CompressionType` 定義在儲存期間套用於 TAR 串流的演算法（BZip2、GZip、LZMA、XZ 等）。

### 步驟 5：儲存壓縮檔
`ArchiveFormat` 是一組列舉（例如 `TarBz2`、`TarGz`），告訴寫入器使用哪種容器與壓縮方式。  
呼叫 `Save` 會使用選定的格式將壓縮檔寫入磁碟。

### 步驟 6：使用密碼解壓縮檔
`ArchiveEntry` 代表壓縮檔內的單一檔案或目錄條目。  
要解壓受密碼保護的 zip，先開啟壓縮檔，找到每個 `ArchiveEntry`，設定其 `Password` 屬性，然後呼叫 `Extract`。此每條目密碼模型允許您在同一 zip 中保護個別檔案。

### 步驟 7：驗證結果
解壓後，比較檔案大小與 SHA‑256 雜湊值，以確認壓縮檔往返過程中資料完整性未受影響。

## 常見使用情境
- **備份工具** – 將每日備份儲存為 `.tar.bz2`，可降低高達 30 % 的儲存成本。  
- **跨平台資料交換** – Tar 系列格式被 Linux、macOS 與 Windows 工具原生支援。  
- **安全分發** – 為敏感條目設定密碼，滿足合規需求，且無需額外加密工具。

## 疑難排解與技巧
- **大型壓縮檔** – 建議使用串流 API（`Archive.CreateEntryFromFile`）以降低記憶體使用量。  
- **密碼不符** – 每個 `ArchiveEntry` 設定的密碼必須完全相同，否則會拋出 `InvalidPasswordException`。  
- **壓縮等級** – BZIP2 不提供自訂等級；若需更細緻的控制，可改用 LZMA（`CompressionType.LZMA`）或 XZ（`CompressionType.XZ`）。

## 常見問題

**Q: 如何建立 TarGz 壓縮檔？**  
A: 設定 `CompressionType.GZip`，在呼叫 `Save` 時使用 `ArchiveFormat.TarGz`。即可一次產生 `.tar.gz` 檔案。

**Q: 能在不知道密碼的情況下解壓受密碼保護的壓縮檔嗎？**  
A: 不能。每個條目必須提供正確的密碼，否則解壓會因 `InvalidPasswordException` 失敗。

**Q: Aspose.Zip 是否支援對不同條目使用不同密碼解壓？**  
A: 支援。在呼叫 `Extract` 前，可為每個 `ArchiveEntry` 個別設定密碼。

**Q: 哪種格式提供最佳壓縮率？**  
A: 通常 TarBz2 產生最小的檔案大小，其次是 TarLz 與 TarXz。TarGz 則提供較快且仍具效能的替代方案。

**Q: 加入 TAR 壓縮檔的檔案數量有上限嗎？**  
A: 實際上沒有，但若壓縮檔極大（>10 GB），分割成多個部分可能較易處理。

## 壓縮檔解壓與格式教學
### [使用 Aspose.Zip for .NET 將檔案壓縮為 TarBz2](./compress-to-tar-bz2/)
了解如何在 .NET 中使用 Aspose.Zip 將檔案壓縮為 TarBz2 格式。遵循我們的步驟指南，以高效完成檔案壓縮。  
### [使用 Aspose.Zip for .NET 壓縮為 TarGz](./compress-to-tar-gz/)
探索在 .NET 中使用 Aspose.Zip 進行高效檔案壓縮。輕鬆壓縮為 TarGz。  
### [使用 Aspose.Zip for .NET 壓縮為 TarLz](./compress-to-tar-lz/)
在 .NET 中使用 Aspose.Zip 輕鬆壓縮檔案。一步步學習建立 TarLz 壓縮檔。  
### [使用 Aspose.Zip for .NET 壓縮為 TarXz](./compress-to-tar-xz/)
了解如何在 .NET 中使用 Aspose.Zip 將檔案壓縮為 TarXz 格式。遵循我們的指南，以達到高效儲存與傳輸。  
### [使用 Aspose.Zip for .NET 壓縮為 TarZ](./compress-to-tar-z/)
探索使用 Aspose.Zip for .NET 逐步壓縮為 TarZ。為您的 .NET 專案提供高效檔案處理。  
### [在 Aspose.Zip for .NET 中使用不同密碼解壓縮條目](./extract-archive-different-passwords/)
了解如何在 Aspose.Zip for .NET 中使用不同密碼解壓縮條目。提升應用程式的安全性與彈性。

---

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## 相關教學

- [使用 Aspose.Zip for .NET 建立 tar 壓縮檔並加入檔案](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [如何使用 Aspose.Zip for .NET 壓縮 tar 並建立 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [使用 Aspose.Zip 將檔案加入 tar 並建立 tarxz 壓縮檔](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}