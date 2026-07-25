---
date: 2026-05-15
description: 了解如何使用 Aspose.Zip for .NET 透過簡單步驟建立受密碼保護的 ZIP 檔案並壓縮帶密碼的檔案。
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: 以個別密碼壓縮檔案
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 在 .NET 中建立受密碼保護的 ZIP 檔案
url: /zh-hant/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 在 .NET 中建立受密碼保護的 ZIP

## 介紹

在本教學中，您將學習如何使用 Aspose.Zip 在 .NET 應用程式中**建立受密碼保護的 zip**檔案。當您需要傳輸機密資料或儲存敏感文件而不讓未授權人士存取時，安全的壓縮是必不可少的。

**Aspose.Zip** 是一個 .NET 函式庫，可程式化地建立、讀取與加密 ZIP 壓縮檔。它支援 AES‑256 加密，並允許您為壓縮檔內的每個項目指定唯一的密碼。

## 快速解答
- **Aspose.Zip 的功能是什麼？** 它建立並操作 ZIP 壓縮檔，包含逐檔案的密碼保護。  
- **我可以指派多少個密碼？** 每個檔案一個獨立密碼；項目數量不限。  
- **使用哪種加密演算法？** AES‑256，提供 256 位元的安全性。  
- **測試是否需要授權？** 提供免費試用版；正式環境需購買授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 前置條件

在開始本教學之前，請確保您已具備以下前置條件：

- Aspose.Zip for .NET：確保已在您的 .NET 專案中安裝 Aspose.Zip 函式庫。您可於[此處](https://reference.aspose.com/zip/net/)取得相關文件。

- 下載：若尚未下載，請從[此連結](https://releases.aspose.com/zip/net/)取得 Aspose.Zip for .NET 函式庫。

- 文件目錄：準備一個包含您欲壓縮檔案的資料夾。

## 匯入命名空間

在您的 .NET 專案中，請確保匯入必要的命名空間：

`ZipFile` 是 Aspose.Zip 用於建立 ZIP 壓縮檔並為每個項目指派個別密碼的主要類別。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 如何在 .NET 中建立受密碼保護的 zip 檔案？

載入目標資料夾，實例化 `ZipFile` 物件，為每個檔案設定各自的密碼，最後呼叫 `Save` 以寫入壓縮檔。整個流程僅需幾行程式碼，即可確保每個項目皆以您指定的密碼加密。

### 步驟 1：設定資源目錄路徑

定義放置檔案之資源目錄的路徑。

```csharp
string dataDir = "Your Document Directory";
```

### 步驟 2：以個別密碼壓縮檔案

現在，讓我們以個別密碼壓縮檔案。我們將使用三個範例檔案（`alice29.txt`、`asyoulik.txt`、`fields.c`），為每個檔案設定不同的密碼。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

## 為何要對 ZIP 壓縮檔使用密碼保護？

Aspose.Zip 支援 **30 多種壓縮演算法**，並可使用 AES‑256 加密壓縮檔，提供最高 **256 位元的安全性**。它能在不將整個檔案載入記憶體的情況下處理數百兆位元的壓縮檔，適用於高效能伺服器端情境。此外，密碼保護有助於符合 GDPR、HIPAA 等法規要求，確保敏感資料在靜止與傳輸過程中皆保持加密。

## 結論

恭喜！您已成功學會如何使用 Aspose.Zip for .NET **建立受密碼保護的 zip** 檔案以及 **以密碼壓縮檔案**。此功能為您的壓縮檔提供額外的安全層，確保機密性並符合資料保護政策的規範。

## 常見問題

**Q: 我可以為每個檔案使用不同的加密方式嗎？**  
A: 可以，Aspose.Zip 允許您在將檔案加入壓縮檔時為每個項目選擇加密演算法（例如 AES‑256）。

**Q: 是否提供試用版？**  
A: 有，您可於[此處](https://releases.aspose.com/)取得 Aspose.Zip for .NET 的免費試用版。

**Q: 若遇到問題，我該如何取得支援？**  
A: 請前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)尋求社群與 Aspose 支援。

**Q: 我在哪裡可以找到 Aspose.Zip for .NET 的詳細文件？**  
A: 文件可於[此處](https://reference.aspose.com/zip/net/)取得。

**Q: 我可以購買臨時授權以供測試使用嗎？**  
A: 可以，您可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

---

**最後更新：** 2026-05-15  
**測試版本：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Zip for .NET 建立受密碼保護的 ZIP](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [使用 Aspose.Zip 以 AES 加密保護 ZIP 檔案](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [在 Aspose.Zip .NET 中以加密壓縮多個檔案](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}