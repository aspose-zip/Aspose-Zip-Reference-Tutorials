---
date: 2026-10-25
description: 了解如何在使用 Aspose.Zip for .NET 壓縮 TAR 檔案時提取 ZIP 密碼並設定壓縮演算法，以提升儲存效率與安全性。
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: 檔案解壓與格式
og_description: 了解如何在使用 Aspose.Zip for .NET 壓縮 TAR 檔案時提取 ZIP 密碼並設定壓縮演算法，以提升儲存效率與安全性。
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: 使用 Aspose.Zip 提取 ZIP 密碼並壓縮 TAR 檔案
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: 使用 Aspose.Zip 提取 ZIP 密碼並壓縮 TAR 檔案
url: /zh-hant/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 提取 zip 密碼並使用 Aspose.Zip 壓縮 tar 檔案

## 介紹

在本指南中，您將了解 **extract zip password** 的技巧，學習在建立基於 tar 的壓縮檔時如何設定壓縮演算法，並了解如何使用 Aspose.Zip for .NET 建立 TarGz、TarBz2 以及其他格式。無論您是構建備份服務、雲端儲存客戶端，或是資料處理管線，掌握這些操作都能降低儲存成本、加快傳輸速度，並保護敏感檔案。

## 快速回答
- **What is TarBz2?** 結合 TAR 打包與 BZIP2 壓縮的壓縮檔，可提供高壓縮比。  
- **Why choose Aspose.Zip for .NET?** 支援超過 50 種壓縮與封存格式，可在 Windows、Linux 與 macOS 上執行，且對於數百 MB 的壓縮檔，記憶體使用量低於 10 MB。  
- **Can I create a TarGz archive?** 可以 — Aspose.Zip 提供 TarGz、TarLz、TarXz、TarZ 等多種格式。  
- **How do I extract a password‑protected zip archive?** 在呼叫 `Extract` 之前，為每個 `ArchiveEntry` 設定 `Password` 屬性。  
- **Do I need a license for production use?** 生產環境需要商業授權；可使用免費試用版進行評估。

## 什麼是 tar 壓縮？

Tar 壓縮將 TAR 容器與 BZIP2、GZIP、LZMA 或 XZ 等壓縮演算法結合。最終產生單一檔案（例如 `.tar.gz`、`.tar.bz2`），可在 Linux、macOS 與 Windows 上解壓。它保留原始目錄結構，支援隨機存取解壓，且被各種命令列工具與程式庫廣泛支援，適合跨平台分發與歸檔儲存。

## 為什麼在 .NET 中使用 Aspose.Zip 處理這些格式？

Aspose.Zip 提供統一且無相依性的 API，支援 **50+** 種封存與壓縮格式，涵蓋所有主要的 tar 系列類型。其串流架構可處理超過 10 GB 的壓縮檔，同時將記憶體使用量控制在 10 MB 以下，適合高吞吐量的伺服器工作負載。  

**Direct answer:** 您使用 Aspose.Zip 是因為它允許透過單一流暢的 API 建立、壓縮與解壓 tar 系列壓縮檔以及受密碼保護的 zip 檔，無需外部工具，且能以記憶體有效的串流模式處理多 GB 的壓縮檔。

## 前置條件
- .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 或 .NET 5–10。  
- Aspose.Zip for .NET NuGet 套件 (`Install-Package Aspose.Zip`)。  
- 具備 C# 檔案 I/O 與 .NET 專案系統的基本知識。

## 步驟指南

### 如何壓縮 tar 檔案 – 直接答案
建立 `Archive` 實例，加入欲打包的檔案，設定 `CompressionType.BZip2`（或其他演算法），然後以 `ArchiveFormat.TarBz2` 呼叫 `Save`。函式庫會在一次串流過程中寫入 TAR 容器並完成壓縮，無需將整個壓縮檔載入記憶體。

### 步驟 1：選擇所需的壓縮檔案格式
決定哪種 tar 系列格式最符合您的壓縮與速度取捨：

- **TarBz2** – 壓縮比最高（約比 TarGz 小 30 %），但速度較慢。  
- **TarGz** – 在速度與檔案大小之間取得良好平衡；適用於大多數雲端儲存情境。  
- **TarLz / TarXz** – 壓縮率極高且速度適中，適合歸檔儲存。  
- **TarZ** – 為相容舊版 Unix 工具的傳統格式。

### 步驟 2：建立新的 `Archive` 實例
`Archive` 代表單一壓縮檔，提供加入項目與儲存壓縮檔的方法。  

`Archive` 類別負責打包與壓縮工作流程，公開加入項目與寫入最終檔案的功能。

### 步驟 3：加入檔案與資料夾
您可以使用 `AddAll` 加入整個目錄樹，或使用 `AddFile` 加入單一檔案。  

`AddAll` 會將整個目錄樹加入壓縮檔，保留其結構。  
`AddFile` 會將單一檔案加入壓縮檔。只要傳入基礎目錄路徑，即可保留原始資料夾階層。

