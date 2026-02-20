---
date: 2026-02-15
description: 學習如何使用 Aspose.Zip for .NET 將檔案加入 tar 並壓縮為 TarZ——一步一步的高效 .NET 檔案處理指南。
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 將檔案加入 tar 並壓縮為 TarZ
url: /zh-hant/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 將檔案加入 tar 並打包為 TarZ

## 簡介

如果您需要 **add files to tar**，然後將封存檔壓縮為 TarZ 格式，Aspose.Zip for .NET 可讓整個流程變得毫不費力。在本教學中，我們會一步步說明——從設定專案、建立 tar 封存檔、加入檔案，到最後儲存為壓縮的 .tar.z 檔案。完成後，您將擁有一段可直接嵌入任何 .NET 應用程式的可重用程式碼片段。


## 快速解答

- **哪個庫負責創建 tar 檔案？ ** Aspose.Zip for .NET
- **需要多少行程式碼？ ** 約 15 行（不含註解）
- **測試需要許可證嗎？ ** 提供免費試用版；生產環境需要許可證。
- **支援的 .NET 版本？ ** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+
- **可以壓縮資料夾而不僅僅是檔案嗎？ ** 可以—您可以使用循環新增整個目錄。

## 什麼是**將檔案加入 tar**？

將檔案加入 tar 封存檔會把它們打包成單一的、未壓縮的容器，同時保留目錄結構與檔案中繼資料。Tar 是傳統的 Unix 格式，也是許多壓縮工作流程的基礎，包括本指南中使用的 TarZ 格式。


## 為什麼要在壓縮為 TarZ 之前將檔案加入 tar？
- **Portability** – Tar 封存檔可跨平台使用，無需擔心單一檔案的處理方式。  
- **Speed** – 建立 tar 容器非常快速，之後的 Z 壓縮只需專注於縮小體積。  
- **Compatibility** – 許多舊有工具在套用 gzip 類型壓縮前，都會先期待一個 `.tar`，這正是 `.tar.z` 所提供的。

### 這對 .NET 開發人員為何重要
使用 tar 容器可讓您的 .NET 程式碼保持簡潔且可預測。您可以在記憶體中產生封存檔、直接串流回應，或儲存至磁碟，而不必處理暫存的 zip 檔。此模式特別適合建置管線、日誌彙總，或需要將一組設定檔傳送至 Linux 服務的情境。

## 前提條件

在開始撰寫程式碼之前，請確保您已具備以下項目：

- **Aspose.Zip for .NET** 已安裝。可從官方網站 [here](https://releases.aspose.com/zip/net/) 下載。  
- 您機器上有一個資料夾，內含欲封存的檔案。請將佔位路徑替換為實際目錄。

## 匯入命名空間

在 C# 檔案的最上方加入必要的 `using` 陳述式：

```csharp
using System;
using Aspose.Zip.Tar;
```

> **專業提示：** 如果您需要動態建置路徑，請使用 `Path.Combine`；它可以避免在不同作業系統上出現路徑分隔符號缺失的情況。

## 逐步指南

### 步驟 1：定義文件目錄

```csharp
string dataDir = "Your Document Directory";
```

> **此步驟的重要性：** `dataDir` 是您新增的每個檔案的基本位置。將其保存在單一變數中，可以簡化程式碼的維護，並方便在多個歸檔檔案中重複使用。

### 步驟 2：建立 Tar 歸檔並新增文件

#### 2.1：建立 Tar 歸檔實例

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> `using` 程式碼區塊確保 `TarArchive` 物件被正確釋放，包括所有檔案句柄和記憶體緩衝區。

#### 2.2：在歸檔中新增文件

在 `using` 程式碼區塊中，新增您要包含的每個檔案：

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

您可以根據需要重複使用 `CreateEntry` 來新增任意數量的文件，或遍歷目錄以程式設計方式新增文件。例如，`foreach (var file in Directory.GetFiles(dataDir))` 迴圈可以讓你處理任意數量的文件，同時保留它們的相對路徑。

#### 2.3：儲存被壓縮的 TarZ 文件

新增所有條目後，將 tar 歸檔檔案壓縮為 `.tar.z` 格式：

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

產生的 `archive.tar.z` 檔案將位於您在 `dataDir` 中指定的相同資料夾中。現在，您可以將這個壓縮包分發到任何支援 TarZ 的系統。

## 常見問題及解決方案

| 問題 | 原因 | 解決方法 |

|-------|--------|-----|

| **檔案未找到** | 路徑錯誤或缺少檔案副檔名 | 請檢查 `dataDir` 是否以路徑分隔符號結尾，以及檔案名稱是否正確。 |

| **存取被拒絕** | 目標資料夾權限不足 | 請使用相應的權限運行應用程序，或選擇一個可寫入的目錄。 |

| **壓縮檔案大於預期** | 原始檔案已被壓縮（例如，圖像、視訊） | TarZ 最適合處理文字或日誌檔案；對於已壓縮的文件，請考慮保持其原始大小。 |

### 常見陷阱

- **缺少尾部斜線** – 如果 `dataDir` 不以 `\` 或 `/` 結尾，字串拼接將產生無效路徑。

- **大型目錄** – 新增數千個檔案會消耗大量記憶體；請考慮串流條目或使用直接寫入檔案流的 `TarArchive` 重載。

- **編碼問題** – 非 ASCII 檔案名稱可能需要明確編碼處理；Aspose.Zip 預設支援 UTF-8 編碼，但請在目標平台上進行驗證。

## 常見問題解答

**問：我可以使用 Aspose.Zip for .NET 壓縮整個資料夾嗎？ **

答：當然可以。使用 `Directory.GetFiles` 循環，並為每個檔案呼叫 `CreateEntry`，同時保留相對路徑。

**問：Aspose.Zip for .NET 有沒有試用版？ **
答：是的，您可以下載免費試用版[點擊此處](https://releases.aspose.com/)來體驗 Aspose.Zip for .NET 的各項功能。

**問：哪裡可以找到 Aspose.Zip for .NET 的完整文件？ **
答：文件位於[點擊此處](https://reference.aspose.com/zip/net/)，其中詳細介紹了此程式庫的功能和使用方法。

**問：如何獲得 Aspose.Zip for .NET 的支援？ **
答：請造訪[Aspose.Zip 論壇](https://forum.aspose.com/c/zip/37)尋求協助、分享經驗並與社群交流。

**問：我可以取得 Aspose.Zip for .NET 的臨時授權嗎？ **
答：可以，如果您需要臨時許可證，可以[點擊此處](https://purchase.aspose.com/temporary-license/)取得。

## 總結

現在您已經學會如何使用 Aspose.Zip for .NET 將檔案新增至 tar 檔案中，並將結果壓縮成 TarZ 檔案。這種方法可以產生一個乾淨、可移植的軟體包，方便傳輸、儲存或進一步處理。您可以隨意修改此程式碼片段，用於批次處理目錄、將其整合到建置管道中，或將其與其他 Aspose 元件結合使用，以實現更豐富的文件工作流程。

---

**上次更新時間：** 2026-02-15
**測試版本：** Aspose.Zip for .NET 24.11
**作者：** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}