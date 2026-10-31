---
date: 2026-10-31
description: 了解如何在 .NET 中使用 Aspose.Zip 建立 tar 檔案並壓縮為 TarBz2 檔案。逐步指南說明 tar 建立、Bzip2
  壓縮以及最佳實踐技巧。
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: 壓縮為 TarBz2
og_description: 了解如何使用 Aspose.Zip for .NET 建立 tar 檔案並壓縮為 TarBz2 檔案。逐步指南涵蓋 tar 建立、Bzip2
  壓縮以及最佳實踐技巧。
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: 使用 .NET 建立 tar 檔案並壓縮為 TarBz2
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
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
title: 如何使用 .NET 建立 tar 檔案並壓縮為 TarBz2
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 .NET 建立 tar 檔案並壓縮為 TarBz2

在本教學中，您將學習 **如何建立 tar 檔案**，然後使用 **Aspose.Zip** .NET 函式庫將其壓縮成緊湊的 **TarBz2** 套件。無論您是建立備份工具、準備部署套件，或需要輕量級的發佈格式，以下步驟將指導您將檔案加入 tar 容器、套用 Bzip2 壓縮，並寫入最終的 `.tar.bz2` 檔案。

## 快速解答
- **應該使用哪個函式庫？** Aspose.Zip for .NET  
- **實作需要多長時間？** 約 5‑10 分鐘  
- **需要授權嗎？** 需要臨時授權才能投入生產；提供免費試用版  
- **可以壓縮多個檔案嗎？** 可以 – 任意新增條目至 tar 壓縮檔  
- **是否相容於 .NET 6 以上？** 絕對相容，Aspose.Zip 支援 .NET Framework 與 .NET Core/5/6  

## 什麼是 TarBz2 壓縮檔？

TarBz2 檔案結合了傳統的 **tar** 容器（保留目錄結構與檔案中繼資料）與 **Bzip2** 壓縮，產生高度壓縮的 `.tar.bz2` 套件。此格式在類 Unix 系統中相當受歡迎，因為它在壓縮率與解壓速度之間取得了良好的平衡。

## 為什麼使用 Aspose.Zip 壓縮檔案為 TarBz2？

Aspose.Zip 能在 **兩個 API 呼叫** 內產生 TarBz2 壓縮檔，同時有效處理串流。它支援 **超過 50 種壓縮與封存格式**，可處理高達 **2 GB** 的檔案而不需將整個封存檔載入記憶體，且可在 Windows、Linux 與 macOS .NET 執行環境上執行。此函式庫亦提供對條目名稱、時間戳記與壓縮等級的細緻控制，讓它成為控制台工具與 Web 服務的理想選擇。

## 前置條件

- **Aspose.Zip for .NET** – 從官方網站下載最新套件：[https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – 包含您想要封存的檔案的資料夾。在範例中，我們以變數 `dataDir` 來指代它。

> **專業提示：** 請將來源檔案放在專用資料夾中，以免不小心包含不需要的檔案。

## 匯入命名空間

首先，匯入所需的命名空間，以便存取 Aspose.Zip 的 Tar 與 Bzip2 類別。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步驟 1：設定文件目錄

定義指向保存您想要封存檔案之資料夾的路徑。

```csharp
string dataDir = "Your Document Directory";
```

> 將 `"Your Document Directory"` 替換為指向來源資料夾的絕對或相對路徑。

## 步驟 2：將檔案加入 tar 並建立 TarBz2 壓縮檔

`TarArchive` 類別代表記憶體中的 tar 容器，而 `Bzip2Archive` 使用 Bzip2 演算法壓縮串流。  
`CreateEntry` 方法會將新檔案條目加入 tar 壓縮檔。

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

- `CreateEntry` **adds files to tar** – 您可以對每個需要加入封存檔的檔案呼叫此方法。  
- `bz2.SetSource(archive)` 告訴 Bzip2 壓縮檔要壓縮整個 tar 串流。  
- `bz2.Save(...)` 將最終的 **TarBz2** 檔案寫入磁碟。

**提示：** 若要大量 **add files to tar**，只需在呼叫 `bz2.Save` 之前，對每個檔案重複執行 `archive.CreateEntry`。

## 如何將檔案加入 tar？

載入來源目錄，建立 `TarArchive` 實例，使用 `CreateEntry` 加入每個檔案，然後將 tar 串流包裝於 `Bzip2Archive` 中並呼叫 `Save`。此兩步驟模式可加入任意數量的檔案，並在單一流暢的流程中產生 `.tar.bz2` 檔案，免除暫存檔或外部工具的需求。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| **File not found** 錯誤 | `dataDir` 路徑錯誤或缺少檔案副檔名 | 確認完整路徑並確保檔案存在。 |
| **Empty archive** | `bz2.Save` 前未加入任何條目 | 至少呼叫一次 `CreateEntry`。 |
| **Permission denied** | 應用程式缺乏對輸出資料夾的寫入權限 | 以適當權限執行應用程式或選擇可寫入的目錄。 |

## 常見問答

**Q: Aspose.Zip 是否相容於所有 .NET 應用程式？**  
A: 是的。它支援 .NET Framework、.NET Core、.NET 5/6 以及更新的執行環境。

**Q: 我可以同時壓縮多個檔案嗎？**  
A: 當然可以。在儲存封存檔之前，對每個檔案呼叫 `CreateEntry`。

**Q: 我可以在哪裡找到更多文件？**  
A: 詳細文件可在 **Aspose.Zip .NET API 參考** 中取得：[Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/)。

**Q: 我如何取得 Aspose.Zip 的暫時授權？**  
A: 您可以在此 **申請暫時授權**： [request a temporary license](https://purchase.aspose.com/temporary-license/)。

**Q: 是否提供免費試用？**  
A: 有，**可從 Aspose 釋出頁面下載試用版**： [download a trial version](https://releases.aspose.com/)。

您也可以 [下載試用版](https://releases.aspose.com/)。

## 結論

您現在已了解 **如何建立 tar 檔案**，使用 Bzip2 壓縮 tar 串流，並使用 Aspose.Zip for .NET 產生 **TarBz2** 壓縮檔。此方法快速、記憶體效能高，且可在所有現代 .NET 平台上運作。歡迎嘗試更大的檔案集合、自訂條目名稱，或將程式碼整合到您自己的備份或部署流程中。

如果您遇到任何挑戰，Aspose.Zip 社群隨時提供協助——只要前往 **Aspose.Zip 支援論壇**： [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37)。

---

**最後更新：** 2026-10-31  
**測試環境：** Aspose.Zip for .NET (latest release)  
**作者：** Aspose  

## 相關教學

- [建立 tar 檔案並使用 Aspose.Zip for .NET 加入檔案至 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [使用 Aspose.Zip 加入檔案至 tar 並建立 tarxz 壓縮檔](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [使用 Aspose.Zip 加入檔案至 tar 並壓縮為 TarZ](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}