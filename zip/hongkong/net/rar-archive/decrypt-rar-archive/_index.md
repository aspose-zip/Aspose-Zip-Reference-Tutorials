---
description: 學習如何使用 Aspose.Zip for .NET 將 RAR 解壓縮至資料夾並解密已加密的 RAR 檔案。按照步驟說明，讀取已加密的
  RAR 檔案並指定 RAR 密碼。
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 將 RAR 解壓縮至資料夾
url: /zh-hant/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 提取 RAR 至資料夾

## 簡介

如果您需要 **extract RAR to folder** 並處理受密碼保護的壓縮檔，Aspose.Zip for .NET 讓這項工作變得輕鬆。於本教學中，我們將逐步說明如何讀取加密的 RAR 檔案、指定 RAR 密碼，並將壓縮檔內容解壓至目標目錄。無論您是開發桌面工具或伺服器端服務，都能快速且可靠地整合解密邏輯。

## 快速解答
- **What does “extract RAR to folder” mean?** 它表示開啟 RAR 壓縮檔，並將每個項目寫入磁碟上指定的目錄。  
- **Which library handles decryption?** Aspose.Zip for .NET 提供內建的加密 RAR 壓縮檔支援。  
- **Do I need a license for testing?** 可取得暫時授權供評估使用；正式環境需購買完整授權。  
- **Which .NET versions are supported?** .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。  
- **How long does the implementation take?** 基本的解壓情境通常在 10 分鐘內完成。

## 什麼是 “extract RAR to folder”？

將 RAR 壓縮檔解壓至資料夾即是將壓縮檔內的所有檔案解壓縮，並放置於您指定的目錄中。若壓縮檔已加密，必須先提供正確的密碼才能進行解壓。

## 為何使用 Aspose.Zip 來解壓加密的 RAR？

Aspose.Zip 抽象化了 RAR 格式的複雜性，能在不依賴外部套件的情況下處理標準與加密壓縮檔。它提供乾淨的物件導向 API、卓越的效能與完善的錯誤處理——非常適合想要可靠 **how to decrypt RAR** 檔案解決方案的 .NET 開發人員。

## 先決條件

在開始本教學之前，請確保已具備以下先決條件：

1. Aspose.Zip for .NET Library: 確認已在您的 .NET 專案中安裝 Aspose.Zip 套件。您可從 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 下載。  
2. Document Directory: 建立一個放置加密 RAR 壓縮檔的目錄。於範例程式碼中將 "Your Document Directory" 替換為該目錄的實際路徑。

## 匯入命名空間

首先匯入使用 Aspose.Zip 套件所需的命名空間。於您的 .NET 檔案頂部加入以下程式碼：

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## 步驟 1 – 開啟加密的 RAR 壓縮檔

首先，為加密的 RAR 檔案開啟唯讀串流。此步驟會為解密與解壓作好準備。

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## 步驟 2 – 指定 RAR 密碼（how to decrypt RAR）

現在建立 `RarArchive` 實例，並告訴 Aspose.Zip 壓縮檔的保護密碼。將 `"p@s$"` 替換為您建立加密 RAR 時所使用的實際密碼。

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## 步驟 3 – 解壓內容至資料夾（extract encrypted RAR）

最後，將所有項目解壓至您選擇的資料夾。此步驟完成 **extract RAR to folder** 操作。

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

對每個需要解密的 RAR 壓縮檔重複上述步驟，即可將 Aspose.Zip for .NET 無縫整合至您的專案中。

## 常見問題與技巧

- **Incorrect password** – 若密碼錯誤，Aspose.Zip 會拋出 `WrongPasswordException`。請再次確認傳遞給 `DecryptionPassword` 的字串。  
- **Large archives** – 若 RAR 檔案非常大，建議先解壓至暫存資料夾，再將檔案移至最終位置，以免磁碟空間不足。  
- **Path safety** – 必須驗證 `dataDir` 與輸出路徑，以防止目錄遍歷漏洞。

## 結論

恭喜！您已成功 **extracted a RAR to folder**，並學會使用 Aspose.Zip for .NET **read encrypted RAR file**。這個功能強大的套件簡化了解鎖受密碼保護壓縮檔的複雜流程，對於開發 .NET 應用程式的開發者而言，是不可或缺的工具。

## 常見問題 (FAQs)

### Aspose.Zip for .NET 是否相容所有 RAR 壓縮檔版本？

Aspose.Zip for .NET 支援多種 RAR 壓縮檔版本，確保與各種檔案的相容性。

### 我可以在商業專案中使用 Aspose.Zip for .NET 嗎？

是的，Aspose.Zip for .NET 可用於商業用途。請前往 [purchase page](https://purchase.aspose.com/buy) 了解授權細節。

### 是否提供暫時授權以供測試？

是的，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得測試用的暫時授權。

### 我可以在哪裡取得額外支援或社群討論？

請造訪 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 取得支援與社群討論。

### 如何取得 Aspose.Zip for .NET 的文件說明？

請參考 [documentation](https://reference.aspose.com/zip/net/) 取得 Aspose.Zip for .NET 的完整使用說明。

**Additional Q&A**

**Q:** 如何僅從加密的 RAR 中提取特定檔案？  
**A:** 使用 `RarArchiveEntry` 找到目標項目，並呼叫 `ExtractToFile`（在壓縮檔上已設定解密密碼）來提取。

**Q:** 如果需要動態變更輸出資料夾名稱該怎麼辦？  
**A:** 在呼叫 `ExtractToDirectory` 前，使用 `Path.Combine` 結合執行時變數來組合輸出路徑。

**Q:** Aspose.Zip 是否支援多卷 RAR 壓縮檔？  
**A:** 是的，只要所有卷都可取得，該套件即可開啟並解壓多卷 RAR 壓縮檔。

---

**最後更新：** 2026-03-13  
**測試環境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}