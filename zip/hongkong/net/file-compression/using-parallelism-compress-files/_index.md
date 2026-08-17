---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 平行壓縮在 C# 中壓縮多個檔案

## 簡介

如果您需要快速且高效地 **zip multiple files c#**，利用平行處理是最佳方案。在現代 .NET 應用程式中，建立大型 zip 壓縮檔可能成為瓶頸——尤其是處理數十或數百個檔案時。Aspose.Zip for .NET 透過內建的 **parallel zip compression**，將工作分散至所有可用的 CPU 核心，解決此問題。本教學將逐步說明整個流程：從環境設定到以平行模式儲存 zip 壓縮檔，並示範如何 **create zip archive c#** 在 .NET Core 上順利執行。

## 快速解答
- **What is parallel zip compression?** 它同時壓縮多個檔案，使用多執行緒縮短整體處理時間。  
- **Which .NET library supports it?** Aspose.Zip for .NET 提供簡單的 API 以支援平行壓縮。  
- **Do I need a license for production?** 是的，需購買完整授權；測試可使用臨時授權。  
- **Can I add files to zip on the fly?** 當然可以——對每個要加入的檔案使用 `Archive.CreateEntry`。  
- **Is it compatible with .NET 6/7?** 是的，API 在所有現代 .NET 執行環境皆相容。

## 什麼是 zip multiple files c#？
`zip multiple files c#` 指的是使用 C# 程式碼建立一個包含多個單獨檔案的單一 ZIP 壓縮檔。結合 **parallel zip compression** 後，程式庫會在不同執行緒上處理每個檔案，顯著縮短產生最終壓縮檔的時間。

## 為何使用 Aspose.Zip 進行平行壓縮？
平行壓縮可讓您利用多處理器機器的每一個核心，通常可提供 **2‑3 倍** 的吞吐量，遠快於單執行緒方式。它亦能優雅擴展：新增檔案不會線性增加實際耗時，且 API 會為您處理執行緒管理，讓您專注於業務邏輯。

- **Speed:** 利用所有邏輯處理器，將 zip 建立時間縮短最多 70 %（視一般工作負載而定）。  
- **Scalability:** 能處理 500+ 檔案的批次，而 CPU 時間不會成比例上升。  
- **Simplicity:** 高階方法隱藏了 `System.Threading.Tasks` 的複雜性。  
- **Flexibility:** 支援 .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10，亦包括 .NET 6/7 的雲端原生服務。

## 先決條件

在開始之前，請確保您已具備：

- 基本的 C# 與 .NET 開發知識。  
- 已安裝 Aspose.Zip for .NET。您可於 **[here](https://releases.aspose.com/zip/net/)** 下載。  
- 臨時或完整授權（本教學只需臨時授權即可）。

## 匯入命名空間

`Aspose.Zip` 命名空間包含處理 ZIP 壓縮檔所需的所有類型。  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

First, bring the required namespaces into your C# file so the compiler knows where to find the classes you’ll use.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## 步驟 1：設定文件目錄

定義包含欲壓縮檔案的資料夾。此路徑儲存在 `dataDir` 變數中，您可以指向磁碟上的任何位置。

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：初始化壓縮程序

開啟一個新的 ZIP 檔案以供寫入。`using` 陳述式可確保操作完成後正確釋放檔案串流，防止檔案句柄洩漏。

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## 步驟 3：平行讀取與壓縮檔案

`Parallel.ForEach` 會執行 foreach 迴圈，讓各次迭代可同時在多個執行緒上執行。

開啟每個您打算加入壓縮檔的來源檔案。本例使用兩本經典文本，但您可以 **add files to zip** 任意數量的文件。`Parallel.ForEach` 迴圈會自動將工作分配給執行緒。

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## 步驟 4：建立壓縮檔條目

`Archive` 類別是 Aspose.Zip 的頂層物件，代表您正在建立的 ZIP 容器。

`CreateEntry` 為指定的檔案在 ZIP 壓縮檔中建立新條目。每次呼叫 `CreateEntry` 都會向壓縮檔新增一個檔案條目。

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## 步驟 5：定義平行度條件

`ParallelOptions` 是 .NET 的類型，用於控制平行迴圈的執行方式。

透過設定 `ParallelOptions` 來將壓縮設定為平行執行。`ParallelCompressInMemory` 旗標指示 Aspose.Zip 永遠使用平行處理，而 `MaxDegreeOfParallelism` 則可限制同時執行的執行緒數量。

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## 步驟 6：儲存壓縮檔

最後，使用先前定義的選項（包括編碼、註解與平行設定）將壓縮檔寫入磁碟。`Save` 方法會完成 ZIP 檔的產生。

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** 若您正在壓縮非常大的檔案，建議將 `ParallelOptions.MaxDegreeOfParallelism` 設為低於邏輯處理器數量的值。這可協助在負載下保持伺服器的回應性。

### 常見使用情境

- **Batch reporting:** 為下游系統產生每日 CSV 報表的 zip 套件。  
- **Document archiving:** 將大量 PDF、影像或日誌存放於單一壓縮檔以作備份。  
- **Data export APIs:** 在單一 HTTP 回應中返回包含多個資料檔案的 zip 檔給客戶端。  

## 常見問題與技巧

- **Memory pressure on huge files:** 不要一次將整個檔案載入記憶體，可分塊串流檔案或有選擇地使用 `ParallelCompressInMemory` 模式。  
- **Thread safety:** Aspose.Zip API 在平行模式下是執行緒安全的，但在壓縮過程中避免在程式庫之外修改相同的 `FileStream`。  
- **Performance tuning:** 若需在共享伺服器上限制 CPU 使用率，可嘗試調整 `ParallelOptions.MaxDegreeOfParallelism`。

## 常見問與答

**Q: 我可以將 Aspose.Zip for .NET 與其他壓縮函式庫一起使用嗎？**  
A: 可以，Aspose.Zip 可以與其他 .NET 函式庫共存；只需保持它們的命名空間不同即可。

**Q: 是否提供臨時授權供測試使用？**  
A: 可以，您可從 **[here](https://purchase.aspose.com/temporary-license/)** 取得測試用的臨時授權。

**Q: 若遇到問題，我可以在哪裡尋求協助？**  
A: 前往 **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** 取得社群支援與討論。

**Q: 我在哪裡可以找到更多程式碼範例與詳細的 API 文件？**  
A: 瀏覽 **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** 以取得完整範例。

**Q: 我要如何購買 Aspose.Zip 的完整授權？**  
A: 您可於 **[here](https://purchase.aspose.com/buy)** 購買 Aspose.Zip for .NET。

---

**最後更新時間：** 2026-06-09  
**測試環境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [zip multiple files c# – 使用 Aspose.Zip for .NET 輕鬆壓縮](/zip/net/file-compression/compress-multiple-files/)
- [如何使用 Aspose.Zip for .NET 建立 Zip 壓縮檔並加入檔案](/zip/net/file-compression/compress-single-file/)
- [在 Aspose.Zip .NET 中使用加密壓縮多個檔案](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}