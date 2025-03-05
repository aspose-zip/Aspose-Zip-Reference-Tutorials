---
title: 使用 Aspose.Zip for .NET 中的 FileInfo 壓縮文件
linktitle: 使用 FileInfo 壓縮文件
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 學習使用 Aspose.Zip for .NET 的 fileinfo 來壓縮檔案。請按照我們的逐步指南進行高效率的文件管理。
type: docs
weight: 11
url: /zh-hant/net/file-compression/compress-files-fileinfo/
---
## 介紹

歡迎來到我們關於使用 Aspose.Zip for .NET 壓縮檔案的綜合指南！如果您希望優化檔案儲存或傳輸，Aspose.Zip 是您的首選解決方案。在本教程中，我們將引導您完成使用 FileInfo 類別壓縮檔案的過程，並提供詳細的逐步指南。讓我們深入了解吧！

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1.  Aspose.Zip for .NET：確保您已安裝 Aspose.Zip 函式庫。您可以從[網站](https://releases.aspose.com/zip/net/).

2. 文檔目錄：在系統上設定一個目錄來儲存要壓縮的檔案。

## 導入命名空間

在您的 .NET 專案中，包含必要的命名空間：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## 第 1 步：設定您的文件目錄

首先，定義儲存文件的目錄。您可以使用以下程式碼：

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：使用 FileInfo 壓縮文件

現在，讓我們進入該流程的核心。我們將使用`FileInfo`類別與 Aspose.Zip 一起壓縮檔案。按著這些次序：

### 步驟 2.1：開啟 Zip 文件

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步驟2.2：建立FileInfo對象

創造`FileInfo`您要壓縮的檔案的物件：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### 步驟2.3：建立存檔並新增條目

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 步驟 2.4：儲存 Zip 文件

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

恭喜！您已使用 Aspose.Zip for .NET 中的 FileInfo 類別成功壓縮檔案。

## 結論

在本教程中，我們探索如何使用 Aspose.Zip for .NET 有效地壓縮檔案。透過執行以下步驟，您可以增強檔案管理功能並優化空間使用。嘗試不同的檔案類型和大小，體驗 Aspose.Zip 的全部潛力。

## 常見問題解答

### Q1：Aspose.Zip 是否相容於所有文件類型？

A1：Aspose.Zip 支援多種檔案類型，確保壓縮的多功能性。

### Q2：我可以將Aspose.Zip用於商業項目嗎？

 A2：當然！訪問我們的[購買頁面](https://purchase.aspose.com/buy)探索許可證選項。

### Q3：如何獲得 Aspose.Zip 的支持？

 A3：加入我們的社區[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)尋求幫助和討論。

### Q4：有免費試用嗎？

 A4: 是的，你可以抓住你的[在這裡免費試用](https://releases.aspose.com/).

### Q5：如何取得 Aspose.Zip 的臨時授權？

 A5：參觀[這個連結](https://purchase.aspose.com/temporary-license/)有關獲得臨時許可證的資訊。