---
title: 在 Aspose.Zip for .NET 中使用并行性压缩文件
linktitle: 使用并行性来压缩文件
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 学习使用 Aspose.Zip 在 .NET 中高效压缩文件。通过我们的分步教程来利用并行性的力量。
type: docs
weight: 17
url: /zh/net/file-compression/using-parallelism-compress-files/
---
## 介绍

在 .NET 开发领域，有效压缩文件对于优化存储和传输至关重要。 Aspose.Zip for .NET 提供了一个强大的解决方案，其突出的功能之一是能够利用并行性进行文件压缩。在本教程中，我们将指导您完成使用 Aspose.Zip for .NET 使用并行性来压缩文件的过程。

## 先决条件

在我们深入学习本教程之前，请确保您满足以下先决条件：

- 对 C# 和 .NET 开发有基本了解。
- 安装了 Aspose.Zip for .NET 库。你可以下载它[这里](https://releases.aspose.com/zip/net/).
- 文件压缩概念的实用知识。

## 导入命名空间

首先，将必要的命名空间导入到您的 C# 项目中。在代码文件的开头添加以下命名空间：

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## 第 1 步：设置您的文档目录

通过在中定义路径来确保您已准备好文档目录`dataDir`多变的。该目录将包含您要压缩的文件。

```csharp
string dataDir = "Your Document Directory";
```

## 第2步：初始化压缩过程

现在，让我们通过打开 ZIP 文件进行写入来初始化压缩过程：

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    //您的压缩代码将放在此处。
}
```

## 第 3 步：并行读取和压缩文件

在 - 的里面`using`block，打开要压缩的源文件。在此示例中，我们使用“alice29.txt”和“asyoulik.txt”：

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        //您用于并行压缩文件的代码将位于此处。
    }
}
```

## 第 4 步：创建存档条目

使用 Aspose.Zip 为存档中的每个文件创建条目：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    //您的附加条目代码将位于此处。
}
```

## 第 5 步：定义并行性标准

使用定义并行度标准`ParallelOptions`：

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## 步骤 6：保存压缩档案

使用指定选项保存压缩档案：

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

恭喜！您已成功使用 Aspose.Zip for .NET 使用并行性来压缩文件。

## 结论

在本教程中，我们探索了 Aspose.Zip for .NET 中并行文件压缩的强大功能。通过执行这些步骤，您可以提高文件压缩过程的效率，最终提高 .NET 应用程序的性能。

## 常见问题解答

### Q1：我可以将 Aspose.Zip for .NET 与其他 .NET 库一起使用吗？

A1：是的，Aspose.Zip for .NET 旨在与其他 .NET 库无缝集成。

### Q2：临时许可证是否可用于测试目的？

 A2：是的，您可以从以下位置获取临时测试许可证：[这里](https://purchase.aspose.com/temporary-license/).

### Q3：我在哪里可以找到额外的支持或提出问题？

 A3：访问[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)以获得社区支持和讨论。

### Q4：有可用的示例或文档吗？

 A4：探索[Aspose.Zip 文档](https://reference.aspose.com/zip/net/)获取全面的示例和文档。

### Q5：如何购买 Aspose.Zip for .NET？

 A5：您可以购买 Aspose.Zip for .NET[这里](https://purchase.aspose.com/buy).