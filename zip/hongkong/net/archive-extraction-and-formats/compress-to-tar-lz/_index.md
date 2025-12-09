---
date: 2025-12-01
description: 學習如何在 .NET 中使用 Aspose.Zip 壓縮 tar.lz 檔案，輕鬆建立 tar.lz 壓縮檔。
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

在現代 .NET 開發中，有效地打包檔案可以顯著減少部署大小並加快網路傳輸時間。**How to compress tar.lz** 是在需要輕量級、LZ 壓縮的 TAR 壓縮檔時的常見需求。在本教學中，我們將使用 Aspose.Zip 函式庫逐步說明一個清晰的 **tar.lz compression example**，讓您能快速在自己的應用程式中建立 tar.lz 壓縮檔。

## 快速解答
- **應該使用哪個函式庫？** Aspose.Zip for .NET.
- **實作需要多長時間？** 基本範例約 5‑10 分鐘。
- **需要授權嗎？** 免費試用可用於測試；正式環境需購買商業授權。
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **可以一次壓縮多個檔案嗎？** 可以 – 在儲存前只需加入更多條目。

## 什麼是 tar.lz 壓縮？
`tar.lz` 是使用 LZMA 演算法（常簡稱為 **LZ**）壓縮的 TAR 壓縮檔。它結合了 TAR 的檔案分組簡易性與 LZ 的高壓縮比，適用於備份檔案、套件發佈或任何對頻寬有要求的情境。

## 為什麼使用 Aspose.Zip for .NET？
Aspose.Zip 抽象化了壓縮檔建立的底層細節，提供乾淨的物件導向 API。您將獲得：

* **Zero external dependencies** – 純 .NET 實作。  
* **Cross‑platform support** – 可在 Windows、Linux 與 macOS 上執行。  
* **Built‑in LZ compression** – 無需安裝額外的原生工具。  
* **Strong error handling** – 例外資訊具描述性，讓除錯更容易。

## 前置條件
在開始之前，請確保您已擁有：

- **Aspose.Zip for .NET** 函式庫 – 從 [here](https://releases.aspose.com/zip/net/) 下載。  
- 包含欲壓縮檔案的資料夾。此資料夾路徑將儲存在 `dataDir` 變數中（您會在第 3 步設定）。

## 匯入命名空間
加入必要的命名空間，讓編譯器知道要使用的類別所在位置。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 如何建立 tar.lz 壓縮檔 – 步驟指南

### 步驟 1：壓縮單一檔案
第一個範例示範最基本的情境 – 將單一檔案加入 TAR 壓縮檔，然後儲存為 **tar.lz** 檔案。

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**說明**

- `new TarArchive()` 建立一個空的 TAR 容器。  
- `CreateEntry` 從您的 `dataDir` 加入檔案 `alice29.txt`。  
- `SaveLzipped` 將壓縮檔寫入磁碟並套用 LZ 壓縮，產生 `archive.tar.lz`。

### 步驟 2：在同一壓縮檔中壓縮多個檔案
通常您需要一次打包多個檔案。只要在儲存前為每個檔案呼叫 `CreateEntry` 即可。

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

- 程式碼遵循與步驟 1 相同的模式，但加入第二個條目 (`lcet10.txt`)。  
- 您可以依需求多次呼叫 `CreateEntry`；函式庫會自動處理內部的 TAR 結構。

### 步驟 3：指定文件目錄
將佔位符替換為實際的來源檔案路徑。此路徑會被上述範例使用。

```csharp
string dataDir = "Your Document Directory";
```

**說明**

- 將 `dataDir` 設為完整的資料夾路徑，例如 `@"C:\MyFiles\"`。  
- 將目錄存於變數中可提升程式碼的可重用性與維護性。

## 常見問題與除錯
| 症狀 | 可能原因 | 解決方法 |
|---------|--------------|-----|
| 執行範例時出現 `FileNotFoundException` | `dataDir` 指向不存在的資料夾或檔名拼寫錯誤 | 確認路徑與檔名正確；建議使用 `Path.Combine` 以確保安全。 |
| 輸出檔案為 **0 KB** | `archive.SaveLzipped` 在加入任何條目之前就被呼叫 | 確保至少有一次 `CreateEntry` 呼叫在 `SaveLzipped` 之前。 |
| 壓縮速度似乎很慢 | 使用預設緩衝區大小處理大型檔案 | 若效能關鍵，可考慮分塊處理檔案或使用非同步 I/O。 |

## 結論
現在您已了解如何使用 Aspose.Zip for .NET **壓縮 tar.lz** 檔案，無論是單一文件或是多個文件的集合。此 **tar.lz compression example** 展示了一種簡潔且適合正式環境的方式，建立輕量級的壓縮檔，便於傳輸或儲存。

## 常見問答

**Q:** 使用 Aspose.Zip for .NET 能壓縮任何大小的檔案嗎？  
**A:** 可以，函式庫能處理小檔案與極大檔案；只需確保有足夠的記憶體與磁碟空間供暫存的 TAR 結構使用。

**Q:** 程式碼是否相容於最新的 Aspose.Zip 版本？  
**A:** 此範例針對目前版本；請務必保持 NuGet 套件為最新，以取得錯誤修正與新功能。

**Q:** 有授權方面的考量嗎？  
**A:** 正式環境需購買商業授權。授權細節請參閱 [Aspose website](https://purchase.aspose.com/buy)。

**Q:** 可以在商業專案中使用嗎？  
**A:** 當然可以 – 只要取得有效授權，即可將函式庫嵌入任何商業應用程式。

**Q:** 若遇到問題，該向哪裡尋求協助？  
**A:** 前往 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 取得社群支援與官方協助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-01  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose