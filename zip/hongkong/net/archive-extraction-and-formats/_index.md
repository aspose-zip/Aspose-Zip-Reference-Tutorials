---
date: 2026-01-28
description: 學習如何使用 Aspose.Zip for .NET 解壓帶密碼的壓縮檔、將檔案壓縮為 TarBz2、建立 TarGz 壓縮檔。提升儲存效率與安全性。
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用密碼解壓縮並壓縮為 TarBz2 (.NET)
url: /zh-hant/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用密碼解壓縮檔案並壓縮為 TarBz2 (.NET)

在本指南中，您將學會 **如何使用密碼解壓縮檔案**，以及掌握 **使用 Aspose.Zip for .NET 壓縮檔案為 TarBz2** 的技巧。無論您是在構建備份服務、雲端儲存客戶端，或是資料處理管線，這些技術都能幫助您減少儲存空間、加速傳輸，並確保敏感資料受到保護。

## 快速回答
- **什麼是 TarBz2？** 一種結合 TAR 打包與 BZIP2 壓縮的壓縮檔案，具備高壓縮比。  
- **為什麼選擇 Aspose.Zip for .NET？** 它提供單一、流暢的 API，支援多種壓縮格式，且無需本機依賴。  
- **我可以建立 TarGz 壓縮檔嗎？** 可以 – Aspose.Zip 支援 TarGz、TarLz、TarXz、TarZ 等多種格式。  
- **如何解壓受密碼保護的檔案？** 在解壓前，於每個 `ArchiveEntry` 設定 `Password` 屬性。  
- **正式環境需要授權嗎？** 生產環境必須購買商業授權，亦提供免費試用版供評估。

## 使用 Aspose.Zip for .NET 解壓受密碼保護的檔案
解壓 **受密碼保護的 zip 檔案** 非常簡單。您只需開啟壓縮檔、定位目標條目、指定其密碼，然後呼叫 `Extract`。此方式同樣適用於 TarBz2、TarGz 以及其他支援的格式。

## 「壓縮檔案為 TarBz2」實際是什麼意思？
將檔案壓縮為 TarBz2，首先會把多個檔案與目錄打包成單一的 **TAR** 容器，接著套用 **BZIP2** 壓縮。最終產生的 `.tar.bz2` 檔案既易於傳輸，又具高度壓縮率。

## 為什麼使用 Aspose.Zip for .NET 處理這些格式？
- **統一 API** – 一個函式庫支援多種格式（TarBz2、TarGz、TarLz、TarXz、TarZ）。  
- **無本機依賴** – 可直接在 Windows、Linux、macOS 上執行。  
- **密碼支援** – 可為每個條目設定獨立密碼，安全保護與解壓。  
- **效能導向** – 基於串流的處理方式降低記憶體使用。

## 前置條件
- .NET 6.0 或更新版本（或 .NET Core 3.1+ / .NET Framework 4.5+）。  
- 已安裝 Aspose.Zip for .NET NuGet 套件（`Install-Package Aspose.Zip`）。  
- 具備 C# 與檔案 I/O 的基本知識。

## 步驟說明

### 步驟 1：選擇需要的壓縮格式
決定使用 **TarBz2**、**TarGz**、**TarLz**、**TarXz** 或 **TarZ**，以符合壓縮比與相容性需求。  
- **TarBz2** – 壓縮率最高，處理較慢。  
- **TarGz** – 在速度與檔案大小之間取得良好平衡（涵蓋次要關鍵字 *compress files to targz*）。  
- **TarZ** – 老舊 Unix 工具的傳統格式。

### 步驟 2：建立新的 `Archive` 實例
實例化 `Archive` 類別，並指向輸出檔案路徑。此物件負責打包與壓縮的全部流程。

### 步驟 3：加入檔案與資料夾
使用 `AddAll` 或 `AddFile` 方法加入欲壓縮的檔案。透過加入基礎資料夾，可保留目錄結構。

