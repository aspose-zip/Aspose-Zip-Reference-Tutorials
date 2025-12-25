---
date: 2025-12-25
description: 精通 Aspose.Zip for .NET 以建立加密的 7z 壓縮檔。本 Aspose.Zip 範例示範如何將檔案加入 7z，並使用加密與壓縮。
linktitle: Create SevenZip Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 建立加密的 7z 壓縮檔
url: /zh-hant/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 建立加密 7z 壓縮檔

## 介紹

在本教學中，您將學習 **如何使用 Aspose.Zip 程式庫 for .NET 建立加密 7z** 檔案。無論是需要保護敏感資料、遵守安全政策，或僅僅是有效壓縮檔案，本指南將帶您一步步完成——從設定專案到確認壓縮檔成功建立。讓我們一起看看如何輕鬆將檔案加入具 AES 加密的 7z 壓縮檔。

## 快速回答
- **「建立加密 7z」是什麼意思？** 意指產生一個使用 AES 加密保護的 7‑zip 壓縮檔。  
- **使用哪個程式庫？** Aspose.Zip for .NET。  
- **需要授權嗎？** 測試時暫時授權即可；正式環境需購買完整授權。  
- **可以加入多個檔案嗎？** 可以，對每個檔案重複呼叫 `CreateEntry`。  
- **支援 AES 加密嗎？** 支援，Aspose.Zip 為 7z 壓縮檔提供 AES‑256 加密。

## 什麼是加密的 7z 壓縮檔？
7z 壓縮檔是一種高壓縮率的容器格式。當您 **建立加密 7z** 壓縮檔時，內容會使用 AES 加密進行混淆，未輸入正確密碼則無法讀取。這非常適合安全傳輸或儲存機密檔案。

## 為什麼使用 Aspose.Zip 處理加密的 7z 檔案？
- **完整 .NET 整合** – 支援 .NET Framework、.NET Core 以及 .NET 5/6。  
- **內建 AES‑256 支援** – 無需額外工具。  
- **簡易 API** – 單行呼叫即可加入檔案並儲存壓縮檔。  
- **跨平台** – 可於 Windows、Linux 與 macOS 執行。

## 前置條件

在開始之前，請先確保您具備以下項目：

- **Aspose.Zip for .NET 程式庫** – 前往[此處](https://releases.aspose.com/zip/net/)下載。  
- **可寫入的資料夾** – 您的電腦上用於儲存壓縮檔的資料夾。  
- **來源檔案**（例如 `file.dat`），即您想要壓縮與加密的檔案。

## 匯入命名空間

在 C# 檔案的最上方加入所需的命名空間：

```csharp
using Aspose.Zip.SevenZip;
```

## 步驟說明指南

### 步驟 1：定義工作目錄

設定包含您欲壓縮來源檔案的資料夾路徑。

```csharp
string dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您機器上實際的路徑。

### 步驟 2：建立加密的 7z 條目

本教學的核心 – 我們開啟新檔案串流、建立 `SevenZipArchive`、加入條目，最後儲存壓縮檔。此範例將單一檔案 (`file.dat`) 以 `data.bin` 的名稱加入壓縮檔內。

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **小技巧：** 若要啟用 AES 加密，請在呼叫 `Save` 之前設定 `SevenZipArchive` 的 `Encryption` 屬性。（此處為簡潔起見省略此屬性設定。）

### 步驟 3：確認成功

印出友善訊息，以確保操作順利完成且未發生錯誤。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### 步驟 4：驗證壓縮檔（可選）

程式執行完畢後，前往包含 `archive.7z` 的資料夾，使用 7‑zip 客戶端開啟。若在第 2 步加入了加密，系統會要求輸入密碼。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **找不到檔案** | `dataDir` 或來源檔案名稱不正確 | 再次確認路徑，確保 `file.dat` 存在。 |
| **存取被拒** | 寫入權限不足 | 以提升權限執行應用程式，或選擇可寫入的資料夾。 |
| **未套用加密** | 壓縮檔未設定加密 | 在 `Save` 之前設定 `archive.Encryption = EncryptionAlgorithm.Aes256;`。 |

## 常見問答

### Q: 我可以在 .NET 使用 Aspose.Zip 處理其他壓縮格式嗎？
Aspose.Zip 主要支援 ZIP 與 7z 格式。如需處理其他格式，請尋找專門針對該格式的程式庫。

### Q: 如何使用 Aspose.Zip 從 zip 壓縮檔中解壓縮檔案？
使用 Aspose.Zip 提供的解壓功能，例如 `ExtractToDirectory` 方法，即可輕鬆將檔案從 zip 壓縮檔中解壓。

### Q: Aspose.Zip 適合大型應用程式嗎？
絕對適合！Aspose.Zip 為大型應用程式設計，提供高效的 zip 壓縮檔操作功能。

### Q: 使用 Aspose.Zip 有授權上的注意事項嗎？
是的，請確保擁有有效授權。若為臨時使用或試用，可在[此處](https://purchase.aspose.com/temporary-license/)取得暫時授權。

### Q: 我該去哪裡尋求協助或與 Aspose.Zip 社群交流？
前往 [Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37) 獲取支援、提問，並與社群互動。

## 結論

現在您已具備使用 Aspose.Zip for .NET **建立加密 7z** 壓縮檔的完整基礎。依照上述步驟，即可安全壓縮檔案、加入 7z 容器，並在需要時啟用 AES 加密。歡迎自行擴充此範例，加入更多條目、設定密碼，或整合至更大的工作流程中。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-25  
**測試環境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose