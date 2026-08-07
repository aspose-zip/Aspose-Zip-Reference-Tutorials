---
date: 2026-08-07
description: 了解如何在 .NET 中使用 Aspose.Zip 將檔案加入 tar 並產生 TarBz2 壓縮檔。一步一步的指南展示 tar 建立、Bzip2
  壓縮以及最佳實踐技巧。
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: 壓縮為 TarBz2
og_description: 在 .NET 中使用 Aspose.Zip 將檔案加入 tar 並產生 TarBz2 壓縮檔。本指南涵蓋 tar 建立、Bzip2
  壓縮及疑難排解技巧。
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: 將檔案加入 tar 並使用 Aspose.Zip 建立 TarBz2 壓縮檔
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: 將檔案加入 tar 並使用 Aspose.Zip 建立 TarBz2 壓縮檔
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 將檔案加入 tar 並建立 TarBz2 壓縮檔

在本教學中，您將學習如何使用 .NET 的 **Aspose.Zip** 程式庫，將檔案 **加入 tar** 壓縮檔並轉換為緊湊的 **TarBz2** 檔案。無論您是要建立備份工具、發佈部署套件，或是需要輕量級的分發包，以下步驟將指引您將檔案加入 tar 容器、套用 Bzip2 壓縮，並產生可直接分享的壓縮檔。

## 快速解答
- **我應該使用哪個程式庫？** Aspose.Zip for .NET  
- **實作需要多長時間？** 約 5‑10 分鐘  
- **需要授權嗎？** 正式環境需使用暫時授權；亦提供免費試用  
- **可以一次壓縮多個檔案嗎？** 可以——您可以在 tar 壓縮檔中加入任意多的項目  
- **是否相容於 .NET 6 以上？** 當然，Aspose.Zip 支援 .NET Framework 以及 .NET Core/5/6  

## 什麼是 TarBz2 壓縮檔？

TarBz2 檔案結合了傳統的 **tar** 容器（保留目錄結構與檔案中繼資料）與 **Bzip2** 壓縮，產生高度壓縮的 `.tar.bz2` 套件。此格式在類 Unix 系統中相當流行，因為它在壓縮率與解壓速度之間取得了良好的平衡。

## 為什麼使用 Aspose.Zip 壓縮檔案為 TarBz2？

Aspose.Zip 能在 **兩個 API 呼叫** 內產生 TarBz2 壓縮檔，且能有效處理串流。它支援 **超過 50 種壓縮與封存格式**，可處理高達 **2 GB** 的檔案而不需將整個壓縮檔載入記憶體，並可在 Windows、Linux 與 macOS 的 .NET 執行環境上執行。此程式庫亦提供對項目名稱、時間戳記與壓縮等級的細緻控制，適用於控制台工具與 Web 服務。

## 先決條件

- **Aspose.Zip for .NET** – 從官方網站下載最新套件：[https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **文件目錄** – 包含您欲封存檔案的資料夾。範例中以變數 `dataDir` 參照。

> **專業提示：** 請將來源檔案放在專用資料夾，以免不小心納入不需要的檔案。

## 匯入命名空間

首先，匯入所需的命名空間，以便存取 Aspose.Zip 的 Tar 與 Bzip2 類別。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步驟 1：設定文件目錄

定義指向存放欲封存檔案之資料夾的路徑。

```csharp
string dataDir = "Your Document Directory";
```

> 將 `"Your Document Directory"` 替換為指向來源資料夾的絕對或相對路徑。

## 步驟 2：將檔案加入 tar 並建立 TarBz2 壓縮檔

`TarArchive` 代表一個記憶體中的 tar 容器，可容納多個檔案項目。  
`Bzip2Archive` 使用 Bzip2 演算法壓縮串流。  
`CreateEntry` 方法將檔案作為新項目加入 tar 壓縮檔。

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **將檔案加入 tar** – 您可以對每個需要的檔案呼叫此方法。  
- `bz2.SetSource(archive)` 告訴 Bzip2 壓縮檔壓縮整個 tar 串流。  
- `bz2.Save(...)` 將最終的 **TarBz2** 檔案寫入磁碟。

**提示：** 若要批次 **將檔案加入 tar**，只需在呼叫 `bz2.Save` 前，對每個檔案重複執行 `archive.CreateEntry`。

## 如何將檔案加入 tar？

載入來源目錄，建立 `TarArchive` 實例，使用 `CreateEntry` 加入每個檔案，然後將 tar 串流包裝於 `Bzip2Archive` 並呼叫 `Save`。此兩步驟模式可加入任意數量的檔案，並在單一流暢的過程中產生 `.tar.bz2` 檔案，免除暫存檔或外部工具的需求。

## 常見問題與解決方案

| Issue | Reason | Fix |
|-------|--------|-----|
| **找不到檔案** 錯誤 | `dataDir` 路徑錯誤或缺少檔案副檔名 | 核對完整路徑並確認檔案存在。 |
| **空的壓縮檔** | 在 `bz2.Save` 之前未加入任何項目 | 至少呼叫一次 `CreateEntry`。 |
| **權限被拒** | 應用程式沒有寫入輸出資料夾的權限 | 以適當權限執行應用程式或選擇可寫入的目錄。 |

## 常見問與答

**Q: Aspose.Zip 是否相容於所有 .NET 應用程式？**  
A: 是的。它支援 .NET Framework、.NET Core、.NET 5/6 以及更新的執行環境。

**Q: 我可以同時壓縮多個檔案嗎？**  
A: 當然可以。在儲存壓縮檔之前，對每個檔案呼叫 `CreateEntry`。

**Q: 我在哪裡可以找到更多文件？**  
A: 詳細文件可於 **Aspose.Zip .NET API 參考** 中取得：[Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: 如何取得 Aspose.Zip 的暫時授權？**  
A: 您可以在此 **申請暫時授權**：[request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: 是否提供免費試用？**  
A: 有，您可 **從 Aspose 釋出頁面下載試用版**：[download a trial version](https://releases.aspose.com/).

## 結論

您現在已了解 **如何將檔案加入 tar**，使用 Bzip2 壓縮 tar 串流，並透過 Aspose.Zip for .NET 產生 **TarBz2** 壓縮檔。此方法快速、記憶體效能佳，且可在所有現代 .NET 平台上運作。歡迎嘗試更大的檔案集合、自訂項目名稱，或將程式碼整合至您自己的備份或部署流程中。

若遇到任何問題，Aspose.Zip 社群隨時提供協助——只要前往 **Aspose.Zip 支援論壇**： [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37)。

**最後更新：** 2026-08-07  
**測試環境：** Aspose.Zip for .NET (latest release)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Zip for .NET 建立 tar 壓縮檔並加入檔案](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [使用 Aspose.Zip 將檔案加入 tar 並建立 tarxz 壓縮檔](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [使用 Aspose.Zip for .NET 將檔案加入 tar 並壓縮為 TarZ](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}