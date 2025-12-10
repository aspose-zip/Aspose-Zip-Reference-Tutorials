---
date: 2025-12-10
description: 学习在 .NET 中使用 Aspose.Zip 进行并行文件压缩。通过我们的分步指南高效压缩多个文件。
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 实现并行文件压缩
url: /zh/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 进行并行文件压缩

## Introduction

在 .NET 开发领域，**并行文件压缩**对于优化存储空间和加速数据传输至关重要。Aspose.Zip for .NET 提供了强大的解决方案，其突出特性之一是能够利用并行性进行文件压缩。在本教程中，我们将手把手教您如何使用 Aspose.Zip for .NET **高效压缩多个文件**，充分发挥并行优势。

## Quick Answers
- **并行文件压缩是什么？** 一种同时压缩多个文件的技术，利用多个 CPU 核心来减少整体处理时间。  
- **哪个库在 .NET 中支持它？** Aspose.Zip for .NET 提供内置的并行压缩选项。  
- **我需要许可证吗？** 提供用于测试的临时许可证；生产环境需要完整许可证。  
- **我可以实时向 zip 添加文件吗？** 可以——对每个要包含的文件使用 `Archive.CreateEntry`。  
- **它兼容 .NET Core/5/6 吗？** 完全兼容，API 在所有现代 .NET 运行时上均可使用。

## What Is Parallel File Compression?
并行文件压缩指将压缩工作负载分配到多个线程或核心上，使多个文件（或大文件的不同部分）能够同时进行压缩。与传统的顺序压缩相比，这种方式显著缩短了创建 **zip archive c#** 所需的时间。

## Why Use Aspose.Zip for Parallel Compression?
- **速度：** 充分利用多核 CPU。  
- **可扩展性：** 处理大批量文件而不会导致处理时间成比例增加。  
- **简易性：** 高层 API 抽象了线程的复杂性。  
- **灵活性：** 兼容任何 .NET 版本，并能平滑集成到现有代码库。

## Prerequisites

在开始之前，请确保您具备以下条件：

- 具备 C# 和 .NET 开发的基础知识。  
- 已安装 Aspose.Zip for .NET 库。您可以在 **[here](https://releases.aspose.com/zip/net/)** 下载。  
- 了解标准文件压缩概念。

## Import Namespaces

首先，将所需的命名空间导入到您的 C# 文件中，以便编译器能够找到您将使用的类。

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Step 1: Set Up Your Document Directory

定义包含待压缩文件的文件夹路径。该路径存储在 `dataDir` 变量中。

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Initialize the Compression Process

打开一个新的 ZIP 文件进行写入。`using` 语句可确保操作完成后正确释放文件流。

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Step 3: Read and Compress Files in Parallel

打开每个要添加到归档的源文件。本示例使用两本经典文本，但您可以 **add files to zip** 任意数量的文档。

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Step 4: Create Archive Entries

创建 `Archive` 实例并将每个文件作为单独的条目添加。这一步实现了 **create zip archive c#** 的过程。

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Step 5: Define Parallelism Criterion

通过设置 `ParallelOptions` 来配置并行压缩。`ParallelCompressInMemory` 标志指示 Aspose.Zip 始终使用并行处理。

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Step 6: Save the Compressed Archive

最后，使用所需的选项（包括编码、注释以及前面定义的并行设置）将归档写入磁盘。

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

恭喜！您已使用 Aspose.Zip for .NET 完成了 **并行文件压缩**，高效地 **压缩多个文件** 到单个归档中。

## Common Issues & Tips

- **大文件：** 如果遇到内存压力，考虑将文件分块压缩，而不是一次性加载整个文件到内存。  
- **线程安全：** Aspose.Zip API 在并行模式下是线程安全的；避免在库外部从多个线程修改同一流。  
- **性能调优：** 如果需要在共享服务器上限制 CPU 使用率，可尝试调整 `ParallelOptions.MaxDegreeOfParallelism`。

## FAQ's

### Q1: Can I use Aspose.Zip for .NET with other .NET libraries?

A1: Yes, Aspose.Zip for .NET is designed to seamlessly integrate with other .NET libraries.

### Q2: Is a temporary license available for testing purposes?

A2: Yes, you can obtain a temporary license for testing from **[here](://purchase.aspose.com/temporary-license/)**.

### Q3: Where can I find additional support or ask questions?

A3: Visit the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** for community support and discussions.

### Q4: Are there any examples or documentation available?

A4: Explore the **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** for comprehensive examples and documentation.

### Q5: How can I purchase Aspose.Zip for .NET?

A5: You can purchase Aspose.Zip for .NET **[here](https://purchase.aspose.com/buy)**.

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}