### 步驟 4：設定欲使用的壓縮類型
在儲存壓縮檔時指定壓縮演算法（`CompressionType.BZip2`、`CompressionType.GZip` 等）。此步驟即為 **compress files to tarbz2** 或其他格式的實作。

### 步驟 5：儲存壓縮檔
呼叫 `Save`，並傳入相應的格式列舉值（`ArchiveFormat.TarBz2`、`ArchiveFormat.TarGz` 等）。函式庫會一次性寫入 TAR 容器並套用選定的壓縮。

### 步驟 6：使用密碼解壓縮檔案
若需 **extract archive entries with different passwords**（次要關鍵字 *how to extract password protected archive*），開啟壓縮檔、定位每個條目、設定其密碼，然後執行解壓。

### 步驟 7：驗證結果
解壓後比對檔案大小與雜湊值，確保壓縮與解壓皆正確無誤。

## 常見使用情境
- **備份工具** – 將每日備份儲存為 `.tar.bz2`，降低儲存成本。  
- **跨平台資料交換** – Tar 系列格式在 Linux、macOS 與 Windows 上皆通用。  
- **安全發佈** – 為個別條目設定密碼，符合合規需求的分發方式。

## 疑難排解與小技巧
- **大型壓縮檔** – 使用串流 API（`Archive.CreateEntryFromFile`）避免一次載入整個檔案至記憶體。  
- **密碼不符** – 確認每個 `ArchiveEntry` 設定的密碼與解壓時使用的相同，否則會拋出 `InvalidPasswordException`。  
- **不支援自訂壓縮等級** – BZIP2 不提供自訂壓縮等級；若需更細緻的控制，可考慮 TarLz 或 TarXz。  
- **效能建議** – 建立 **create tarbz2 archive** 時，於底層串流啟用緩衝，可提升寫入速度。

## 常見問答

**Q: 如何建立 TarGz 壓縮檔？**  
A: 在呼叫 `Save` 時，將壓縮類型設為 `CompressionType.GZip`，格式設為 `ArchiveFormat.TarGz`。

**Q: 能否在不知道密碼的情況下解壓受密碼保護的檔案？**  
A: 不能。每個條目必須提供正確的密碼，否則解壓會失敗。

**Q: Aspose.Zip 是否支援對不同條目設定不同密碼的解壓？**  
A: 支援。您可以在解壓前為每個 `ArchiveEntry` 個別設定密碼。

**Q: 哪種格式的壓縮率最高？**  
A: TarBz2 通常提供最高的壓縮比，其次是 TarLz 與 TarXz。TarGz 在速度與大小之間取得平衡。

**Q: TAR 壓縮檔能加入的檔案數量有限制嗎？**  
A: 實務上沒有明顯限制，但極大型的壓縮檔建議分割成多個部分，以便於處理。

## 壓縮與解壓教學
### [File Compressing to TarBz2 with Aspose.Zip for .NET](./compress-to-tar-bz2/)
了解如何在 .NET 中使用 Aspose.Zip 將檔案壓縮為 TarBz2 格式，並跟隨步驟完成高效壓縮。

### [Compressing to TarGz with Aspose.Zip for .NET](./compress-to-tar-gz/)
探索在 .NET 中使用 Aspose.Zip 輕鬆壓縮為 TarGz 的方法。

### [Compressing to TarLz with Aspose.Zip for .NET](./compress-to-tar-lz/)
在 .NET 中使用 Aspose.Zip 無縫建立 TarLz 壓縮檔，步驟說明完整。

### [Compressing to TarXz with Aspose.Zip for .NET](./compress-to-tar-xz/)
學習如何在 .NET 中使用 Aspose.Zip 壓縮檔案為 TarXz，提升儲存與傳輸效率。

### [Compressing to TarZ with Aspose.Zip for .NET](./compress-to-tar-z/)
透過 Aspose.Zip for .NET，逐步完成 TarZ 壓縮，適用於 .NET 專案的檔案處理。

### [Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET](./extract-archive-different-passwords/)
學會在 Aspose.Zip for .NET 中以不同密碼解壓縮條目，提升應用程式的安全性與彈性。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-28  
**測試環境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

---