---
date: 2025-12-05
description: 學習如何在 .NET 中建立 tarxz 壓縮檔，以及如何使用 Aspose.Zip for .NET 壓縮 tarxz 檔案。遵循此一步一步的指南，以實現高效的儲存與傳輸。
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 .NET 中使用 Aspose.Zip 建立 tarxz 壓縮檔
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip 在 .net 中建立 tarxz 壓縮檔

## 介紹

如果您需要 **建立 tarxz 壓縮檔 .net**，Aspose.Zip for .NET 讓此過程變得簡單且可靠。無論您是要打包日誌、設定檔，或任何其他資產以供儲存或傳輸，使用 TarXz 格式壓縮可提供高壓縮比，同時保留熟悉的 tar 結構。在本教學中，我們將逐步說明完整步驟——附上程式碼片段——讓您能自信地在 .NET 應用程式中整合 tarxz 建立功能。

## 快速答案
- **主要類別是什麼？** `TarArchive` 來自 `Aspose.Zip.Tar`
- **如何壓縮 tarxz？** 在加入條目後使用 `SaveXzCompressed`
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6
- **需要授權嗎？** 是，正式環境需有效的 Aspose.Zip 授權
- **典型實作時間？** 約 5‑10 分鐘

## 什麼是 TarXz 壓縮檔？

**TarXz 壓縮檔** 結合了傳統的 Unix `tar` 容器與 XZ 壓縮。tar 部分將多個檔案打包成單一串流，而 XZ 提供強大的無損壓縮。此格式常用於分發原始碼、備份與大型資料集，因為它保留目錄結構且比純 tar 或 zip 檔案更小。

## 為什麼要使用 Aspose.Zip 在 .net 中建立 tarxz 壓縮檔？

- **高壓縮比** – XZ 通常比 gzip 小 30‑50 %。
- **跨平台相容性** – TarXz 檔案可在 Linux、macOS 與 Windows 開啟。
- **簡易 API** – Aspose.Zip 抽象低階細節，讓您專注於業務邏輯。
- **無需外部工具** – 所有操作都在 .NET 程序內執行，適合雲端或 CI 流程。

## 前置條件

在開始之前，請確保您已具備：

- **Aspose.Zip for .NET** 已安裝（可從官方 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 下載）。
- 包含欲壓縮檔案的資料夾。以下範例中，此資料夾以 `dataDir` 變數引用。
- 有效的 Aspose.Zip 授權（評估可選，正式環境必須）。

## 匯入命名空間

首先，匯入提供 TarXz 功能的命名空間。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 步驟說明：在 .net 中建立 tarxz 壓縮檔

### 步驟 1：初始化 `TarArchive`

建立一個新的 `TarArchive` 實例，用來保存您想壓縮的檔案。

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **專業提示：** `using` 陳述式可確保壓縮檔正確釋放，並清除任何未受管理的資源。

### 步驟 2：將檔案加入壓縮檔

將每個欲納入的檔案加入。以下範例加入兩個文字檔，您可依需求加入任意數量的條目。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **為什麼重要：** 在壓縮前先加入條目，讓 Aspose.Zip 先建立 tar 容器，然後一次性套用 XZ 壓縮。

### 步驟 3：使用 XZ 壓縮儲存壓縮檔

最後，使用 XZ 壓縮將 tar 壓縮檔寫入磁碟。產生的檔案副檔名為 `.tar.xz`。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **結果：** 您現在擁有一個完整壓縮的 `archive.tar.xz` 檔案，可在任何支援 TarXz 的平台上傳輸、儲存或解壓。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **「找不到檔案」例外** | `dataDir` 路徑不正確 | 確認目錄路徑以反斜線 (`\`) 結尾，或使用 `Path.Combine`。 |
| **記憶體使用量過大** | 大檔案在記憶體中壓縮 | 使用支援串流的 `TarArchive`（`SaveXzCompressed` 的接受 `Stream` 的重載）。 |
| **授權未套用** | 缺少授權檔案 | 在應用程式啟動時載入授權：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## 常見問答

**Q: Aspose.Zip 是否相容所有 .NET 環境？**  
A: 是，Aspose.Zip 支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。詳情請參閱 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: 您可從 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

**Q: 是否有其他壓縮格式的額外範例？**  
A: 當然，請在 [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) 中探索完整範例集。

**Q: 哪裡可以取得協助或討論問題？**  
A: 歡迎加入 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 與社群交流，或取得官方回覆。

**Q: 購買前可以免費試用 Aspose.Zip 嗎？**  
A: 可以，請前往 [Aspose.Zip download page](https://releases.aspose.com/zip/net) 下載免費試用版。

## 結論

依照上述步驟，您現在已掌握 **如何壓縮 tarxz** 檔案，更重要的是，了解 **如何使用 Aspose.Zip 在 .net 中建立 tarxz 壓縮檔**。此方法可產生緊湊、可攜帶的套件，輕鬆整合至任何 .NET 工作流程——無論是桌面工具、Web 服務，或自動化 CI/CD 管線。

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}