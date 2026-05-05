---
date: 2026-02-28
description: 學習如何使用 Aspose.Zip for .NET 將資料夾加入 ZIP 檔案以及將檔案加入 ZIP。此一步一步的指南示範如何在 ASP.NET
  專案中使用 FileInfo 壓縮檔案。
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 將資料夾加入 Zip – 以 FileInfo 壓縮檔案
url: /zh-hant/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 將資料夾加入 Zip

## 介紹

如果您需要以程式方式 **建立 zip 壓縮檔**，Aspose.Zip for .NET 為您提供一套乾淨且高效能的 API，能在任何 .NET（包括 ASP.NET）應用程式中使用。在本教學中，我們將示範如何使用 `FileInfo` 類別壓縮檔案，說明如何 **將檔案加入 zip**，並解釋為何此方式非常適合現代 .NET 專案。我們也會說明如何 **將資料夾加入 zip**，讓您一次打包整個目錄。讓我們開始吧！

## 快速回答
- **建立 zip 壓縮檔最簡單的方式是什麼？** 使用 Aspose.Zip 的 `Archive` 類別搭配 `FileInfo` 物件。  
- **可以一次加入多個檔案嗎？** 可以，只要為每個檔案建立 `FileInfo`，然後呼叫 `CreateEntry`。  
- **ASP.NET 需要特別授權嗎？** 生產環境必須使用商業版 Aspose.Zip 授權；免費試用版可用於評估。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **API 是否為執行緒安全？** 是，只要每個執行緒使用自己的 `Archive` 實例即可。

## 什麼是 Zip 壓縮檔，為什麼要建立它？
Zip 壓縮檔會將一個或多個檔案打包成單一的壓縮容器。這樣可以減少儲存空間、加快網路傳輸，並簡化分發流程。無論是傳送日誌、匯出報表，或是為客戶打包資源，能夠以程式方式 **建立 zip 壓縮檔** 是每位 .NET 開發者的實用技能。

## 為什麼使用 Aspose.Zip 來將檔案加入 Zip？
- **零外部相依性** – 完全純 .NET 實作。  
- **可完全控制壓縮等級與編碼**（ASCII、UTF‑8 等）。  
- **支援大型檔案**（> 4 GB）與密碼保護。  
- **在 .NET Framework、.NET Core 與 .NET 5+ 之間提供一致的 API**。

## 前置條件

在開始撰寫程式碼之前，請確保您已具備：

1. 已安裝 **Aspose.Zip for .NET**。可從 [Aspose.Zip 下載頁面](https://releases.aspose.com/zip/net/) 取得最新套件。  
2. 您機器上有一個資料夾，內含欲壓縮的檔案（例如 `alice29.txt` 與 `fields.c`）。  

## 匯入命名空間

在任何需要操作 zip 壓縮檔的 C# 檔案中，加入以下 `using` 陳述式：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

這些命名空間讓您可以存取 `Archive` 類別、儲存選項以及標準 I/O 工具。

## 步驟說明

### 步驟 1：設定文件目錄

首先，定義保存來源檔案的資料夾。將佔位字串替換為您系統上的絕對或相對路徑：

```csharp
string dataDir = "Your Document Directory";
```

> **專業提示：** 使用 `Path.Combine` 以跨平台方式組合路徑。

### 步驟 2：開啟 Zip 檔案以寫入

建立指向輸出 zip 檔的 `FileStream`。此串流以 **Create** 模式開啟，會覆寫同名的既有檔案：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步驟 3：為每個來源檔案準備 `FileInfo` 物件

`FileInfo` 讓 Aspose.Zip 直接存取磁碟上的實體檔案。為每個欲壓縮的檔案建立一個實例：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **為什麼使用 `FileInfo`？** 它避免將整個檔案載入記憶體，對於大型檔案尤其有幫助。

### 步驟 4：建立 Archive 並加入條目

實例化 `Archive` 物件，然後對每個 `FileInfo` 呼叫 `CreateEntry`。第一個參數是檔案在 zip 內的名稱，第二個參數是來源的 `FileInfo`：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 步驟 5：以指定編碼儲存 Zip 壓縮檔

最後，將 Archive 儲存至先前開啟的 `FileStream`。此範例使用 ASCII 編碼作為條目名稱，如檔名含非 ASCII 字元，可改用 UTF‑8：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

當 `using` 區塊結束時，串流會自動關閉，zip 檔即完成。

## 如何使用 Aspose.Zip 將資料夾加入 Zip

若您需要 **將資料夾加入 zip** 而非單一檔案，流程相當簡單：

1. 使用 `DirectoryInfo.GetFiles`（若需遞迴亦可使用 `GetDirectories`）**列舉資料夾**。  
2. 為每個找到的檔案 **建立 `FileInfo`**。  
3. 使用包含資料夾名稱的相對路徑呼叫 `CreateEntry`，例如 `"MyFolder/Report.pdf"`。  

由於 API 直接使用 `FileInfo`，您永遠不必將整個檔案載入記憶體，對大型目錄亦相當安全。此技巧同樣適用於 **zip multiple files asp.net** 的情境，讓您即時產生報表集合並一次交付為單一壓縮檔。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **空的 zip 檔** | `FileInfo` 指向不存在的路徑 | 確認 `dataDir` 與檔名正確；使用 `File.Exists` 於建立條目前檢查。 |
| **檔名編碼不正確** | 使用預設編碼處理非 ASCII 名稱 | 在 `ArchiveSaveOptions` 中設定 `Encoding = Encoding.UTF8`。 |
| **大型檔案發生 OutOfMemoryException** | 將整個檔案載入記憶體 | `FileInfo` 會串流檔案；確保未在其他地方將檔案讀入 byte 陣列。 |
| **權限被拒絕** | 應用程式沒有寫入輸出資料夾的權限 | 以適當的權限執行應用程式，或改用可寫入的目錄。 |

### 常見問題解答

#### 問題1：Aspose.Zip 是否相容於所有檔案類型？

答1：Aspose.Zip 支援多種檔案類型，確保壓縮的彈性。

#### 問題2：我可以將 Aspose.Zip 用於商業專案嗎？

答2：當然可以！請造訪我們的[購買頁面](https://purchase.aspose.com/buy)以了解授權選項。

#### 問題3：如何獲得 Aspose.Zip 的支援？

答3：加入我們的[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)社區，取得協助並參與討論。

#### 問題4：是否有免費試用版？

答4：是的，您可以[在此處](https://releases.aspose.com/)取得免費試用版。

#### 問題5：如何取得 Aspose.Zip 的臨時授權？

A5：請造訪[此連結](https://purchase.aspose.com/temporary-license/)以了解有關取得臨時許可證的資訊。

## 結論

現在您已瞭解 **如何將資料夾加入 zip** 以及 **如何建立 zip 壓縮檔**，同時也知道 **如何將檔案加入 zip**，且明白此方法為 ASP.NET 及其他 .NET 應用程式的理想選擇。請自行嘗試不同的壓縮等級、編碼與加密選項，以符合您的精確需求。祝您壓縮順利！

---

**最後更新：** 2026-02-28  
**測試環境：** Aspose.Zip for .NET 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}