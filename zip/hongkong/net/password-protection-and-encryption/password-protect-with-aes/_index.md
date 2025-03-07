---
title: 保護您的檔案 - 使用 Aspose.Zip 進行 AES 加密
linktitle: 使用 AES 進行密碼保護
second_title: 用於檔案壓縮和歸檔的 Aspose.Zip .NET API
description: 了解如何使用 Aspose.Zip for .NET 和 AES 加密來增強檔案安全性。請遵循我們的逐步指南以獲得最佳保護。
weight: 11
url: /zh-hant/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 保護您的檔案 - 使用 Aspose.Zip 進行 AES 加密


## 介紹

在當今的數位時代，保護您的敏感文件至關重要，Aspose.Zip for .NET 提供了一個強大的解決方案，使用高級加密標準 (AES) 為您的檔案提供密碼保護。在本教程中，我們將探討如何使用三種金鑰長度（128 位元、192 位元和 256 位元）實施 AES 加密，以確保壓縮檔案的最高等級的安全性。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Zip for .NET：確保您已將 Aspose.Zip 程式庫整合到您的 .NET 專案中。你可以下載它[這裡](https://releases.aspose.com/zip/net/).

- 文檔目錄：有一個來源檔案所在的目錄。

## 導入命名空間

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 第 1 步：使用 AES-128 進行密碼保護

```csharp
//ExStart：使用 AES128 進行密碼保護
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//結束：PasswordProtectWithAES128
```

在此步驟中，我們建立一個 zip 檔案並使用 AES-128 加密對其進行保護。密碼「p@s$」可確保您的存檔的安全。

## 步驟 2：使用 AES-192 進行密碼保護

```csharp
//ExStart：使用 AES192 進行密碼保護
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//結束：PasswordProtectWithAES192
```

此步驟示範如何實作 AES-192 加密以增強安全性。為了一致性，使用相同的密碼“p@s$”。

## 步驟 3：使用 AES-256 進行密碼保護

```csharp
//ExStart：使用 AES256 進行密碼保護
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//結束：PasswordProtectWithAES256
```

在最後一步中，我們實作最高等級的加密 AES-256，為您的壓縮檔案提供額外的安全層。

## 結論

在本教程中，我們介紹了在 Aspose.Zip for .NET 中使用 AES 加密來密碼保護存檔的基本步驟。無論您選擇 128 位元、192 位元還是 256 位元加密，您的檔案都將受到保護，不會受到未經授權的存取。

## 經常問的問題

### 我可以將 Aspose.Zip for .NET 與其他程式語言一起使用嗎？
Aspose.Zip 主要為 .NET 應用程式設計，確保無縫整合和最佳效能。

### AES 加密方法對於敏感資料安全嗎？
是的，AES 加密被廣泛認為是保護敏感資訊的安全可靠的方法。

### 我可以更改已加密已存檔的密碼嗎？
不可以，加密存檔的密碼一旦設定就無法更改。您需要使用不同的密碼建立新的加密存檔。

### 使用 Aspose.Zip 加密的檔案類型是否有任何限制？
Aspose.Zip 支援各種文件類型的加密，確保保護不同類型資料的靈活性。

### 如果我忘記加密存檔的密碼會怎樣？
不幸的是，沒有辦法恢復加密存檔的密碼。將密碼保存在安全的位置至關重要。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
