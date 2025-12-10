---
date: 2025-12-10
description: 學習如何使用 Aspose.Zip for .NET 儲存未壓縮的檔案。本指南將示範如何建立未壓縮的 ZIP、將檔案存入 ZIP，以及有效管理壓縮檔案。
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 儲存未壓縮的檔案
url: /zh-hant/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 以未壓縮方式儲存檔案

在現代 .NET 開發中，**如何有效儲存檔案** 可能會對效能與儲存成本產生重大影響。當您需要將檔案保持原樣——不進行任何壓縮——Aspose.Zip for .NET 提供了簡潔直觀的 API。本教學將一步步說明如何建立未壓縮的 ZIP 壓縮檔、將檔案儲存至 ZIP，並將此解決方案整合至您的應用程式中。

## 快速解答
- **「未壓縮 zip」是什麼意思？** 它是一種 ZIP 壓縮檔，每個項目皆以「store」方式儲存，原始檔案的位元組保持不變。  
- **為什麼要避免壓縮？** 為了加快壓縮速度、保留原始檔案大小以供後續處理，或符合禁止資料變更的法規要求。  
- **哪個 Aspose.Zip 類別負責此功能？** `ArchiveEntrySettings` 搭配 `StoreCompressionSettings`。  
- **我需要授權嗎？** 免費試用版可用於測試，正式環境需購買商業授權。  
- **支援的 .NET 版本？** .NET Framework、.NET Core、.NET 5/6/7 以及更高版本。

## 什麼是未壓縮儲存多個檔案？
未壓縮儲存多個檔案指的是使用 *store* 壓縮方式將每個檔案加入 ZIP 容器。檔案的位元組與原始檔案完全相同，適用於需要快速封存或必須保持資料不變的情況。

## 為什麼要使用 Aspose.Zip 來建立未壓縮壓縮檔？
- **速度：** 不會執行耗費 CPU 的壓縮演算法。  
- **可預測大小：** 壓縮檔大小等於原始檔案總和加上極少的 ZIP 開銷。  
- **相容性：** 產生的 ZIP 可在任何標準解壓縮工具中使用。  
- **彈性：** 如有需要，仍可在同一壓縮檔中混合壓縮與未壓縮的項目。

## 前置條件
- **Aspose.Zip for .NET** – 已整合至您的專案。請參考官方 [documentation](https://reference.aspose.com/zip/net/) 了解安裝步驟。  
- **.NET 開發環境** – Visual Studio、VS Code 或您慣用的任何 IDE。  
- **文件目錄** – 您機器上存放欲封存檔案的資料夾（例如「Your Document Directory」）。

## 匯入命名空間
在撰寫程式碼之前，先匯入必要的命名空間，讓編譯器能找到 Aspose 類別。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 步驟 1：設定文件目錄
定義來源檔案所在的路徑。請將佔位符替換為您系統上的實際資料夾路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立未壓縮的 Zip 壓縮檔
本教學的核心——我們建立一個以 `StoreCompressionSettings` 設定的 `Archive` 實例，告訴 Aspose.Zip *store*（即不壓縮）每個項目。

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **專業提示：** 若您需要 **將檔案儲存至 zip** 時，同時對部分檔案進行壓縮、對其他檔案保持未壓縮，只要為每個檔案建立不同的 `ArchiveEntrySettings`，再將它們加入同一個 `Archive` 即可。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **找不到檔案** | `dataDir` 路徑不正確或缺少副檔名。 | 核對路徑並確認檔案存在。使用 `Path.Combine` 以取得更安全的路徑組合。 |
| **存取被拒** | 程式缺乏讀取來源檔案或寫入 ZIP 的權限。 | 以具備相應權限的身分執行應用程式，或選擇具有寫入權限的資料夾。 |
| **ZIP 中的檔案大小異常** | 壓縮檔是以預設壓縮方式建立的。 | 確認在 `ArchiveEntrySettings` 中傳入 `new StoreCompressionSettings()`。 |

## 常見問答

**Q: 我可以對特定類型的檔案進行壓縮，其他則保持未壓縮嗎？**  
A: 可以，為每種檔案建立不同的 `ArchiveEntrySettings`，即可在同一壓縮檔中混合壓縮與未壓縮的項目。

**Q: Aspose.Zip for .NET 是否相容 .NET Core 與 .NET 5/6？**  
A: 完全相容。此函式庫支援 .NET Framework、.NET Core、.NET Standard，以及最新的 .NET 版本。

**Q: 在封存過程中應如何處理例外狀況？**  
A: 將封存程式碼包在 `try‑catch` 區塊中，並記錄例外細節。這樣可確保程式平順失敗並方便除錯。

**Q: Aspose.Zip 支援多執行緒封存嗎？**  
A: 支援，您可以平行處理多個檔案並將它們加入壓縮檔，但需注意 `Archive` 物件本身不是執行緒安全的；在加入項目時請同步存取。

**Q: 我可以在不大幅修改程式碼的情況下將 Aspose.Zip 整合到既有專案嗎？**  
A: 完全可以。API 設計為即插即用。請參考官方 [documentation](https://reference.aspose.com/zip/net/) 取得遷移指引。

---

**最後更新：** 2025-12-10  
**測試環境：** Aspose.Zip for .NET 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}