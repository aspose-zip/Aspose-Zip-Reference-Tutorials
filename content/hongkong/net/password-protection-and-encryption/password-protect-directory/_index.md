---
title: 使用 Aspose.Zip 教學密碼保護 .NET 中的目錄
linktitle: 密碼保護目錄
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 了解如何使用 Aspose.Zip 對 .NET 中的目錄進行密碼保護。透過此逐步教學輕鬆保護您的檔案。
type: docs
weight: 10
url: /zh-hant/net/password-protection-and-encryption/password-protect-directory/
---

## 介紹

在 .NET 開發領域，管理和保護目錄是文件處理的一個重要面向。 Aspose.Zip for .NET 為密碼保護目錄提供了強大的解決方案，確保敏感資料的機密性和完整性。在本教學中，我們將指導您使用 Aspose.Zip for .NET 逐步完成密碼保護目錄的過程。

## 先決條件

在深入學習本教程之前，請確保您符合以下先決條件：

- 對 C# 程式語言有基本了解。
- Visual Studio 安裝在您的電腦上。
-  Aspose.Zip for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/zip/net/).
- 包含要受密碼保護的檔案的目錄。

## 導入命名空間

首先，您需要將必要的命名空間匯入到您的 C# 專案中。這些命名空間對於利用 Aspose.Zip for .NET 提供的功能至關重要。

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 第1步：設定資源目錄的路徑

首先，定義包含要使用密碼保護的檔案的目錄的路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 第 2 步：用密碼保護目錄

現在，讓我們深入研究執行目錄密碼保護的程式碼。我們使用`TraditionalEncryptionSettings`類別設定密碼並將其套用至指定目錄。

```csharp
//ExStart：密碼保護目錄
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //結束：密碼保護目錄
    }
}
```

## 第 3 步：程式碼解釋

讓我們分解程式碼來理解每個步驟：

- 設定輸出檔：`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)`為加密輸出建立一個新的 ZIP 檔案。

- 定義目錄：`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")`指定要受密碼保護的目錄。

- 建立和儲存條目：`archive.CreateEntries(corpus)`為指定目錄中的檔案建立條目，並且`archive.Save(zipFile)`保存受密碼保護的存檔。

## 結論

在本教學中，我們示範了使用 Aspose.Zip for .NET 使用密碼保護目錄的過程。透過執行這些步驟，您可以以使用者友好且有效率的方式確保敏感文件的安全。

---

## 經常問的問題

### Aspose.Zip for .NET 適合大型目錄嗎？
是的，Aspose.Zip for .NET 旨在高效處理大型目錄，提供最佳效能。

### 我可以更改已受保護目錄的密碼嗎？
是的，您可以透過調整密碼來修改密碼`TraditionalEncryptionSettings`相應地在代碼中。

### 使用 Aspose.Zip for .NET 有任何許可要求嗎？
是的，在生產環境中使用 Aspose.Zip for .NET 需要有效的授權。您可以獲得許可證[這裡](https://purchase.aspose.com/buy).

### Aspose.Zip for .NET 有沒有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).

### 在哪裡可以找到 Aspose.Zip for .NET 的其他支援？
您可以訪問[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)如有任何支持或疑問。

