---
date: 2025-12-23
description: 學習如何使用 Aspose.Zip for .NET 為 ZIP 檔案設定密碼保護及加密，並在不壓縮的情況下以安全密碼儲存多個檔案。
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 為 ZIP 設定密碼保護
url: /zh-hant/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 為 ZIP 加密密碼保護

在現代 .NET 開發中，保護壓縮檔的安全性與壓縮本身同等重要。本教學示範 **如何對 zip 檔案設定密碼保護**，同時展示 **在 .NET 中建立不壓縮的 zip 壓縮檔** 以及 **如何加密 zip 壓縮檔**，使用 AES 加密。完成本指南後，您將擁有一套清晰、逐步的解決方案，可直接套用於任何 C# 專案。

## 快速解答
- **主要的函式庫是什麼？** Aspose.Zip for .NET  
- **可以不壓縮而儲存檔案嗎？** 可以 – 使用 `StoreCompressionSettings`。  
- **如何加入密碼？** 提供一個帶有密碼的 `AesEcryptionSettings` 實例。  
- **支援 AES‑256 嗎？** 當然 – 設定 `EncryptionMethod.AES256`。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。

## 什麼是「如何對 zip 檔案設定密碼保護」？
密碼保護為 ZIP 壓縮檔加入一層加密，確保只有知道密碼的使用者才能解壓縮其內容。Aspose.Zip 透過在建立壓縮檔時定義加密設定，使此過程變得簡單直觀。

## 為什麼使用 Aspose.Zip for .NET？
- **無外部相依性** – 純 .NET 函式庫。  
- **完整控制** 壓縮、加密與壓縮檔結構。  
- **支援現代加密** 方法，如 AES‑256。  
- **有效處理大型檔案**，搭配串流 API。

## 前置條件

在開始之前，請確保您已具備以下項目：

- **Aspose.Zip for .NET 函式庫** – 前往 **[此處](https://releases.aspose.com/zip/net/)** 下載。  
- **文件目錄** – 包含您想要壓縮的檔案的資料夾。在範例中，變數 `dataDir` 指向此位置。

## 匯入命名空間

首先，匯入使用 Aspose.Zip 所需的命名空間：

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 如何在 .NET 中建立不壓縮的 Zip 壓縮檔

### 步驟 1：開啟 Zip 檔案

此處建立一個新的壓縮檔，用以容納條目。`FileMode.Create` 旗標確保每次執行時都會產生全新的檔案。

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

### 步驟 2：開啟來源檔案

我們開啟第一個來源檔案 (`alice29.txt`)。如需儲存其他檔案，可重複此區塊。

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

### 步驟 3：建立「不壓縮的 zip 壓縮檔」

- `StoreCompressionSettings()` 告訴 Aspose.Zip **不壓縮** 該檔案，從而產生 **不壓縮的 zip 壓縮檔**。  
- `AesEcryptionSettings("p@s$", EncryptionMethod.AES256)` 為 **如何加密 zip 壓縮檔** 的設定 – 密碼為 `"p@s$"`，加密方式為 AES‑256。

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

### 步驟 4：新增壓縮檔條目並儲存

檔案被加入壓縮檔，並將壓縮檔儲存至磁碟，完成 **如何對 zip 檔案設定密碼保護** 的流程。

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

## 常見問題與技巧
- **密碼複雜度** – 使用強密碼；簡單字串易被暴力破解。  
- **串流釋放** – `using` 陳述式會自動關閉串流，避免檔案被鎖定。  
- **多檔案** – 若要加入更多檔案，只需開啟額外的 `FileStream` 物件，並對每個檔案呼叫 `CreateEntry`。  
- **相容性** – 大多數現代壓縮工具（WinRAR、7‑Zip 等）皆支援 AES‑256 加密的 ZIP。

## 常見問答

**Q: 除了 AES‑256，我可以使用其他加密方式嗎？**  
A: 可以，Aspose.Zip 支援 ZipCrypto 以及其他 AES 級別。請依需求調整 `EncryptionMethod` 列舉。

**Q: 能否對已存在的壓縮檔進行加密？**  
A: 必須使用期望的加密設定重新建立壓縮檔；Aspose.Zip 無法即時修改已存在壓縮檔的加密。

**Q: 不壓縮儲存檔案會導致壓縮檔體積變大嗎？**  
A: 會略為增加，因為直接存放原始檔案位元組。當需要快速解壓或保留原始檔案完整性時，此方式很有用。

**Q: 如何取得受密碼保護的檔案？**  
A: 使用包含相同 `AesEcryptionSettings`（密碼）的 `Archive` 實例開啟壓縮檔，即可存取。

**Q: 對檔案大小或條目數量有無限制？**  
A: Aspose.Zip 能處理大型檔案與數千筆條目，唯一限制為系統記憶體與儲存空間。

## 其他資源
- **Aspose.Zip 文件** – 詳細的 API 參考 **[此處](https://reference.aspose.com/zip/net/)**。  
- **社群支援** – 可於 **[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)** 提問。  
- **免費試用** – 取得試用版 **[此處](https://releases.aspose.com/)**。  
- **臨時授權** – 申請臨時授權 **[此處](https://purchase.aspose.com/temporary-license/)**。  
- **購買方案** – 購買完整授權 **[此處](https://purchase.aspose.com/buy)**。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}