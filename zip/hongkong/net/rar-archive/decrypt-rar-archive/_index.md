---
date: 2025-12-23
description: 學習如何使用 Aspose.Zip for .NET 提取受密碼保護的 RAR 檔案及解壓加密的 RAR 檔案。跟隨一步一步的指南，高效讀取加密的
  RAR 檔案。
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 解壓受密碼保護的 RAR
url: /zh-hant/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 解壓受密碼保護的 RAR

## 介紹

如果你曾在 .NET 應用程式中需要 **解壓受密碼保護的 rar** 壓縮檔，你會知道這件事有多棘手。幸運的是，Aspose.Zip for .NET 消除了猜測的麻煩，讓你只需幾行程式碼即可讀取加密的 rar 檔案。在本教學中，我們將完整說明從專案設定到內容解壓的每一步，讓你能順利將解密功能整合到解決方案中。

## 快速回答
- **哪個函式庫負責 RAR 解密？** Aspose.Zip for .NET  
- **正式環境需要授權嗎？** 需要，必須購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **可以在迴圈中解壓多個壓縮檔嗎？** 當然，只要對每個檔案重複步驟即可。  
- **密碼是否區分大小寫？** 會，請視為普通字串處理。

## 什麼是「解壓受密碼保護的 rar」？

解壓受密碼保護的 RAR 壓縮檔意味著打開壓縮檔、提供正確的解密密碼，然後將內部檔案寫入目標資料夾。Aspose.Zip 抽象化了底層細節，讓你可以專注於業務邏輯。

## 為什麼選擇 Aspose.Zip for .NET？

- **完整的 RAR 支援** – 支援 RAR4 與 RAR5 格式，包含加密壓縮檔。  
- **簡易 API** – 只需少數方法呼叫即可開啟、解密與解壓。  
- **跨平台** – 可在 Windows、Linux 與 macOS 的 .NET 執行環境上運作。  
- **無外部相依** – 不需要額外的第三方 RAR 工具。

## 前置條件

1. **Aspose.Zip for .NET 函式庫** – 透過 NuGet 安裝或從 [Aspose.Zip 文件](https://reference.aspose.com/zip/net/) 下載。  
2. **文件目錄** – 準備一個資料夾，內含你要處理的加密 RAR 壓縮檔。請將程式碼中的佔位路徑替換為實際目錄。

## 匯入命名空間

在 C# 檔案的最上方加入必要的 `using` 陳述式：

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## 步驟 1：開啟加密的 RAR 壓縮檔

為欲解密的 RAR 檔案建立唯讀串流。將 `"encrypted.rar"` 改成你的檔名。

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## 步驟 2：指定解密密碼

提供保護壓縮檔的密碼。此範例的密碼為 `"p@s$"`，請改成實際使用的密碼。

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## 步驟 3：將內容解壓至目錄

將解密後的檔案抽取到你指定的資料夾。將 `"DecompressRar_out"` 改成想要的輸出路徑。

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

## 使用 Aspose.Zip 解壓受密碼保護的 rar 檔案

依照上述三個步驟，你即可以程式方式 **解壓受密碼保護的 rar** 壓縮檔。此方法適用於任意數量的檔案——只要在檔案清單上迴圈並重複步驟即可。

## 常見使用情境

- **自動化資料匯入** – 從加密的 RAR 檔案批次取得資料並自動處理。  
- **企業備份還原** – 解密並還原儲存在受密碼保護 RAR 檔案中的備份。  
- **安全檔案交換** – 允許使用者上傳加密的 RAR 壓縮檔，驗證後於伺服器端解壓。

## 結論

現在你已掌握如何使用 Aspose.Zip for .NET **解壓加密的 rar 檔案** 以及 **讀取加密 rar 檔案內容**。此函式庫負責繁重的工作，你只需專注於將解壓後的資料整合到應用程式流程中。

## 常見問題 (FAQs)

### Aspose.Zip for .NET 是否相容所有 RAR 壓縮檔版本？
Aspose.Zip for .NET 支援多種 RAR 壓縮檔版本，確保與廣泛的檔案相容。

### 我可以在商業專案中使用 Aspose.Zip for .NET 嗎？
可以，Aspose.Zip for .NET 可用於商業用途。請前往 [購買頁面](https://purchase.aspose.com/buy) 了解授權細節。

### 是否提供測試用的臨時授權？
有，您可以從 [此處](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

### 我可以在哪裡找到更多支援或社群討論？
請造訪 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 取得支援與社群討論。

### 如何取得 Aspose.Zip for .NET 的文件說明？
[文件說明](https://reference.aspose.com/zip/net/) 提供了完整的使用資訊。

**其他問答**

**Q: 密碼錯誤會發生什麼事？**  
A: Aspose.Zip 會拋出 `InvalidPasswordException`。請捕捉例外以優雅處理錯誤。

**Q: 我可以只解壓特定檔案嗎？**  
A: 可以，遍歷 `archive.Entries` 後對目標條目呼叫 `entry.ExtractToFile()`。

**Q: 能否解壓超過 2 GB 的壓縮檔？**  
A: 完全可以——Aspose.Zip 使用串流，檔案大小僅受系統資源限制。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}