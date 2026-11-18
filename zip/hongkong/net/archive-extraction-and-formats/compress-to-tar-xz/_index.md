---
date: 2026-11-18
description: 了解如何使用 Aspose.Zip 在 .NET 中將檔案加入 tar 並壓縮為 tarxz 壓縮檔。遵循此一步一步的指南，以實現高效的儲存與傳輸。
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: 壓縮至 TarXz
og_description: 使用 Aspose.Zip 將檔案加入 tar 並建立 tarxz 壓縮檔。了解如何在 .NET 中快速將檔案壓縮為 TarXz，具備高壓縮效率與跨平台相容性。
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: 使用 Aspose.Zip 將檔案加入 tar 並建立 tarxz 壓縮檔
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: 使用 Aspose.Zip 將檔案加入 tar 並建立 tarxz 壓縮檔
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將檔案加入 tar 並使用 Aspose.Zip 建立 tarxz 壓縮檔

## 介紹

如果您需要 **add files to tar**，然後 **create a tarxz archive .net**，Aspose.Zip for .NET 可讓此過程簡單且可靠。無論您是要打包日誌、設定檔，或任何其他資產以供儲存或傳輸，將資料壓縮為 TarXz 格式可提供高壓縮率，同時保留熟悉的 tar 結構。在本教學中，我們將逐步說明完整步驟——包含程式碼片段——讓您能自信地在 .NET 應用程式中整合 tarxz 建立。最後，您將了解為何「add files to tar」是打造緊湊、跨平台套件的第一步。

## 快速解答
- **主要類別是什麼？** `TarArchive` from `Aspose.Zip.Tar`
- **如何壓縮為 tarxz？** 呼叫 `SaveXzCompressed` 於加入條目後
- **支援哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 以及 .NET 5–10
- **需要授權嗎？** 是，生產環境必須使用有效的 Aspose.Zip 授權
- **實作時間？** 基本壓縮檔大約需要 5‑10 分鐘

## TarXz 壓縮檔是什麼？

TarXz 壓縮檔結合了傳統 Unix `tar` 容器與 XZ 壓縮。tar 部分將多個檔案打包成單一串流，而 XZ 提供強大且無損的壓縮。此格式因能保留目錄結構且比純 tar 或 zip 產生更小的檔案大小，常用於分發原始碼、備份與大型資料集。

## 為何使用 Aspose.Zip 在 .net 建立 tarxz 壓縮檔？

使用 Aspose.Zip 建立 TarXz 壓縮檔提供快速且一步到位的解決方案，無需外部工具。檔案大小比 gzip 小 30‑50 %，且可在 .NET 中直接處理超過 20 種壓縮格式。此函式庫在不將整個檔案載入記憶體的情況下處理大型壓縮檔，適合雲端服務與 CI 流程。它亦支援超過 50 種輸入與輸出格式。

## 前置條件

在開始之前，請確保您已具備：

- **Aspose.Zip for .NET** 已安裝（從官方 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 下載）。  
- 包含欲壓縮檔案的資料夾。以下範例中，此資料夾以 `dataDir` 變數引用。  
- 有效的 Aspose.Zip 授權（評估可選，正式使用必須）。

## 匯入命名空間

您只需匯入提供 TarXz 功能的命名空間。除核心 Aspose.Zip 函式庫外，無需其他套件。

## 如何使用 Aspose.Zip 將檔案加入 tar

`TarArchive` 是 Aspose.Zip 中代表 tar 容器的類別。您可透過建立 `TarArchive` 實例，然後對每個欲加入的檔案呼叫其 `AddEntry` 方法，指定來源路徑與可選的條目名稱，將檔案加入 tar 壓縮檔。該壓縮檔會在記憶體中建構 tar 容器，準備後續的 XZ 壓縮。

```csharp
using System;
using Aspose.Zip.Tar;
```

> **專業提示：** `using` 陳述式可確保壓縮檔正確釋放，釋放任何未受管理的資源。

### 步驟 1：初始化 `TarArchive`

在 `using` 區塊內建立 `TarArchive` 物件，讓所有未受管理的資源在操作完成後自動釋放。

```csharp
using (TarArchive archive = new TarArchive())
{
```

### 步驟 2：將檔案加入壓縮檔

將您想要加入的每個檔案加入。此範例加入兩個文字檔，但您可依需求加入任意數量的條目。`AddEntry` 方法接受完整檔案路徑以及會出現在 tar 內的可選條目名稱。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **為何重要：** 在壓縮前加入條目可讓 Aspose.Zip 先建構 tar 容器，然後在單一步驟中套用 XZ 壓縮。

### 步驟 3：以 XZ 壓縮儲存壓縮檔

`SaveXzCompressed` 方法會在一次步驟中將 tar 壓縮檔寫入檔案並套用 XZ 壓縮，產生可直接分發的 `.tar.xz` 檔案。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **結果：** 您現在擁有完整壓縮的 `archive.tar.xz` 檔案，可在任何支援 TarXz 的平台上傳輸、儲存或解壓縮。

## 如何使用 Aspose.Zip 壓縮 tarxz 檔案

使用 Aspose.Zip 壓縮為 tarxz 為兩步驟流程，封裝於單一方法呼叫中：首先 **add files to tar**，然後呼叫 `SaveXzCompressed`。此方式免除外部指令列工具的需求，並將整個工作流程保留在您的 .NET 程式碼中。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|-------|-------|-----|
| **“File not found” 例外** | `dataDir` 路徑不正確 | 確認目錄路徑以反斜線 (`\`) 結尾，或使用 `Path.Combine`。 |
| **記憶體使用量大** | 在記憶體中壓縮非常大的檔案 | 使用串流模式的 `TarArchive`（接受 `Stream` 的 `SaveXzCompressed` 重載）。 |
| **未套用授權** | 缺少授權檔案 | 在應用程式啟動時載入授權：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## 常見問答

**Q: Aspose.Zip 是否相容所有 .NET 環境？**  
A: 是，Aspose.Zip 支援 .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 以及 .NET 5–10。詳情請參閱 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: 您可從 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

**Q: 是否有其他壓縮格式的額外範例？**  
A: 當然有——請在 [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) 中探索完整範例集。

**Q: 在哪裡可以取得協助或討論問題？**  
A: 加入 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 的討論，可獲得社群支援與官方回覆。

**Q: 購買前可以免費試用 Aspose.Zip 嗎？**  
A: 可以，免費試用版可在 [Aspose.Zip download page](https://releases.aspose.com/zip/net) 取得。

## 結論

依照上述步驟，您現在已了解 **how to add files to tar** 與 **compress tarxz** 檔案，更重要的是，如何使用 Aspose.Zip **create tarxz archive .net**。此方法可產生緊湊且可攜的套件，能無縫整合至任何 .NET 工作流程——無論是桌面工具、Web 服務，或自動化 CI/CD 管線。

---

**最後更新：** 2026-11-18  
**測試版本：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

## 相關教學

- [使用 Aspose.Zip for .NET 建立 tar 壓縮檔並將檔案加入 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [如何壓縮 tar 並使用 Aspose.Zip for .NET 建立 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [如何使用 Aspose.Zip for .NET 壓縮多個檔案為 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}