---
date: 2026-02-12
description: 學習如何使用 Aspose.Zip for .NET 建立未壓縮的 ZIP 檔案。本指南將示範如何在不進行壓縮的情況下壓縮檔案、以未壓縮方式儲存檔案，並有效管理壓縮檔案。
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 建立未壓縮的 zip 檔案
url: /zh-hant/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

 Paragraphs etc.

- Quick Answers list items.

- etc.

Make sure to keep code block placeholders unchanged.

Also note: "Traditional Chinese (Hong Kong)" uses Traditional characters, maybe some HK-specific terms like "檔案" vs "文件". We'll use Traditional Chinese.

Let's translate.

We'll keep markdown formatting.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 建立未壓縮的 ZIP

在現代 .NET 開發中，**建立未壓縮的 ZIP** 可以大幅提升壓縮速度，且讓檔案大小更可預測。當您需要**不壓縮檔案**——例如符合規範要求或加速後續處理——Aspose.Zip for .NET 提供簡潔直觀的 API。本教學將逐步說明如何建立未壓縮的 ZIP 壓縮檔、加入檔案，並將解決方案整合至您的應用程式。

## 快速解答
- **「未壓縮的 ZIP」是什麼意思？** 這是一種每個項目皆使用「store」方式儲存的 ZIP 壓縮檔，原始檔案位元保持不變。  
- **為什麼要避免壓縮？** 為了加快壓縮速度、保留原始檔案大小供後續處理，或符合禁止資料變更的法規要求。  
- **哪個 Aspose.Zip 類別負責此功能？** `ArchiveEntrySettings` 搭配 `StoreCompressionSettings`。  
- **需要授權嗎？** 免費試用可用於測試；正式環境需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework、.NET Core、.NET 5/6/7 以及更新版本。  

## 什麼是 create uncompressed zip .net？
建立未壓縮的 ZIP 即是以 *store* 壓縮方式將每個檔案加入 ZIP 容器。檔案內容保持與原檔完全相同，適用於需要快速壓縮或必須保持資料不變的情境。

## 為什麼使用 Aspose.Zip 來建立不壓縮的 ZIP 檔？
- **速度快：** 不會執行耗費 CPU 的壓縮演算法。  
- **大小可預測：** 壓縮檔大小等於原始檔案總和加上最小的 ZIP 開銷。  
- **相容性高：** 產生的 ZIP 可在任何標準解壓工具中使用。  
- **彈性高：** 若需要，仍可在同一壓縮檔中混合壓縮與未壓縮的項目。

## 前置作業
- **Aspose.Zip for .NET** – 已整合至您的專案。請參考官方[文件](https://reference.aspose.com/zip/net/)了解安裝步驟。  
- **.NET 開發環境** – Visual Studio、VS Code 或您慣用的任何 IDE。  
- **文件目錄** – 您機器上存放欲壓縮檔案的資料夾（例如「Your Document Directory」）。

## 匯入命名空間
在撰寫程式碼之前，先匯入必要的命名空間，讓編譯器能找到 Aspose 類別。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 步驟 1：設定文件目錄
定義來源檔案所在的路徑。將佔位字串替換為您系統中的實際資料夾路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立未壓縮的 ZIP 壓縮檔
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

> **小技巧：** 若您需要**在壓縮同時保留部分檔案未壓縮**，可為每個檔案建立不同的 `ArchiveEntrySettings`，再將它們加入同一個 `Archive`。

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **找不到檔案** | `dataDir` 路徑錯誤或缺少副檔名。 | 檢查路徑並確認檔案存在。使用 `Path.Combine` 可提升安全性。 |
| **存取被拒** | 程式缺乏讀取來源檔案或寫入 ZIP 的權限。 | 以適當權限執行應用程式，或選擇具有寫入權限的資料夾。 |
| **ZIP 中檔案大小異常** | 壓縮檔使用了預設的壓縮方式。 | 確認在 `ArchiveEntrySettings` 中傳入 `new StoreCompressionSettings()`。 |

## 常見問答

**Q: 可以只壓縮特定類型的檔案，而其他檔案保持未壓縮嗎？**  
A: 可以，為每種檔案建立不同的 `ArchiveEntrySettings`，在同一個壓縮檔中混合壓縮與未壓縮的項目。

**Q: Aspose.Zip for .NET 是否相容 .NET Core 與 .NET 5/6？**  
A: 完全相容。此函式庫支援 .NET Framework、.NET Core、.NET Standard 以及最新的 .NET 版本。

**Q: 壓縮過程中應如何處理例外情況？**  
A: 將壓縮程式碼包在 `try‑catch` 區塊中，並記錄例外資訊，以確保程式能優雅失敗並方便除錯。

**Q: Aspose.Zip 支援多執行緒壓縮嗎？**  
A: 支援，您可以平行處理多個檔案並加入壓縮檔，但 `Archive` 物件本身不是執行緒安全的；加入項目時需同步存取。

**Q: 能否在既有專案中直接整合 Aspose.Zip，且不需大幅度修改程式碼？**  
A: 完全可以。API 設計為即插即用。請參考官方[文件](https://reference.aspose.com/zip/net/)取得遷移指南。

---

**最後更新：** 2026-02-12  
**測試環境：** Aspose.Zip for .NET（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}