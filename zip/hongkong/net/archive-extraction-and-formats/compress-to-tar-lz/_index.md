---
date: 2026-02-02
description: 學習如何在 .NET 中使用 Aspose.Zip 壓縮 tar.lz 檔案——一步步指南，教您輕鬆壓縮 tar.lz 壓縮檔。
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮 tar.lz
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮 tar.lz

在現代 .NET 開發中，有效地打包檔案可以大幅減少部署體積與網路傳輸時間。**如何壓縮 tar.lz** 是在需要輕量、LZ 壓縮的 TAR 壓縮檔時的常見需求。本教學將逐步說明使用 Aspose.Zip 函式庫的 **tar.lz 壓縮範例**，讓您能快速在自己的應用程式中建立 tar.lz 壓縮檔。

## 快速答覆
- **應該使用哪個函式庫？** Aspose.Zip for .NET。  
- **實作需要多久？** 基本範例約 5‑10 分鐘即可完成。  
- **需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權。  
- **支援哪些 .NET- **可以一次壓縮多個檔案嗎？** 可以 – 在儲存前加入更多條目即可。

## 什麼是 tar.lz 壓縮？
`tar.lz` 是使用 LZMA 演算法（通常簡稱 **LZ**）壓縮的 TAR 壓縮檔。它結合了 TAR 簡易的檔案分組方式與 LZ 的高壓縮比，適合備份、套件發佈或任何對頻寬有要求的情境。

## 為什麼選擇 Aspose.Zip for .NET？
Aspose.Zip 抽象化了壓縮檔建立的底層細節，提供乾外部相依** – 完全以 .NET 實作。  
* **跨平台支援** – 可在 Windows、Linux 與 macOS 上執行。  
* **內建 LZ 壓縮** – 不需額外安裝原生工具。  
* **完善的錯誤處理** – 例外訊息具描述性，除錯更輕鬆。

## 前置作業
在開始之前，請確保您已具備：

- **Aspose.Zip for .NET** 函式庫 – 從 [此處](https://releases.aspose.com/zip/net/) 下載。  
- 一個包含欲壓縮檔案的資料夾。此資料夾路徑將存於 `dataDir` 變數（於第 3 步設定）。

## 匯入命名空間
加入必要的命名空間，讓編譯器能找到我們將使用的類別。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 使用 Aspose.Zip 壓縮 tar.lz – 步驟說明

### 步驟 1：建立 tar.lz 壓縮檔 – 壓縮單一檔基本的情況 – 將一個檔案加入 TAR 壓縮檔，然後儲存為 **tar.lz**。

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
dataDir`）加入檔案。  
- `SaveLzipped` 會將壓縮檔寫入磁碟並套用 LZ 壓縮，產生 `archive.tar.lz`。

### 步驟 2：壓縮多個檔案 tar.lz – 新增多筆條目
通常需要一次打包多個檔案，只要在儲存前對每個檔案呼叫 `CreateEntry` 即可。

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

- 程式碼與步驟 1Entry` 任意次數；函式庫會自動處理內部的 TAR 結構。

### 步驟 3：指定文件目錄 – 設定 tar.lz 壓縮檔的建立路徑
將佔位符替換為實際的來源檔案所在路徑。此路徑會在上述範例中使用。

```csharp
string dataDir = "Your Document Directory";
```

**說明**

- 將 `dataDir` 設為完整的資料夾路徑，例如 `@"C:\MyFiles\"`。  
- 將目錄存於變數中，可提升程式碼的可重用性與---------|--------------|-----|
| 執行範例時出現 `FileNotFoundException` | `dataDir` 指向不存在的資料夾或檔名拼寫錯誤 | 檢查路徑與檔名；建議使用 `Path.Combine` 以確保正確性。 |
| 輸出檔案為 **0 KB** | 在加入任何條目之前就呼叫了 `archive.SaveLzipped` | 確認至少有一次 `CreateEntry` 呼叫在 `SaveLzipped` 之前。 |
| 壓縮速度緩慢 | 大檔案使用預設緩衝區大小 | 若效能關鍵，可考慮分塊處理或使用非同步 I/O。 |

## 常見問答

**Q:** 可以使用 Aspose.Zip for .NET 壓縮任意大小的檔案嗎？  
**A:** 可以，函式庫支援小檔案與極大檔案；只要確保有足夠的記憶體與磁碟空間供暫存的 TAR 結構使用。

**Q:** 程式碼針對目前最新版本撰寫；建議定期更新 NuGet 套件以取得錯誤修正與新功能。

**Q:** 授權方面有什麼需要注意的？  
**A:** 正式上線必須購買商業授權。詳情請參閱 [Aspose 官方網站](https://purchase.aspose.com/buy) 的授權說明。

**Q:** 可以在商業專案中使用嗎？  
**A:** 完全可以 – 取得有效授權後，即可將函式庫嵌入任何商業應用程式。

**Q:** 若遇到問題該向哪裡尋求協助？  
**A:** 前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 取得社群與官方的支援。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-02  
**測試環境：** Aspose.Zip for .NET（最新發行版）  
**作者：** Aspose  

---