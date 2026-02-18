---
date: 2025-12-17
description: 學習如何在 Aspose.Zip for .NET 中使用 LZMA 壓縮，以優化儲存和資料傳輸效率。
linktitle: Compress to Lzma
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 Aspose.Zip for .NET 中壓縮 LZMA
url: /zh-hant/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Zip for .NET 中壓縮 LZMA

## 簡介

在本教學中，您將學習 **如何在 Aspose.Zip for .NET 中壓縮 LZMA**，這是一項優化儲存空間與提升資料傳輸效率的關鍵技巧。Aspose.Zip for .NET 提供強大的檔案壓縮解決方案，支援多種演算法（包括 LZMA），讓您能依需求選擇最適合的壓縮方式。

## 快速答覆
- **需要的函式庫是什麼？** Aspose.Zip for .NET  
- **本指南涵蓋哪種演算法？** LZMA 壓縮  
- **需要授權嗎？** 測試階段使用臨時授權即可；正式上線需購買完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **實作需要多長時間？** 基本檔案壓縮通常在 10 分鐘內完成。

## 如何壓縮 LZMA

## 先決條件

在開始之前，請確保您已具備以下項目：

- Aspose.Zip for .NET：確保已安裝 Aspose.Zip 套件。您可以在此取得文件說明 [here](https://reference.aspose.com/zip/net/)。  
- 文件目錄：選擇或建立一個資料夾，內含您欲壓縮的檔案。

## 匯入命名空間

在 C# 檔案的最上方加入必要的命名空間，以便使用 Aspose.Zip 的 LZMA 功能：

```csharp
using System;
using Aspose.Zip.LZMA;
```

## 步驟 1：設定文件目錄

```csharp
string dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為實際存放欲壓縮檔案之資料夾路徑。

## 步驟 2：使用 LZMA 壓縮檔案

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

此範例會建立 `LzmaArchive` 物件，指向來源檔案 (`alice29.txt`)，並將壓縮後的結果儲存為 `archive.lzma`。

## 步驟 3：顯示成功訊息

```csharp
Console.WriteLine("Successfully Compressed a File");
```

壓縮完成後，這行程式會通知使用者操作已成功。

## 結論

恭喜您！您已成功學會 **如何在 Aspose.Zip for .NET 中壓縮 LZMA**。此高效的壓縮技術能減少儲存空間佔用並加速資料傳輸，讓您的應用程式更具回應性與成本效益。

## 常見問題解答

**Q: 可以將多個檔案壓縮成同一個 LZMA 壓縮檔嗎？**  
A: 可以。於呼叫 `archive.AddFile()` 加入每一個檔案，最後再執行 `archive.Save()`。

**Q: 能否設定 LZMA 的壓縮等級？**  
A: `LzmaArchive` 類別使用預設的壓縮等級，已在速度與尺寸之間取得良好平衡。如需更細緻的控制，可透過 `LzmaEncoder` 進行進階設定。

**Q: 產生的 .lzma 檔案能在非 Windows 平台使用嗎？**  
A: 完全可以。LZMA 格式與平台無關，任何支援 LZMA 的工具皆可解壓縮。

**Q: 如何使用 Aspose.Zip 解壓縮 LZMA 壓縮檔？**  
A: 使用 `LzmaArchive` 建構子傳入壓縮檔路徑，然後呼叫 `ExtractToDirectory()` 即可將內容解壓縮。

**Q: Aspose.Zip 是否支援串流壓縮以避免將整個檔案載入記憶體？**  
A: 支援。您可以將 `Stream` 物件傳入 `SetSource()` 與 `Save()` 方法，以串流方式處理壓縮。

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.Zip for .NET（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}