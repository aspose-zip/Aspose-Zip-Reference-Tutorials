---
date: 2026-02-05
description: 了解如何在 .NET 中使用 Aspose.Zip 將檔案加入 tar 並建立 tarxz 壓縮檔。本指南示範如何高效地將檔案壓縮為 tarxz。
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 將檔案加入 tar，使用 Aspose.Zip 在 .NET 中建立 tarxz 壓縮檔
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何將檔案加入 tar，使用 Aspise.Zip 在 .NET 中建立 tarxz 壓縮檔

## 簡介

如果您需要 **將檔案加入 tar**，然後使用 .NET 的 Aspose.Zip 壓縮成 tarxz 壓縮檔，Aspose.Zip for .NET 能讓此過程既簡單又可靠。無論您是要打包日誌、設定檔，或任何其他資產以供儲存或傳輸，使用 TarXz 格式可在保留熟悉的 tar 結構的同時，獲得高壓縮比。在本教學中，我們將逐步說明完整步驟——附上程式碼片段——讓您能自信地在 .NET 應用程式中整合 tarxz 建立功能。

## 快速回答
- **主要類別是什麼？** `TarArchive` 來自 `Aspose.Zip.Tar`
- **如何壓縮 tarxz？** 在加入條目後使用 `SaveXzCompressed`
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6
- **需要授權嗎？** 是，需要有效的 Aspose.Zip 授權才能在正式環境使用
- **一般實作時間？** 約 5‑10 分鐘

## 什麼是 TarXz 壓縮檔？

**TarXz 壓縮檔** 結合了傳統的 Unix `tar` 容器與 XZ 壓縮。tar 部分將多個檔案打包成單一資料流，而 XZ 則提供強大的無損壓縮。此格式因能保留目錄結構且比純 tar 或 zip 更小的檔案大小，常用於分發原始碼、備份與大型資料集。

## 為什麼要將檔案加入 tar 並使用 Aspose.Zip 壓縮為 tarxz？

- **高壓縮比** – XZ 通常比 gzip 小 30‑50 %  
- **跨平台相容性** – TarXz 檔案可在 Linux、macOS 與 Windows 上開啟  
- **簡易 API** – Aspose.Zip 抽象化低階細節，讓您專注於業務邏輯  
- **無需外部工具** – 所有操作皆在 .NET 程序內執行，適合雲端或 CI 流程  

## 先決條件

在開始之前，請確保您已具備：

- **已安裝 Aspose.Zip for .NET**（可從官方 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 下載）  
- 包含欲壓縮檔案的資料夾。以下範例中，此資料夾以 `dataDir` 變數引用  
- 有效的 Aspose.Zip 授權（評估版可選，正式環境必須）

## 匯入命名空間

首先，匯入提供 TarXz 功能的命名空間。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 如何使用 Aspose.Zip 將檔案加入 tar

### 步驟 1：初始化 `TarArchive`

建立一個新的 `TarArchive` 實例，用來保存您想要壓縮的檔案。

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **專業提示：** `using` 陳述式可確保壓縮檔正確釋放，並釋放任何非受控資源。

### 步驟 2：將檔案加入壓縮檔

將每個欲加入的檔案加入。此範例加入兩個文字檔，您可以依需求加入任意數量的條目。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **為什麼重要：** 在壓縮前先加入條目，可讓 Aspose.Zip 先建立 tar 容器，然後一次性套用 XZ 壓縮。

### 步驟 3：使用 XZ 壓縮儲存壓縮檔

最後，使用 XZ 壓縮將 tar 壓縮檔寫入磁碟。產生的檔案副檔名為 `.tar.xz`。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **結果：** 您現在擁有一個完整壓縮的 `archive.tar.xz` 檔案，可在任何支援 TarXz 的平台上傳輸、儲存或解壓縮。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **“File not found” 例外** | `dataDir` 路徑不正確 | 確認目錄路徑以反斜線 (`\`) 結尾，或使用 `Path.Combine`。 |
| **大量記憶體使用** | 在記憶體中壓縮非常大的檔案 | 使用串流模式的 `TarArchive`（接受 `Stream` 的 `SaveXzCompressed` 重載）。 |
| **未套用授權** | 缺少授權檔案 | 在應用程式啟動時載入授權：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## 常見問答

**Q: Aspose.Zip 是否相容所有 .NET 環境？**  
A: 是，Aspose.Zip 支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。詳情請參閱[文件](https://reference.aspose.com/zip/net/)。

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: 您可從 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

**Q: 是否有其他壓縮格式的額外範例？**  
A: 當然有——請在 [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) 中探索完整範例集。

**Q: 哪裡可以取得協助或討論問題？**  
A: 加入 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 與社群互動，或取得官方回覆。

**Q: 購買前可以免費試用 Aspose.Zip 嗎？**  
A: 可以，免費試用版可在 [Aspose.Zip download page](https://releases.aspose.com/zip/net) 取得。

## 結論

依照上述步驟，您現在已掌握 **如何將檔案加入 tar** 以及 **使用 Aspose.Zip 在 .NET 中建立 tarxz 壓縮檔**。此方法可為您提供緊湊、可攜的套件，輕鬆整合至任何 .NET 工作流程——無論是桌面工具、Web 服務，或自動化 CI/CD 管線。

---

**最後更新：** 2026-02-05  
**測試版本：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}