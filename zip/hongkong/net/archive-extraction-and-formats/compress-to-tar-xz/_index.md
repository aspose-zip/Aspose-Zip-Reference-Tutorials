---
date: 2026-02-23
description: 學習如何在 .NET 中使用 Aspose.Zip 將檔案加入 tar，並壓縮成 tar.xz 壓縮檔。請遵循此一步一步的指南，以實現高效的儲存與傳輸。
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 將檔案加入 tar 並建立 tarxz 壓縮檔
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 新增檔案至 tar 並建立 tarxz 壓縮檔

## 介紹

如果您需要 **add files to tar**，然後 **create a tarxz archive .net**，Aspose.Zip for .NET 讓此過程變得簡單且可靠。無論您是要打包日誌、設定檔，或任何其他資產以供儲存或傳輸，將它們壓縮為 TarXz 格式可提供高壓縮率，同時保留熟悉的 tar 結構。在本教學中，我們將逐步說明完整步驟——附上程式碼片段——讓您能有信心在 .NET 應用程式中整合 tarxz 的建立。

## 快速解答
- **主要類別是什麼？** `TarArchive` from `Aspose.Zip.Tar`
- **如何壓縮 tarxz？** Use `SaveXzCompressed` after adding entries
- **支援的 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **需要授權嗎？** Yes, a valid Aspose.Zip license for production
- **典型實作時間？** ~5‑10 minutes

## TarXz 壓縮檔是什麼？

A **TarXz archive** combines the traditional Unix `tar` container with XZ compression. The tar part bundles multiple files into a single stream, while XZ provides strong, lossless compression. This format is popular for distributing source code, backups, and large data sets because it retains directory structures and achieves smaller file sizes than plain tar or zip.

## 為何使用 Aspose.Zip 在 .NET 中建立 tarxz 壓縮檔？

- **高壓縮比** – XZ 通常比 gzip 小 30‑50 %  
- **跨平台相容性** – TarXz 檔案可在 Linux、macOS 與 Windows 開啟  
- **簡易 API** – Aspose.Zip 抽象化低階細節，讓您專注於業務邏輯  
- **無需外部工具** – 所有操作皆在 .NET 程序內執行，適合雲端或 CI 流程  

## 前置條件

在開始之前，請確保您已具備：

- **Aspose.Zip for .NET** 已安裝（從官方 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 下載）。  
- 包含欲壓縮檔案的資料夾。以下範例中，此資料夾以 `dataDir` 變數引用。  
- 有效的 Aspose.Zip 授權（評估版可選，正式環境必須）。

## 匯入命名空間

首先，匯入提供 TarXz 功能的命名空間。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 使用 Aspose.Zip 新增檔案至 tar 的方法

以下步驟說明如何在壓縮前 **add files to tar**。

### 步驟 1：初始化 `TarArchive`

建立一個新的 `TarArchive` 實例，以容納您想要壓縮的檔案。

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **專業提示：** `using` 陳述式可確保壓縮檔正確釋放，並釋放任何非受控資源。

### 步驟 2：將檔案加入壓縮檔

將每個欲納入的檔案加入。此範例加入兩個文字檔，您可依需求加入任意數量的項目。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **為什麼重要：** 在壓縮前加入條目可讓 Aspose.Zip 先建立 tar 容器，然後一次性套用 XZ 壓縮。

### 步驟 3：使用 XZ 壓縮儲存壓縮檔

最後，使用 XZ 壓縮將 tar 壓縮檔寫入磁碟。產生的檔案副檔名為 `.tar.xz`。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **結果：** 您現在擁有一個完整壓縮的 `archive.tar.xz` 檔案，可在任何支援 TarXz 的平台上傳輸、儲存或解壓。

## 使用 Aspose.Zip 壓縮 tarxz 檔案的方法

上述流程即為 **how to compress tarxz**：先將檔案加入 tar 容器（`add files to tar`），再呼叫 `SaveXzCompressed`。此單一步驟消除對外部指令列工具的需求，全部在 .NET 程式碼中完成。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **「File not found」例外** | `dataDir` 路徑不正確 | 確認目錄路徑以反斜線 (`\`) 結尾，或使用 `Path.Combine`。 |
| **大量記憶體使用** | 大檔案在記憶體中壓縮 | 使用支援串流模式的 `TarArchive`（接受 `Stream` 的 `SaveXzCompressed` 重載）。 |
| **授權未套用** | 缺少授權檔案 | 在應用程式啟動時載入授權：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## 常見問答

**Q: Aspose.Zip 是否相容所有 .NET 環境？**  
A: Yes, Aspose.Zip works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+. See the [documentation](https://reference.aspose.com/zip/net/) for details.

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: You can request a temporary license from the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**Q: 是否有其他壓縮格式的範例？**  
A: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: 哪裡可以取得協助或討論問題？**  
A: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community support and official answers.

**Q: 購買前能否免費試用 Aspose.Zip？**  
A: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## 結論

透過上述步驟，您已掌握 **how to add files to tar**、**compress tarxz**，以及更重要的 **create tarxz archive .net** 使用 Aspose.Zip 的方法。此方式可產生緊湊且可攜的套件，輕鬆整合至任何 .NET 工作流程——無論是桌面工具、Web 服務，或自動化 CI/CD 管線。

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}