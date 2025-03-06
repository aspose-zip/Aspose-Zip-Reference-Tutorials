---
title: 使用 Aspose.Zip 在 .NET 中進行安全性檔案壓縮
linktitle: 使用單獨的密碼壓縮文件
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 了解如何增強 .NET 應用程式中的檔案安全性！請按照我們的逐步指南使用 Aspose.Zip for .NET 壓縮具有單獨密碼的檔案。
weight: 16
url: /zh-hant/net/password-protection-and-encryption/compress-files-individual-passwords/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 在 .NET 中進行安全性檔案壓縮


## 介紹

在 .NET 開發領域，有效管理和壓縮檔案是一項至關重要的任務。 Aspose.Zip for .NET 提供了強大的檔案壓縮解決方案，提供各種功能來增強您的應用程式。一個顯著的功能是能夠使用單獨的密碼壓縮文件，從而提供額外的安全層。在本教學中，我們將引導您完成使用 Aspose.Zip for .NET 壓縮具有單獨密碼的檔案的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Zip for .NET：請確定您的 .NET 專案中安裝了 Aspose.Zip 函式庫。您可以找到必要的文檔[這裡](https://reference.aspose.com/zip/net/).

- 下載：如果您還沒有下載 Aspose.Zip for .NET 函式庫，請從[這個連結](https://releases.aspose.com/zip/net/).

- 文件目錄：準備一個包含要壓縮的文件的目錄。

## 導入命名空間

在您的 .NET 專案中，確保導入必要的命名空間：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 第1步：設定資源目錄路徑

定義檔案所在資源目錄的路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2： 使用單獨的密碼壓縮文件

現在，讓我們使用單獨的密碼來壓縮檔案。我們將使用三個範例文件（`alice29.txt`, `asyoulik.txt` ， 和`fields.c`）每個都有不同的密碼。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        //使用單獨的密碼壓縮每個文件
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        //儲存壓縮檔案
        archive.Save(zipFile);
    }
}
```

## 結論

恭喜！您已成功學習如何使用 Aspose.Zip for .NET 來壓縮具有單獨密碼的檔案。此功能為您的壓縮檔案添加了額外的安全層，確保機密性。

## 常見問題 (FAQ)

### 我可以對每個文件使用不同的加密方法嗎？
是的，Aspose.Zip for .NET 可讓您在壓縮過程中對每個檔案使用不同的加密方法。

### 有試用版嗎？
是的，您可以存取 Aspose.Zip for .NET 的免費試用版[這裡](https://releases.aspose.com/).

### 如果遇到問題，我該如何獲得支援？
參觀[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)尋求社區的幫助和 Aspose 支持。

### 在哪裡可以找到 Aspose.Zip for .NET 的詳細文件？
文件可用[這裡](https://reference.aspose.com/zip/net/).

### 我可以購買臨時許可證用於測試目的嗎？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
