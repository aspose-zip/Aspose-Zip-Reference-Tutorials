---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 并行压缩的 C# 多文件压缩

## 介绍

如果您需要 **zip multiple files c#** 快速且高效地完成，利用并行处理是最佳方案。在现代 .NET 应用程序中，创建大型 zip 存档可能成为瓶颈——尤其是处理数十或数百个文件时。Aspose.Zip for .NET 通过提供内置的 **parallel zip compression**，将工作分配到所有可用的 CPU 核心，从而消除这一痛点。在本教程中，我们将完整演示整个过程：从环境设置到保存启用并行的 zip 存档，并且还会展示如何 **create zip archive c#** 在 .NET Core 上平稳运行。

## 快速答案
- **What is parallel zip compression?** 它在同一时间压缩多个文件，使用多线程来缩短整体处理时间。  
- **Which .NET library supports it?** Aspose.Zip for .NET 提供了一个简单的 API 用于并行压缩。  
- **Do I need a license for production?** 是的，需要完整许可证；临时许可证可用于测试。  
- **Can I add files to zip on the fly?** 当然——对每个想要包含的文件使用 `Archive.CreateEntry`。  
- **Is it compatible with .NET 6/7?** 是的，API 在所有现代 .NET 运行时上均可工作。  

## 什么是 zip multiple files c#?
`zip multiple files c#` 指的是使用 C# 代码创建包含多个单独文件的单个 ZIP 存档的做法。当您将其与 **parallel zip compression** 结合时，库会在独立的线程上处理每个文件，显著缩短生成最终存档所需的时间。

## 为什么使用 Aspose.Zip 进行并行压缩？
并行压缩让您利用多处理器机器的每个核心，通常能够提供 **2‑3× faster** 的吞吐量，远高于单线程方式。它还能优雅地扩展：增加文件数量并不会线性增长实际耗时，API 为您处理线程管理，让您专注于业务逻辑。

- **Speed:** 利用所有逻辑处理器，在典型工作负载下将 zip 创建时间缩短最高达 70 %。  
- **Scalability:** 能够处理 500+ 文件的批次，而 CPU 时间不会成比例增长。  
- **Simplicity:** 高层方法隐藏了 `System.Threading.Tasks` 的复杂性。  
- **Flexibility:** 支持 .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 以及 .NET 5–10，包括用于云原生服务的 .NET 6/7。  

## 先决条件

- 基本的 C# 和 .NET 开发知识。  
- 已安装 Aspose.Zip for .NET。您可以在 **[此处](https://releases.aspose.com/zip/net/)** 下载。  
- 临时或完整许可证（本教程使用临时许可证即可）。  

## 导入命名空间

`Aspose.Zip` 命名空间包含处理 ZIP 存档所需的所有类型。  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

首先，将所需的命名空间引入您的 C# 文件，以便编译器知道在哪里查找您将使用的类。

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## 步骤 1：设置文档目录

定义包含您想要压缩的文件的文件夹。此路径存储在 `dataDir` 变量中，您可以将其指向磁盘上的任意位置。

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：初始化压缩过程

打开一个用于写入的新 ZIP 文件。`using` 语句确保在操作完成后正确释放文件流，防止文件句柄泄漏。

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

## 步骤 3：并行读取并压缩文件

`Parallel.ForEach` 执行一个 foreach 循环，循环的迭代可以在多个线程上并发运行。

打开您打算添加到存档的每个源文件。在本例中我们使用两个经典文本，但您可以 **add files to zip** 任意数量的文档。`Parallel.ForEach` 循环会自动将工作分配到各线程。

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

## 步骤 4：创建存档条目

`Archive` 类是 Aspose.Zip 的顶层对象，表示您正在构建的 ZIP 容器。

`CreateEntry` 为指定文件在 ZIP 存档中创建一个新条目。每次调用 `CreateEntry` 都会向存档中添加一个新文件条目。

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

## 步骤 5：定义并行标准

`ParallelOptions` 是一个 .NET 类型，用于控制并行循环的执行方式。

通过设置 `ParallelOptions` 来配置压缩并行运行。`ParallelCompressInMemory` 标志指示 Aspose.Zip 始终使用并行处理，而 `MaxDegreeOfParallelism` 允许您限制并发线程的数量。

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

## 步骤 6：保存压缩存档

最后，使用所需的选项（包括编码、注释以及前面定义的并行设置）将存档写入磁盘。`Save` 方法完成 ZIP 文件的生成。

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

> **Pro tip:** 如果您正在压缩非常大的文件，考虑将 `ParallelOptions.MaxDegreeOfParallelism` 设置为低于逻辑处理器数量的值。这有助于在负载下保持服务器的响应性。

### 常见用例

- **Batch reporting:** 为下游系统生成每日 CSV 报告的 zip 捆绑包。  
- **Document archiving:** 将大量 PDF、图像或日志存储在单个存档中以备份。  
- **Data export APIs:** 在单个 HTTP 响应中返回包含多个数据文件的 zip 文件给客户端。  

## 常见问题与技巧

- **Memory pressure on huge files:** 与其将整个文件加载到内存中，不如分块流式读取文件或有选择地使用 `ParallelCompressInMemory` 模式。  
- **Thread safety:** Aspose.Zip API 在并行模式下是线程安全的，但在压缩运行时避免在库外修改同一 `FileStream`。  
- **Performance tuning:** 如需在共享服务器上限制 CPU 使用率，可尝试调整 `ParallelOptions.MaxDegreeOfParallelism`。

## 常见问题

**Q: Can I use Aspose.Zip for .NET together with other compression libraries?**  
A: 是的，Aspose.Zip 可以与其他 .NET 库共存；只需保持它们的命名空间不同即可。

**Q: Is a temporary license available for testing purposes?**  
A: 是的，您可以从 **[此处](https://purchase.aspose.com/temporary-license/)** 获取用于测试的临时许可证。

**Q: Where can I ask for help if I run into problems?**  
A: 请访问 **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** 获取社区支持和讨论。

**Q: Where can I find more code examples and detailed API docs?**  
A: 请查阅 **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** 获取完整示例。

**Q: How do I purchase a full license for Aspose.Zip?**  
A: 您可以在 **[此处](https://purchase.aspose.com/buy)** 购买 Aspose.Zip for .NET。

---

**最后更新:** 2026-06-09  
**测试环境:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [zip multiple files c# – 使用 Aspose.Zip for .NET 轻松压缩](/zip/net/file-compression/compress-multiple-files/)
- [如何使用 Aspose.Zip for .NET 创建 Zip 存档并添加文件](/zip/net/file-compression/compress-single-file/)
- [在 Aspose.Zip .NET 中使用加密压缩多个文件](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}