---
date: 2026-02-20
description: 學習如何壓縮 tarbz2 檔案、如何建立 targz 壓縮檔，以及使用 Aspose.Zip for .NET 進行 .NET 壓縮檔的解壓與受密碼保護的
  zip 解壓。提升儲存效率與安全性。
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮 TarBz2 檔案
url: /zh-hant/net/archive-extraction-and-formats/
weight: 23
---

 => "**測試環境：** Aspose.Zip for .NET 24.11"

**Author:** Aspose => "**作者：** Aspose"

Make sure bold formatting remains.

Now produce final content with all translations, preserving shortcodes.

Let's assemble.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮 TarBz2 檔案

## 介紹

在本指南中，您將學習 **如何壓縮 tarbz2 檔案** 使用 Aspose.Zip for .NET，同時了解如何建立 TarGz 壓縮檔以及執行 .net 壓縮檔的密碼保護 zip 檔案解壓縮。高效的檔案處理是現代 .NET 開發的基石，掌握這些格式可降低儲存成本、加快資料傳輸，並確保敏感資訊安全。無論您是構建備份服務、雲端儲存客戶端，或是資料處理管線，本指南所涵蓋的技術都能讓您的檔案管理工作更順暢、更可靠。

## 快速答案
- **什麼是 TarBz2？** 一種結合 TAR 打包與 BZIP2 壓縮的壓縮檔案，可提供高壓縮比。  
- **為什麼選擇 Aspose.Zip for .NET？** 它提供單一、流暢的 API，可在不依賴外部套件的情況下建立與解壓縮多種壓縮檔格式。  
- **我可以建立 TarGz 壓縮檔嗎？** 可以 – Aspose.Zip 支援 TarGz、TarLz、TarXz、TarZ 等多種格式。  
- **如何解壓縮受密碼保護的 zip 壓縮檔？** 在解壓縮時使用 `ArchiveEntry` 物件的 `Password` 屬性。  
- **生產環境需要授權嗎？** 生產環境需購買商業授權；可使用免費試用版進行評估。

## 如何壓縮 TarBz2 檔案
將檔案壓縮為 TarBz2 代表先將多個檔案與目錄打包成單一的 **TAR** 容器，然後再套用 **BZIP2** 壓縮。最終會得到一個 `.tar.bz2` 檔案，既易於傳輸又具高度壓縮率。

## 為什麼使用 Aspose.Zip for .NET 處理這些格式？
- **統一 API** – 單一函式庫支援多種格式（TarBz2、TarGz、TarLz、TarXz、TarZ）。  
- **無原生相依性** – 可直接在 Windows、Linux 與 macOS 上執行。  
- **密碼支援** – 可使用每個條目的密碼安全地保護與解壓縮壓縮檔。  
- **效能導向** – 基於串流的處理可減少記憶體佔用。

## 前置條件
- .NET 6.0 或更新版本（或 .NET Core 3.1+ / .NET Framework 4.5+）。  
- 已安裝 Aspose.Zip for .NET NuGet 套件（`Install-Package Aspose.Zip`）。  
- 具備 C# 與檔案 I/O 的基本概念。

## 步驟說明

### 步驟 1：選擇所需的壓縮檔格式
決定 **TarBz2**、**TarGz**、**TarLz**、**TarXz** 或 **TarZ** 哪一種最符合您的壓縮比與相容性需求。  
- **TarBz2** – 壓縮率最高，但處理較慢。  
- **TarGz** – 在速度與檔案大小之間取得良好平衡（涵蓋次要關鍵字 *how to create targz*）。  
- **TarZ** – 傳統格式，適用於與較舊的 Unix 工具相容。

### 步驟 2：建立新的 `Archive` 實例
實例化 `Archive` 類別並指向輸出檔案路徑。此物件將負責打包與壓縮的流程。

### 步驟 3：加入檔案與資料夾
使用 `AddAll` 或 `AddFile` 方法加入欲壓縮的檔案。透過加入基礎資料夾可保留目錄結構。

