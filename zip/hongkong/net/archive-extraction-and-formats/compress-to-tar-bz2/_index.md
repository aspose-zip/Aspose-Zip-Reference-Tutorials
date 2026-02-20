---
date: 2026-02-20
description: 了解如何在 .NET 中使用 Aspose.Zip 壓縮 tar 並建立 TarBz2 壓縮檔。本一步一步的指南示範如何將檔案加入 tar，以及有效率地產生
  tarbz2 檔案。
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮 tar 並建立 TarBz2
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮 tar 並建立 TarBz2

## 介紹

歡迎閱讀我們的完整指南，內容涵蓋 **如何壓縮 tar**、將檔案加入 tar 壓縮檔，並使用 Aspose.Zip for .NET 建立 TarBz2 檔案。無論您是在開發備份工具、交付部署套件，或只是需要一個緊湊的發佈檔，本教學都會以清晰說明、實務技巧與範例，逐步帶您完成整個流程。

在開始之前，請先確認您已備妥所有必需項目。

## 快速答覆
- **應該使用哪個函式庫？** Aspose.Zip for .NET
- **實作大約需要多久？** 約 5‑10 分鐘
- **需要授權嗎？** 正式環境需要臨時授權；提供免費試用版
- **可以壓縮多個檔案嗎？** 可以──可隨意將多個項目加入 Tar 壓縮檔
- **支援 .NET 6+ 嗎？** 完全支援，Aspose.Zip 支援 .NET Framework 與 .NET Core/5/6

## 如何壓縮 tar

將檔案加入 **tar**（Tape Archive）會產生一個未壓縮的單一容器，保留目錄結構與檔案中繼資料。之後再套用 Bzip2 壓縮，即可得到 **tar.bz2**（TarBz2）檔案——非常適合高效儲存與傳輸。Aspose.Zip 只需一行程式碼，即可同時完成 tar 建立與 Bzip2 壓縮。

## 為什麼要使用 Aspose.Zip 壓縮成 TarBz2？

- **速度與簡易性** – 單行 API 呼叫即可同時處理 tar 建立與 Bzip2 壓縮。  
- **跨平台** – 可在 Windows、Linux 與 macOS 的 .NET 執行環境上執行。  
- **細緻控制** – 可自行挑選要加入的檔案、設定自訂條目名稱，並直接串流寫入磁碟。  
- **完整 .NET 支援** – 完全相容 **tar archive .net** 場景，從主控台應用程式到 Web 服務皆可使用。

## 前置作業

- **Aspose.Zip for .NET** – 從官方網站下載最新套件：[https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **文件目錄** – 放置欲壓縮檔案的資料夾。範例中以變數 `dataDir` 代表此資料夾。

> **專業提示：** 請將來源檔案集中於專屬資料夾，以免不小心納入不需要的檔案。

## 匯入命名空間

首先匯入必要的命名空間，以便使用 Aspose.Zip 的 Tar 與 Bzip2 類別。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步驟 1：設定文件目錄

定義指向欲壓縮檔案所在資料夾的路徑。

```csharp
string dataDir = "Your Document Directory";
```

> 將 `"Your Document Directory"` 替換為您的來源資料夾的絕對或相對路徑。

## 步驟 2：將檔案加入 tar 並建立 TarBz2 壓縮檔

核心流程是建立 `TarArchive`、加入條目，然後以 `Bzip2Archive` 包裝。以下程式碼示範了 **如何建立 tarbz2**，採用乾淨的 disposable 模式。

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

- `CreateEntry` 會將每個檔案加入 **tar** 容器。  
- `bz2.SetSource(archive)` 告訴 Bzip2 壓縮檔要壓縮整個 tar 串流。  
- `bz2.Save(...)` 將最終的 **tar.bz2** 檔案寫入磁碟。

**小技巧：** 若要 **大量壓縮檔案成 tarbz2**，只需對每個檔案重複呼叫 `archive.CreateEntry` 即可。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **找不到檔案** 錯誤 | `dataDir` 路徑錯誤或缺少副檔名 | 核對完整路徑，確保檔案確實存在 |
| **壓縮檔為空** | 在 `bz2.Save` 前未加入任何條目 | 至少呼叫一次 `CreateEntry` |
| **權限被拒絕** | 程式無法寫入目標資料夾 | 以具備寫入權限的身分執行，或改用可寫入的目錄 |

## 常見問答

**Q: Aspose.Zip 能相容所有 .NET 應用程式嗎？**  
A: 能。支援 .NET Framework、.NET Core、.NET 5/6 以及更新的執行環境。

**Q: 可以同時壓縮多個檔案嗎？**  
A: 當然可以。在儲存壓縮檔前，對每個檔案呼叫 `CreateEntry` 即可。

**Q: 哪裡可以找到更多文件說明？**  
A: 詳細文件請參考 [here](https://reference.aspose.com/zip/net/)。

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: 可於 [here](https://purchase.aspose.com/temporary-license/) 申請。

**Q: 有提供免費試用嗎？**  
A: 有，請從 [here](https://releases.aspose.com/) 下載試用版。

## 結論

現在您已掌握 **將檔案加入 tar**、以 Bzip2 串流包裝，並使用 Aspose.Zip for .NET 產生 **TarBz2** 壓縮檔的完整流程。此方法快速、可靠，且可在所有現代 .NET 平台上執行。歡迎嘗試更大的檔案集合、客製化條目名稱，或將程式碼整合至您自己的備份或部署管線中。

若在使用過程中遇到任何問題，Aspose.Zip 社群隨時提供協助——只要前往 [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37) 即可。

---

**最後更新：** 2026-02-20  
**測試環境：** Aspose.Zip for .NET（最新發行版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}