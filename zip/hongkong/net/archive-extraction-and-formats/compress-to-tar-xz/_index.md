---
date: 2025-12-04
description: 學習如何使用 Aspose.Zip 在 .NET 中執行 Aspose Zip 壓縮，將檔案加入 tar 壓縮檔並建立 TarXz 檔案。請遵循我們的逐步指南，以實現高效的儲存與傳輸。
language: zh-hant
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose Zip 壓縮：使用 Aspose.Zip for .NET 壓縮為 TarXz
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Zip Compression：使用 Aspose.Zip for .NET 壓縮為 TarXz

## 介紹

在 .NET 開發領域，**aspose zip compression** 是一項關鍵技術，可同時優化儲存空間與資料傳輸速度。無論是建立備份服務、透過網路傳送資產，或只是歸檔日誌，能有效壓縮檔案都能帶來顯著差異。本教學將逐步說明如何 **add files tar archive**，並使用 Aspose.Zip 函式庫產生 TarXz 套件。

## 快速答覆
- **哪個函式庫負責壓縮？** Aspose.Zip for .NET  
- **範例產生哪種格式？** `archive.tar.xz` (TarXz)  
- **開發時需要授權嗎？** 測試可使用臨時授權；正式上線必須購買正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7  
- **實作大約需要多久？** 基本壓縮約 5‑10 分鐘即可完成  

## 什麼是 Aspose Zip Compression？

Aspose Zip compression 是 Aspose.Zip for .NET 函式庫提供的一組 API，讓您能以程式方式建立、讀取與修改各種封存檔（ZIP、TAR、GZIP、XZ 等）。此函式庫抽象化了壓縮串流的底層細節，提供乾淨的物件導向介面來操作封存檔。

## 為什麼要使用 TarXz 搭配 Aspose Zip Compression？

* **高壓縮比** – XZ 採用 LZMA2 演算法，通常比一般 GZIP 產生更小的檔案。  
* **跨平台相容性** – TarXz 在 Linux、macOS 與 Windows 上皆廣受支援。  
* **簡化 API** – 使用 Aspose.Zip，您只需幾行程式碼即可建立 TAR 容器並壓縮為 XZ。  

## 前置條件

在開始之前，請確保您已具備以下項目：

- 已安裝 **Aspose.Zip for .NET**。可從官方 [Aspose.Zip documentation page](https://reference.aspose.com/zip/net/) 下載。  
- 您的機器上有一個資料夾，內含欲壓縮的檔案。程式碼範例中以 `dataDir` 變數指向該資料夾。

## 匯入 Aspose Zip Compression 的命名空間

這些命名空間提供 TAR 與 XZ 功能的存取。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 步驟說明

### 步驟 1：建立 TarXz 封存檔

我們先建立 TAR 容器，然後再以 XZ 進行壓縮。

#### 1.1 初始化 TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
```

#### 1.2 新增檔案至封存檔 – 如何 **add files tar archive**

`CreateEntry` 方法會將每個檔案加入 TAR 容器。此處透過指定條目名稱與來源檔案路徑來 **add files tar archive**。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

#### 1.3 使用 XZ 壓縮並儲存封存檔

最後，我們指示 Aspose.Zip 使用 XZ 壓縮 TAR 資料，並將結果寫入磁碟。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

以上就是全部步驟——只需三個簡潔的呼叫，即可得到完整壓縮的 TarXz 檔案。

### 常見問題與技巧

- **檔案路徑** – 確保 `dataDir` 以路徑分隔符（`\` 或 `/`）結尾，避免產生錯誤路徑。  
- **大型檔案** – 若來源檔案非常大，建議使用串流方式處理，而非一次載入全部；Aspose.Zip 支援基於串流的條目建立。  
- **授權** – 若未使用有效授權執行程式，函式庫會以評估模式運作，可能在輸出檔案中加入浮水印。

## 結論

本教學示範了如何利用 **aspose zip compression** 來 **add files tar archive**，並以幾行 C# 程式碼產生 TarXz 套件。將這些步驟整合至您的 .NET 應用程式，即可獲得高效、跨平台的封存功能，降低儲存成本並提升傳輸效能。

## 常見問答

**Q: Aspose.Zip 是否相容所有 .NET 環境？**  
A: 是，Aspose.Zip 支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6/7。詳情請參閱 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: 您可於此處申請臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

**Q: 是否有更多 Aspose.Zip 的範例？**  
A: 當然。官方文件提供豐富的範例，涵蓋 ZIP、TAR、GZIP、XZ 等多種使用情境。請參考 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 哪裡可以取得支援或討論 Aspose.Zip 的問題？**  
A: 社群論壇是提問的好地方：[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)。

**Q: 我可以先免費試用 Aspose.Zip 嗎？**  
A: 可以，您可於此處下載免費試用版 [here](https://releases.aspose.com/zip/net)。

---

**最後更新：** 2025-12-04  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}