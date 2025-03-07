---
title: 在 Aspose.Zip for .NET 中使用並行性壓縮文件
linktitle: 使用並行性來壓縮文件
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 學習使用 Aspose.Zip 在 .NET 中高效壓縮檔案。透過我們的逐步教程來利用並行性的力量。
weight: 17
url: /zh-hant/net/file-compression/using-parallelism-compress-files/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Zip for .NET 中使用並行性壓縮文件

## 介紹

在 .NET 開發領域，有效壓縮檔案對於優化儲存和傳輸至關重要。 Aspose.Zip for .NET 提供了一個強大的解決方案，其突出的功能之一是能夠利用並行性進行檔案壓縮。在本教程中，我們將引導您完成使用 Aspose.Zip for .NET 使用平行性來壓縮檔案的過程。

## 先決條件

在我們深入學習本教程之前，請確保您符合以下先決條件：

- 對 C# 和 .NET 開發有基本了解。
- 安裝了 Aspose.Zip for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/zip/net/).
- 文件壓縮概念的實用知識。

## 導入命名空間

首先，將必要的命名空間匯入到您的 C# 專案中。在程式碼檔案的開頭新增以下命名空間：

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## 第 1 步：設定您的文件目錄

透過在中定義路徑來確保您已準備好文件目錄`dataDir`多變的。該目錄將包含您要壓縮的檔案。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟2：初始化壓縮過程

現在，讓我們透過開啟 ZIP 檔案進行寫入來初始化壓縮過程：

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    //您的壓縮代碼將放在此。
}
```

## 第 3 步：並行讀取和壓縮文件

在 - 的裡面`using`block，開啟要壓縮的來源檔案。在此範例中，我們使用“alice29.txt”和“asyoulik.txt”：

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        //您用於並行壓縮檔案的程式碼將位於此處。
    }
}
```

## 第 4 步：建立存檔條目

使用 Aspose.Zip 為存檔中的每個檔案建立項目：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    //您的附加條目代碼將位於此處。
}
```

## 第 5 步：定義平行性標準

使用定義平行度標準`ParallelOptions`：

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## 步驟 6：保存壓縮檔案

使用指定選項儲存壓縮檔案：

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

恭喜！您已成功使用 Aspose.Zip for .NET 使用並行性來壓縮檔案。

## 結論

在本教程中，我們探索了 Aspose.Zip for .NET 中並行檔案壓縮的強大功能。透過執行這些步驟，您可以提高檔案壓縮過程的效率，最終提高 .NET 應用程式的效能。

## 常見問題解答

### Q1：我可以將 Aspose.Zip for .NET 與其他 .NET 函式庫一起使用嗎？

A1：是的，Aspose.Zip for .NET 旨在與其他 .NET 程式庫無縫整合。

### Q2：臨時許可證是否可用於測試目的？

 A2：是的，您可以從以下位置取得臨時測試許可證：[這裡](https://purchase.aspose.com/temporary-license/).

### Q3：我可以在哪裡找到額外的支援或提出問題？

 A3：訪問[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)以獲得社區支持和討論。

### Q4：有可用的範例或文件嗎？

 A4：探索[Aspose.Zip 文檔](https://reference.aspose.com/zip/net/)取得全面的範例和文件。

### Q5：如何購買 Aspose.Zip for .NET？

 A5：您可以購買 Aspose.Zip for .NET[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