### 步驟 4：設定欲使用的壓縮類型
在儲存壓縮檔時指定壓縮演算法（`CompressionType.BZip2`、`CompressionType.GZip` 等）。此處即是實際 **將檔案壓縮為 TarBz2** 或其他格式的步驟。

### 步驟 5：儲存壓縮檔
呼叫 `Save` 並傳入相應的格式列舉值（`ArchiveFormat.TarBz2`、`ArchiveFormat.TarGz` 等）。函式庫會一次寫入 TAR 容器並套用選定的壓縮方式。

### 步驟 6：使用密碼解壓縮壓縮檔
若需 **使用不同密碼解壓縮壓縮檔條目**（次要關鍵字 *password protected zip extraction*），請開啟壓縮檔、定位每個條目、設定其密碼，然後執行解壓縮。

### 步驟 7：驗證結果
解壓縮後，比較檔案大小與校驗碼，以確保壓縮檔已正確建立與解壓。

## 常見使用情境
- **備份工具** – 將每日備份儲存為 `.tar.bz2` 以降低儲存成本。  
- **跨平台資料交換** – 基於 Tar 的格式在 Linux、macOS 與 Windows 上皆通用。  
- **安全分發** – 為個別條目設定密碼，以符合合規需求的環境。

## 疑難排解與技巧
- **大型壓縮檔** – 使用串流 API（`Archive.CreateEntryFromFile`）以避免將整個檔案載入記憶體。  
- **密碼不符** – 確認每個 `ArchiveEntry` 設定的密碼與解壓縮時使用的密碼相同，否則會拋出 `InvalidPasswordException`。  
- **不支援的壓縮等級** – BZIP2 不支援自訂壓縮等級；若需更細緻的控制，可考慮使用 TarLz 或 TarXz。

## 常見問題

**Q: 我如何建立 TarGz 壓縮檔？**  
A: 在呼叫 `Save` 時將壓縮類型設定為 `CompressionType.GZip`，格式設定為 `ArchiveFormat.TarGz`。

**Q: 我可以在不知道密碼的情況下解壓受密碼保護的壓縮檔嗎？**  
A: 不行。每個條目必須提供正確的密碼，否則解壓會失敗。

**Q: Aspose.Zip 是否支援對每個條目使用不同密碼解壓縮？**  
A: 支援。您可在解壓前為每個 `ArchiveEntry` 單獨設定密碼。

**Q: 哪種格式提供最佳壓縮率？**  
A: 通常 TarBz2 提供最高的壓縮比，其次是 TarLz 與 TarXz。TarGz 則在速度與大小之間取得良好平衡。

**Q: 加入 TAR 壓縮檔的檔案數量有限制嗎？**  
A: 實際上沒有，但極大型的壓縮檔可考慮分割成多個部分以便處理。

## 壓縮檔解壓與格式教學
### [使用 Aspose.Zip for .NET 壓縮檔案為 TarBz2](./compress-to-tar-bz2/)
Learn how to compress files to TarBz2 format in .NET using Aspose.Zip. Follow our step-by-step guide for efficient file compression.
### [使用 Aspose.Zip for .NET 壓縮為 TarGz](./compress-to-tar-gz/)
Explore efficient file compression in .NET with Aspose.Zip. Compress to TarGz effortlessly.
### [使用 Aspose.Zip for .NET 壓縮為 TarLz](./compress-to-tar-lz/)
Effortlessly compress files in .NET with Aspose.Zip. Learn to create TarLz archives step-by-step.
### [使用 Aspose.Zip for .NET 壓縮為 TarXz](./compress-to-tar-xz/)
Learn to compress files to TarXz format in .NET using Aspose.Zip. Follow our step-by-step guide for efficient file storage and transmission.
### [使用 Aspose.Zip for .NET 壓縮為 TarZ](./compress-to-tar-z/)
Explore step-by-step compression to TarZ using Aspose.Zip for .NET. Efficient file handling for your .NET projects.
### [在 Aspose.Zip for .NET 中使用不同密碼解壓縮條目](./extract-archive-different-passwords/)
Learn how to extract archive entries with different passwords in Aspose.Zip for .NET. Boost security and flexibility in your applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-20  
**測試環境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose