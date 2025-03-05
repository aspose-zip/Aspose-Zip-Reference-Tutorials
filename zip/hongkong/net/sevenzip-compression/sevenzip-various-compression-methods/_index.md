---
title: 建立七個 Zip 檔案 - Aspose.Zip for .NET 教學課程
linktitle: SevenZip 具有多種壓縮方法
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 了解如何使用不同的壓縮方法透過 Aspose.Zip for .NET 建立七個 Zip 檔案。 LZMA2、BZip2 和 Store（無壓縮）的簡單步驟。
type: docs
weight: 12
url: /zh-hant/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## 介紹

在 .NET 開發領域，管理和壓縮檔案是一項常見任務。 Aspose.Zip for .NET 為處理壓縮檔案提供了強大的解決方案，提供了多種壓縮方法。在本教程中，我們將探索如何使用 Aspose.Zip for .NET 建立七個具有不同壓縮方法的 Zip 檔案。

## 先決條件

在我們深入學習本教學之前，請確保您具備以下條件：

- 對 C# 程式設計有基本了解。
- Visual Studio 安裝在您的電腦上。
-  Aspose.Zip for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/zip/net/).

## 導入命名空間

首先將必要的命名空間匯入到您的 C# 專案中。使用以下程式碼片段開始：

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## LZMA2 壓縮

```csharp
//ExStart：SevenZipWithVarious CompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//結束：SevenZipWithVarious CompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## BZip2 壓縮

```csharp
//壓縮包2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## 存儲，無壓縮

```csharp
//存儲，不壓縮
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## 結論

在本教程中，我們探索了 Aspose.Zip for .NET 在使用各種壓縮方法建立七個 Zip 檔案方面的多功能性。無論您需要高壓縮比還是根本不喜歡壓縮，Aspose.Zip 都能靈活地滿足您的要求。

## 常見問題解答

### 我可以將 Aspose.Zip for .NET 用於任何類型的檔案嗎？
是的，Aspose.Zip for .NET 支援多種檔案類型，讓您可以壓縮和解壓縮各種格式。

### Aspose.Zip for .NET 是否可以免費試用？
是的，您可以獲得免費試用[這裡](https://releases.aspose.com/).

### 在哪裡可以找到 Aspose.Zip for .NET 的文檔？
文件可用[這裡](https://reference.aspose.com/zip/net/).

### 如何取得 Aspose.Zip for .NET 的臨時授權？
可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### 在哪裡可以獲得 Aspose.Zip for .NET 支援？
您可以透過以下方式尋求支持[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37).
