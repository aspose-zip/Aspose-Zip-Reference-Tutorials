---
date: 2026-02-12
description: 學習如何使用 Aspose.Zip for .NET 壓縮資料夾、有效率地建立 zip 壓縮檔，並在您的 .NET 應用程式中減少儲存空間。
linktitle: How to Zip a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 壓縮資料夾
url: /zh-hant/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 壓縮資料夾

在本教學中，您將快速且可靠地學會 **如何壓縮資料夾**，使用 Aspose.Zip for .NET。無論您是在開發桌面工具、雲端服務，或是自動備份腳本，將資料夾壓縮成 ZIP 檔案都能顯著減少儲存需求並加快網路傳輸速度。我們將逐步說明每一行程式碼的意義，並指出常見的陷阱，讓您能自信地應用此技巧。

## 快速回答
- **Aspose.Zip 的功能是什麼？** 它提供一個簡單的 .NET API，用於建立與解壓 ZIP 壓縮檔，且不需外部相依性。  
- **實作需要多長時間？** 基本的資料夾壓縮通常在 10 分鐘以內完成。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+，以及 .NET 5/6+。  
- **生產環境需要授權嗎？** 是的，商業授權是生產環境的必要條件。  
- **可以一次壓縮多個資料夾嗎？** 當然可以——對任何 `DirectoryInfo` 集合使用 `CreateEntries` 方法，即可在一次執行中 **壓縮多個資料夾**。

## 什麼是「如何壓縮資料夾」？

壓縮資料夾是指將指定目錄內的所有檔案與子資料夾打包成單一的 ZIP 檔案。此舉可減少總體大小、保留原始層級結構，並讓資料的傳輸或儲存更加便利。

## 為什麼要使用 Aspose.Zip 來完成此任務？

- **速度與效率：** 優化的演算法能快速處理大型資料夾。  
- **純 .NET：** 不需要本機二進位檔或第三方工具。  
- **功能豐富：** 支援密碼保護（`add password zip`）、串流，以及設定自訂壓縮等級（`set compression level`）。  
- **一致的 API：** 在 .NET Framework、 .NET Core 與 .NET 5/6 上表現相同，非常適合 **create zip archive .net** 的情境。  

## 先決條件

- **Aspose.Zip for .NET** – 前往[此處](https://releases.aspose.com/zip/net/)下載。  
- **開發環境** – Visual Studio、Rider，或任何支援 C# 的 IDE。  
- **文件目錄** – 在程式碼中將 `"Your Document Directory"` 替換為您想壓縮的資料夾路徑。  
- **參考文件** – 請參閱官方文件[此處](https://reference.aspose.com/zip/net/)。  

## 匯入命名空間

先匯入必要的命名空間，以取得核心壓縮類別的存取權。

```csharp
using Aspose.Zip;
using System.IO;
```

## 使用 Aspose.Zip 壓縮資料夾

以下是一個直接的範例，示範 **如何壓縮資料夾** 的內容。同樣的模式也可延伸至 **zip multiple files .net** 或建立自訂的壓縮結構。

### 步驟 1：初始化文件目錄

將變數 `dataDir` 設為您想壓縮的目錄路徑。

```csharp
string dataDir = "Your Document Directory";
```

### 步驟 2：建立輸出 ZIP 檔案

開啟兩個 `FileStream` 物件作為輸出 ZIP 檔案。此示例說明如何從同一來源產生多個壓縮檔，對於版本備份非常有用。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### 步驟 3：壓縮目錄

使用 `Archive` 類別將目標資料夾中的每個項目加入。範例使用名為 **CanterburyCorpus** 的示範資料夾，您亦可指向任何目錄。

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **專業提示：** 若需以特定壓縮等級 **create zip archive .net**，請在呼叫 `Save` 前設定 `archive.CompressionLevel`。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方法 |
|------|----------|----------|
| 空的 ZIP 檔案 | `dataDir` 指向錯誤的資料夾或缺少結尾斜線 | 確認路徑並確保資料夾內有檔案 |
| `UnauthorizedAccessException` | 應用程式缺乏檔案系統權限 | 以系統管理員身分執行 Visual Studio，或授予讀寫權限 |
| 大型目錄導致記憶體使用量過高 | 一次將所有條目載入記憶體 | 在迴圈中使用 `Archive.CreateEntryFromFile` 逐一串流檔案 |

## 常見問題 (補充)

**Q: 可以為 ZIP 檔案加密密碼嗎？**  
A: 可以。在呼叫 `Save` 前設定 `archive.Password = "yourPassword";`。

**Q: 如何只包含特定類型的檔案？**  
A: 在呼叫 `CreateEntries` 前，使用 `GetFiles("*.txt")` 或類似方式過濾 `DirectoryInfo` 集合。

**Q: 有沒有辦法在不重新建立的情況下更新既有 ZIP？**  
A: Aspose.Zip 支援透過 `Archive.UpdateEntry` 進行增量更新。

## FAQ

### Q1: 可以在商業與個人專案中同時使用 Aspose.Zip for .NET 嗎？

A1: 可以，Aspose.Zip for .NET 同時提供商業與個人使用授權。

### Q2: 有提供免費試用嗎？

A2: 有，您可以在[此處](https://releases.aspose.com/zip/net)探索免費試用。

### Q3: 如何取得 Aspose.Zip for .NET 的支援？

A3: 前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)取得社群支援，或考慮購買[臨時授權](https://purchase.aspose.com/temporary-license/)以獲得專屬協助。

### Q4: 是否有其他範例與教學可供參考？

A4: 有，請參閱[文件說明](https://reference.aspose.com/zip/net/)中完整的範例與教學。

### Q5: 可以直接購買 Aspose.Zip for .NET 嗎？

A5: 當然可以，請至[此處](https://purchase.aspose.com/buy)完成購買。

---

**最後更新：** 2026-02-12  
**測試版本：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
