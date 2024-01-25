---
title: Aspose.Zip for .NET - 解密 AES 加密文件
linktitle: 解壓縮 AES 加密儲存文件
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 透過這份全面的逐步指南，了解如何在 Aspose.Zip for .NET 中解壓縮 AES 加密的儲存檔案。立即增強您的 .NET 開發技能！
type: docs
weight: 19
url: /zh-hant/net/password-protection-and-encryption/decompress-aes-encrypted-stored-file/
---

## 介紹

歡迎閱讀使用 Aspose.Zip for .NET 解壓縮 AES 加密儲存檔案的逐步指南。 Aspose.Zip 是一個功能強大的 .NET 程式庫，可讓開發人員輕鬆使用壓縮檔案。在本教程中，我們將重點介紹解壓縮 AES 加密的文件，讓您清楚地了解該過程。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Zip for .NET：確保您已安裝 Aspose.Zip 函式庫。你可以找到文檔[這裡](https://reference.aspose.com/zip/net/).

- 範例 AES 加密檔案：從下列位置下載範例 AES 加密文件[這個連結](https://releases.aspose.com/zip/net/).

- 您的文件目錄：設定要儲存解壓縮檔案的目錄。將程式碼片段中的「您的文件目錄」替換為您的實際目錄路徑。

## 導入命名空間

在提供的程式碼片段中，您會注意到各種命名空間的使用。確保將這些包含在您的項目中：

```csharp
using System.IO;
using Aspose.Zip;
```

## 步驟一：定義資源目錄

確保指定資源目錄的路徑。在範例中，將“您的文件目錄”替換為實際路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 第 2 步：開啟加密存檔

```csharp
using (FileStream fs = File.OpenRead(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"))
{
    using (var extracted = File.Create(dataDir + "alice_aesextracted_out.txt"))
    {
        using (Archive archive = new Archive(fs, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
        {
            //繼續執行後續步驟...
        }
    }
}
```

## 步驟 3：解壓縮加密條目

```csharp
using (var decompressed = archive.Entries[0].Open())
{
    byte[] b = new byte[8192];
    int bytesRead;
    while (0 < (bytesRead = decompressed.Read(b, 0, b.Length)))
    {
        extracted.Write(b, 0, bytesRead);
    }
}
```

## 結論

恭喜！您已成功學習如何使用 Aspose.Zip for .NET 解壓縮 AES 加密的儲存檔案。此過程使您可以在 .NET 應用程式中有效地使用加密檔案。

## 常見問題解答

### 我可以將 Aspose.Zip for .NET 與其他加密演算法一起使用嗎？
Aspose.Zip 主要支援 AES 加密。檢查文件以獲取最新更新。

### 有試用版嗎？
是的，您可以免費試用[這裡](https://releases.aspose.com/).

### 如何獲得 Aspose.Zip for .NET 支援？
造訪支援論壇[這裡](https://forum.aspose.com/c/zip/37)獲得社區的協助。

### 壓縮和解壓支援哪些檔案格式？
Aspose.Zip 支援多種格式，包括 ZIP、7z 和 TAR。請參閱文件以取得完整清單。

### 我可以將 Aspose.Zip 用於商業目的嗎？
是的，您可以購買許可證[這裡](https://purchase.aspose.com/buy)用於商業用途。