### 步驟 4：設定所需的壓縮類型
`CompressionType` 列舉指定套用於 TAR 串流的壓縮演算法。  

`CompressionType` 列出支援的演算法（BZip2、GZip、LZMA、XZ 等），於儲存時套用。

### 步驟 5：儲存壓縮檔
`ArchiveFormat` 列舉選擇輸出檔案的容器與壓縮組合。  

呼叫 `Save` 會使用所選格式將壓縮檔寫入磁碟。

### 步驟 6：使用密碼解壓縮檔案
`ArchiveEntry` 代表壓縮檔內的單一檔案或目錄項目。  

要解壓受密碼保護的 zip，先開啟壓縮檔，找到每個 `ArchiveEntry`，為其設定 `Password` 屬性，然後呼叫 `Extract`。`Password` 屬性用於設定 zip 項目的解密密碼。此每項目密碼模型允許您在同一 zip 中保護個別檔案。

### 步驟 7：驗證結果
解壓後，比較檔案大小與 SHA‑256 雜湊值，以確認壓縮檔往返過程中資料完整性未受影響。

## 常見使用情境
- **Backup utilities** – 將每日備份儲存為 `.tar.bz2`，可降低最高 30 % 的儲存成本。  
- **Cross‑platform data exchange** – Tar 系列格式被 Linux、macOS 與 Windows 工具原生支援。  
- **Secure distribution** – 為敏感項目設定密碼，滿足合規需求，且不需額外加密工具。

## 疑難排解與技巧
- **Large archives** – 使用串流 API（`Archive.CreateEntryFromFile`）以降低記憶體使用。  
- **Password mismatches** – 每個 `ArchiveEntry` 設定的密碼必須完全相符，否則會拋出 `InvalidPasswordException`。  
- **Compression level** – BZIP2 不提供自訂等級；若需更細緻的控制，可改用 LZMA（`CompressionType.LZMA`）或 XZ（`CompressionType.XZ`）。

## 常見問答

**Q: How do I create a TarGz archive?**  
A: 設定 `CompressionType.GZip`，在呼叫 `Save` 時使用 `ArchiveFormat.TarGz`。即可一次產生 `.tar.gz` 檔案。

**Q: Can I extract a password‑protected archive without knowing the password?**  
A: 不行。每個項目必須提供正確的密碼，否則解壓會因 `InvalidPasswordException` 失敗。

**Q: Does Aspose.Zip support extracting archives with different passwords per entry?**  
A: 可以。於呼叫 `Extract` 前，為每個 `ArchiveEntry` 個別設定密碼。

**Q: Which format gives the best compression?**  
A: 通常 TarBz2 產生最小的檔案大小，其次是 TarLz 與 TarXz。TarGz 提供較快且仍具效能的替代方案。

**Q: Is there a limit to the number of files I can add to a TAR archive?**  
A: 實際上沒有限制，但極大型的壓縮檔（>10 GB）可能需要分割成多個部分以便處理。

## 壓縮與解壓縮格式教學
### [使用 Aspose.Zip for .NET 壓縮檔案至 TarBz2](./compress-to-tar-bz2/)
了解如何在 .NET 使用 Aspose.Zip 將檔案壓縮為 TarBz2 格式。遵循我們的步驟指南以實現高效的檔案壓縮。  
### [使用 Aspose.Zip for .NET 壓縮至 TarGz](./compress-to-tar-gz/)
探索在 .NET 使用 Aspose.Zip 進行高效檔案壓縮。輕鬆壓縮為 TarGz。  
### [使用 Aspose.Zip for .NET 壓縮至 TarLz](./compress-to-tar-lz/)
在 .NET 使用 Aspose.Zip 輕鬆壓縮檔案。學習一步步建立 TarLz 壓縮檔。  
### [使用 Aspose.Zip for .NET 壓縮至 TarXz](./compress-to-tar-xz/)
了解如何在 .NET 使用 Aspose.Zip 將檔案壓縮為 TarXz 格式。遵循我們的指南以實現高效的儲存與傳輸。  
### [使用 Aspose.Zip for .NET 壓縮至 TarZ](./compress-to-tar-z/)
探索使用 Aspose.Zip for .NET 步驟式壓縮至 TarZ。為您的 .NET 專案提供高效的檔案處理。  
### [在 Aspose.Zip for .NET 中以不同密碼解壓縮檔案項目](./extract-archive-different-passwords/)
了解如何在 Aspose.Zip for .NET 中以不同密碼解壓縮檔案項目。提升應用程式的安全性與彈性。

## 相關教學

- [使用 Aspose.Zip for .NET 建立 tar 壓縮檔並加入檔案](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [如何使用 Aspose.Zip for .NET 壓縮 tar 並建立 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [使用 Aspose.Zip 加入檔案至 tar 並建立 tarxz 壓縮檔](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**最後更新：** 2026-10-25  
**測試環境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}