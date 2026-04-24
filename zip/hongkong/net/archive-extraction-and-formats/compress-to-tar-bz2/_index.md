---
date: 2026-04-24
description: 學習如何在 .NET 中使用 Aspose.Zip 壓縮 tar 並建立 TarBz2 壓縮檔。此一步一步的指南說明如何將檔案加入 tar
  以及高效產生 tarbz2 檔案。
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: 壓縮成 TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET �縮 tar 並建立 TarBz2
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮 tar 並建立 TarBz2

## 介紹

在本教學中，您將學會 **如何壓縮 tar** 壓縮檔，並使用 **Aspose.Zip** .NET 函式庫將其轉換為緊湊的 **TarBz2** 檔案。無論您是要建立備份工具、發佈部署套件，或只是需要一個輕量的分發包，以下步驟都會指導您如何將檔案加入 tar、套用 Bzip2 壓縮，並產生可直接分享的封存檔。

在開始之前，請確保您已具備本指南稍後列出的先決條件，以免在操作過程中卡關。

## 快速答覆
- **應該使用哪個函式庫？** Aspose.Zip for .NET  
- **實作需要多長時間？** 約 5‑10 分鐘  
- **需要授權嗎？** 生產環境需要臨時授權；提供免費試用版  
- **可以壓縮多個檔案嗎？** 可以 – 您可以隨意將多個條目加入 tar 壓縮檔  
- **相容於 .NET 6+ 嗎？** 完全相容，Aspose.Zip 支援 .NET Framework 以及 .NET Core/5/6  

## 什麼是 TarBz2 壓縮檔？

**TarBz2** 檔案結合了傳統的 **tar** 容器（保留目錄結構與檔案中繼資料）與 **Bzip2** 壓縮，產生高度壓縮的 `.tar.bz2` 套件。此格式在類 Unix 系統中相當流行，因為它在壓縮率與解壓速度之間取得了良好的平衡。

## 為什麼要使用 Aspose.Zip 壓縮成 TarBz2？

- **速度與簡易性** – 單行 API 呼叫即可同時完成 tar 建立與 Bzip2 壓縮。  
- **跨平台** – 可在 Windows、Linux 與 macOS .NET 執行環境上運作。  
- **細緻控制** – 可自行挑選要包含的檔案、設定自訂條目名稱，並直接串流寫入磁碟。  
- **完整 .NET 支援** – 完美適用於 **tar archive .net** 情境，從主控台應用程式到 Web 服務皆可使用。  

## 前置條件

- **Aspose.Zip for .NET** – 從官方網站下載最新套件：[https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **文件目錄** – 包含您要封存檔案的資料夾。在範例中，我們以變數 `dataDir` 代表此路徑。

> **專業提示：** 請將來源檔案放在專屬資料夾中，以免不小心將不需要的檔案納入封存。

## 匯入命名空間

首先，匯入必要的命名空間，以便存取 Aspose.Zip 的 Tar 與 Bzip2 類別。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步驟 1：設定文件目錄

定義指向您要封存檔案所在資料夾的路徑。

```csharp
string dataDir = "Your Document Directory";
```

> 將 `"Your Document Directory"` 替換為您來源資料夾的絕對或相對路徑。

## 步驟 2：將檔案加入 tar 並建立 TarBz2 壓縮檔

此流程的核心是建立 `TarArchive`、加入條目，然後以 `Bzip2Archive` 包裝。以下程式碼示範了 **如何建立 tar** 並將其壓縮為 **TarBz2**，採用乾淨的 disposable‑pattern 風格。

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
- `bz2.SetSource(archive)` 告訴 Bzip2 壓縮檔要壓縮整個 tar 串流。  
- `bz2.Save(...)` 將最終的 **TarBz2** 檔案寫入磁碟。

**小技巧：** 若要 **一次加入多個檔案到 tar**，只需在呼叫 `bz2.Save` 前，為每個檔案重複執行 `archive.CreateEntry`。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **找不到檔案** 錯誤 | `dataDir` 路徑錯誤或缺少副檔名 | 核對完整路徑，確認檔案確實存在。 |
| **封存檔為空** | 在 `bz2.Save` 前未加入任何條目 | 至少呼叫一次 `CreateEntry`。 |
| **權限被拒** | 程式無寫入輸出資料夾的權限 | 以適當權限執行應用程式，或選擇可寫入的目錄。 |

## 常見問答

**Q: Aspose.Zip 是否相容所有 .NET 應用程式？**  
A: 是的。它支援 .NET Framework、.NET Core、.NET 5/6 以及更新的執行環境。

**Q: 可以同時壓縮多個檔案嗎？**  
A: 當然可以。在儲存封存檔之前，為每個檔案呼叫 `CreateEntry` 即可。

**Q: 哪裡可以找到更多文件說明？**  
A: 詳細文件請參考 [here](https://reference.aspose.com/zip/net/)。

**Q: 如何取得 Aspose.Zip 的臨時授權？**  
A: 您可以在此處申請 [here](https://purchase.aspose.com/temporary-license/)。

**Q: 有免費試用版嗎？**  
A: 有，請在此下載試用版 [here](https://releases.aspose.com/)。

## 結論

您現在已掌握 **如何壓縮 tar**、將檔案加入其中，並以 Bzip2 串流包裝，最終使用 Aspose.Zip for .NET 產生 **TarBz2** 壓縮檔。此方法快速、可靠，且可在所有現代 .NET 平台上運作。歡迎嘗試更大的檔案集合、自訂條目名稱，或將程式碼整合至您自己的備份或部署流程中。

若在使用過程中遇到任何挑戰，Aspose.Zip 社群隨時提供協助——只要前往 [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37) 即可。

---

**最後更新：** 2026-04-24  
**測試環境：** Aspose.Zip for .NET（最新發行版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}