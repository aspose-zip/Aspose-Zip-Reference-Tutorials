---
date: 2025-11-29
description: 學習如何在 .NET 中使用 Aspose.Zip 將檔案加入 tar 並壓縮為 tarbz2 格式。此一步一步的指南展示如何有效建立 tarbz2
  壓縮檔。
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 將檔案加入 tar 並壓縮為 TarBz2
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新增檔案至 tar 並使用 Aspose.Zip for .NET 壓縮為 TarBz2

## 介紹

歡迎閱讀我們的完整教學，說明 **如何將檔案加入 tar** 並使用 Aspose.Zip for .NET 壓縮為 TarBz2 格式。無論您是要建立備份工具、交付部署套件，或只是需要一個緊湊的發佈檔案，本教學都會以清晰的說明與實務技巧，逐步帶您完成整個流程。

在開始之前，請先確認您已具備以下所有項目。

## 快速答覆
- **應該使用哪個函式庫？** Aspose.Zip for .NET
- **實作需要多久？** 約 5‑10 分鐘
- **需要授權嗎？** 正式環境需臨時授權；提供免費試用版
- **可以壓縮多個檔案嗎？** 可以 – 想加入多少條目都行
- **相容於 .NET 6+ 嗎？** 完全相容，Aspose.Zip 支援 .NET Framework 與 .NET Core/5/6

## 什麼是「add files to tar」？
將檔案加入 **tar**（Tape Archive）會產生一個未壓縮的單一容器，保留目錄結構與檔案中繼資料。之後再套用 Bzip2 壓縮，即得到 **tar.bz2**（TarBz2）檔案——非常適合高效儲存與傳輸。

## 為什麼要使用 Aspose.Zip 壓縮為 TarBz2？
- **速度與簡易性** – 單行 API 呼叫即可同時完成 tar 建立與 Bzip2 壓縮。
- **跨平台** – 可在 Windows、Linux 與 macOS 的 .NET 執行環境上執行。
- **細緻控制** – 可自行挑選要加入的檔案、設定自訂條目名稱，並直接串流寫入磁碟。

## 前置需求

- **Aspose.Zip for .NET** – 從官方網站下載最新套件：[https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **文件目錄** – 包含欲封存檔案的資料夾。範例中以變數 `dataDir` 代表。

> **專業提示：** 請將來源檔案放在專屬資料夾，以免不小心納入不需要的檔案。

## 匯入命名空間

首先匯入必要的命名空間，以便使用 Aspose.Zip 的 Tar 與 Bzip2 類別。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步驟 1：設定文件目錄

定義指向欲封存檔案所在資料夾的路徑。

```csharp
string dataDir = "Your Document Directory";
```

> 將 `"Your Document Directory"` 替換為來源資料夾的絕對或相對路徑。

## 步驟 2：將檔案加入 tar 並建立 TarBz2 壓縮檔

核心流程是建立 `TarArchive`、加入條目，然後以 `Bzip2Archive` 包裝。以下程式碼示範 **如何以乾淨的 disposable 模式建立 tarbz2**。

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
- `bz2.SetSource(archive)` 告訴 Bzip2 壓縮整個 tar 串流。  
- `bz2.Save(...)` 將最終的 **tar.bz2** 檔案寫入磁碟。

**小技巧：** 若要 **批次壓縮檔案為 tarbz2**，只要對每個檔案重複呼叫 `archive.CreateEntry` 即可。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **找不到檔案** 錯誤 | `dataDir` 路徑錯誤或缺少副檔名 | 核對完整路徑並確認檔案存在 |
| **封存為空** | 在 `bz2.Save` 前未加入任何條目 | 至少呼叫一次 `CreateEntry` |
| **權限被拒** | 程式沒有寫入輸出資料夾的權限 | 以適當權限執行應用程式或選擇可寫入的目錄 |

## 常見問答

**Q: Aspose.Zip 能相容所有 .NET 應用程式嗎？**  
A: 能。它支援 .NET Framework、.NET Core、.NET 5/6 以及更新的執行環境。

**Q: 可以同時壓縮多個檔案嗎？**  
A: 當然可以。在儲存封存檔之前，對每個檔案呼叫 `CreateEntry` 即可。

**Q: 哪裡可以找到更多文件說明？**  
A: 詳細文件請參閱 [此處](https://reference.aspose.com/zip/net/)。

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: 您可以在 [此處](https://purchase.aspose.com/temporary-license/) 申請。

**Q: 有提供免費試用嗎？**  
A: 有，請在 [此處](https://releases.aspose.com/) 下載試用版。

## 結論

現在您已掌握 **將檔案加入 tar**、以 Bzip2 串流壓縮，並使用 Aspose.Zip for .NET 產生 **TarBz2** 檔案的完整流程。此技巧快速、可靠，且能在所有現代 .NET 平台上執行。歡迎嘗試更大的檔案集合、客製化條目名稱，或將程式碼整合至您自己的備份或部署管線。

若在使用過程中遇到任何問題，Aspose.Zip 社群隨時提供協助——只要前往 [Aspose.Zip 支援論壇](https://forum.aspose.com/c/zip/37) 即可。

---

**最後更新：** 2025-11-29  
**測試環境：** Aspose.Zip for .NET（最新發行版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}