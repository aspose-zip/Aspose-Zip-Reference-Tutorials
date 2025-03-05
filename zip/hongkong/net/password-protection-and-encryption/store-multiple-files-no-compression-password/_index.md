---
title: Aspose.Zip for .NET - 安全文件儲存教學課程
linktitle: 使用密碼儲存多個檔案而不進行壓縮
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 探索如何使用 Aspose.Zip for .NET 安全地儲存多個檔案而不進行壓縮。密碼保護的簡單步驟。釋放文件管理的力量！
type: docs
weight: 13
url: /zh-hant/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

在 .NET 開發領域，管理和操作文件是一項常見任務。 Aspose.Zip for .NET 是一個功能強大的函式庫，為開發人員提供無縫壓縮、解壓縮和操作 zip 檔案的功能。在本教程中，我們將深入研究一個特定的場景：儲存多個檔案而不壓縮並使用密碼保護它們。在本指南結束時，您將具備使用 Aspose.Zip for .NET 實作此功能的知識。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Zip for .NET 函式庫：確保您已安裝 Aspose.Zip for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/zip/net/).

- 文件目錄：準備一個來源檔案所在的目錄。在提供的範例中，變數`dataDir`代表您的文檔目錄。

## 導入命名空間

首先，讓我們為我們的程式碼導入必要的命名空間：

```csharp
//資源目錄的路徑。
string dataDir = "Your Document Directory"

//導入 Aspose.Zip 命名空間
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 第 1 步：開啟 Zip 文件

```csharp
//ExStart：儲存多個檔案而不帶密碼壓縮
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

此步驟涉及使用以下命令建立新的 zip 文件`FileStream`。該檔案將命名為「StoreMutlipleFilesWithoutCompressionWithPassword_out.zip」。

## 步驟2：開啟原始檔

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

在這裡，我們打開第一個來源檔案“alice29.txt”，該檔案將儲存在 zip 檔案中。

## 第 3 步：建立檔案

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

在這一步驟中，我們建立一個實例`Archive`類，指定壓縮和加密設定。我們使用`StoreCompressionSettings`儲存不壓縮的文件`AesEcryptionSettings`使用密碼（“p@s$”）套用 AES 加密。

## 第 4 步：建立存檔條目並儲存

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

最後一步涉及在存檔中建立「alice29.txt」條目並保存存檔，完成不壓縮且具有密碼保護的儲存檔案的過程。

透過總結重點並鼓勵讀者探索 Aspose.Zip for .NET 的更多可能性來結束您的教學課程。

## 結論

在本教程中，我們探討如何使用 Aspose.Zip for .NET 儲存多個檔案而不進行壓縮並使用密碼保護它們。當您繼續 .NET 開發之旅時，可以利用 Aspose.Zip 的功能來簡化檔案管理任務並增強應用程式的安全性。

---

### 常見問題解答

### 我可以將 Aspose.Zip for .NET 與其他加密方法一起使用嗎？
是的，Aspose.Zip 支援各種加密方法。檢查文檔[這裡](https://reference.aspose.com/zip/net/)了解詳情。

### 在哪裡可以獲得 Aspose.Zip for .NET 支援？
參觀[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)以獲得社區支持和討論。

### Aspose.Zip for .NET 有沒有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).

### 如何取得 Aspose.Zip for .NET 的臨時授權？
申請臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### 在哪裡可以購買 Aspose.Zip for .NET？
您可以購買 Aspose.Zip for .NET[這裡](https://purchase.aspose.com/buy).
