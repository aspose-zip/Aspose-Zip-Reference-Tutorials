---
date: 2026-02-23
description: 學習如何使用 Aspose.Zip for .NET 壓縮多個檔案為 tar，並高效地建立 tar.lz 壓縮檔。
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮多個檔案為 tar
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮多個檔案為 tar

在現代 .NET 開發中，有效地打包檔案可以大幅減少部署大小與網路傳輸時間。**Compress multiple files tar** 是在需要輕量、LZ 壓縮的 TAR 壓縮檔以作備份、發佈或雲端上傳時的常見需求。在本教學中，我們將逐步說明使用 Aspose.Zip 函式庫的 **tar.lz 壓縮範例**，讓您能快速在自己的應用程式中建立 **tar.lz 壓縮檔**。

## 快速回答
- **我應該使用哪個函式庫？** Aspose.Zip for .NET.  
- **實作需要多長時間？** 基本範例約 5‑10 分鐘。  
- **需要授權嗎？** 免費試用可用於測試；正式環境需商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **可以一次壓縮多個檔案嗎？** 可以 – 在儲存前只要多加條目即可。

## 如何壓縮多個檔案為 tar
本節直接回應主要關鍵字，示範使用 Aspose.Zip 進行 **compress multiple files tar** 的完整步驟。此方法適用於任意數量的檔案，且可輕鬆套用至您自己的資料夾結構。

## 什麼是 tar.lz 壓縮？
`tar.lz` 是使用 LZMA 演算法（常簡稱為 **LZ**）壓縮的 TAR 壓縮檔。它結合了 TAR 的檔案分組簡易性與 LZ 的高壓縮比，十分適合備份檔案、套件發佈或任何對頻寬有要求的情境。

## 為什麼使用 Aspose.Zip for .NET？
* **零外部相依性** – 純 .NET 實作。  
* **跨平台支援** – 可在 Windows、Linux 與 macOS 上執行。  
* **內建 LZ 壓縮** – 無需安裝額外的原生工具。  
* **完善的錯誤處理** – 例外資訊具描述性，讓除錯更容易。

## 前置條件
在開始之前，請確保您已具備：

- **Aspose.Zip for .NET** 函式庫 – 從 [here](https://releases.aspose.com/zip/net/) 下載。  
- 一個包含欲壓縮檔案的資料夾。此資料夾路徑將儲存在 `dataDir` 變數中（會在第 3 步設定）。

## 匯入命名空間
加入必要的命名空間，讓編譯器能找到我們將使用的類別。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 如何建立 tar.lz 壓縮檔 – 步驟指南

### 步驟 1：壓縮單一檔案
第一個範例示範最基本的情況 – 將單一檔案加入 TAR 壓縮檔，然後儲存為 **tar.lz** 檔案。

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**說明**

- `new TarArchive()` 會建立一個空的 TAR 容器。  
- `CreateEntry` 會將 `dataDir` 中的 `alice29.txt` 檔案加入。  
- `SaveLzipped` 將壓縮檔寫入磁碟並套用 LZ 壓縮，產生 `archive.tar.lz`。

### 步驟 2：在同一壓縮檔中壓縮多個檔案
通常您需要將多個檔案打包在一起。只要在儲存前對每個檔案呼叫 `CreateEntry` 即可。此範例示範 **add files to tar lz** 並有效地 **compress multiple files tar**。

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**說明**

- 程式碼與步驟 1 相同，但加入第二個條目 (`lcet10.txt`)。  
- 您可以根據需要多次呼叫 `CreateEntry`；函式庫會自動處理內部的 TAR 結構。

### 步驟 3：指定文件目錄
將佔位符替換為實際的來源檔案所在路徑。上述範例會使用此路徑。

```csharp
string dataDir = "Your Document Directory";
```

**說明**

- 將 `dataDir` 設為完整的資料夾路徑，例如 `@\"C:\\MyFiles\\\"`。  
- 將目錄存於變數可提升程式碼的可重用性與維護性。

## 常見問題與除錯
| 症狀 | 可能原因 | 解決方法 |
|------|----------|----------|
| 執行範例時出現 `FileNotFoundException` | `dataDir` 指向不存在的資料夾或檔名拼寫錯誤 | 核對路徑與檔名；建議使用 `Path.Combine` 以確保安全。 |
| 輸出檔案為 **0 KB** | 在加入任何條目之前就呼叫了 `archive.SaveLzipped` | 確保至少有一次 `CreateEntry` 呼叫在 `SaveLzipped` 之前。 |
| 壓縮速度似乎很慢 | 使用預設緩衝區大小處理大型檔案 | 若性能關鍵，可考慮分塊處理檔案或使用非同步 I/O。 |

## 結論
現在您已了解如何使用 Aspose.Zip for .NET **壓縮 tar.lz** 檔案，無論是單一文件或多個檔案的集合。此 **tar.lz 壓縮範例** 展示了一種乾淨、可投入生產的方式來 **建立 tar lz 壓縮檔**，便於傳輸或儲存。

## 常見問答

**Q:** 使用 Aspose.Zip for .NET 可以壓縮任何大小的檔案嗎？  
**A:** 可以，函式庫支援小檔案與極大檔案；只要確保有足夠的記憶體與磁碟空間供暫存的 TAR 結構使用。

**Q:** 這段程式碼與最新的 Aspose.Zip 版本相容嗎？  
**A:** 範例針對目前版本撰寫；請務必保持 NuGet 套件為最新，以取得錯誤修正與新功能。

**Q:** 有授權方面的考量嗎？  
**A:** 正式環境需購買商業授權。授權細節請參閱 [Aspose 官方網站](https://purchase.aspose.com/buy)。

**Q:** 可以在商業專案中使用嗎？  
**A:** 當然可以 – 只要取得有效授權，即可將函式庫嵌入任何商業應用程式。

**Q:** 若遇到問題該向何處尋求協助？  
**A:** 前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 取得社群支援與官方協助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-23  
**測試環境：** Aspose.Zip for .NET（最新發行版）  
**作者：** Aspose