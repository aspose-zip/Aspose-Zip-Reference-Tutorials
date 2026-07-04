---
date: 2026-07-04
description: 了解如何使用 Aspose.Zip for .NET 压缩多个文件为 tar，并高效创建 tar.lz 存档。
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: 压缩为 TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 将多个文件压缩为 tar
url: /zh/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 将多个文件压缩为 tar

在现代 .NET 开发中，高效地打包文件可以显著降低部署体积并加快网络传输速度。**压缩多个文件为 tar** 是一个常见需求，当您需要轻量级、LZ 压缩的 TAR 归档用于备份、分发或云上传时。本教程将通过使用 Aspose.Zip 库的清晰、逐步 **tar.lz 压缩示例**，帮助您快速在自己的应用程序中创建 **tar.lz 归档**。

## 快速回答
- **应该使用哪个库？** Aspose.Zip for .NET.  
- **实现大概需要多长时间？** 基本示例大约 5‑10 分钟。  
- **我需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **我可以一次压缩多个文件吗？** 可以——只需在保存前添加更多条目。

## 如何使用 Aspose.Zip for .NET 压缩多个文件 tar？
加载源文件，创建 `TarArchive` 实例，使用 `CreateEntry` 添加每个文件，最后调用 `SaveLzipped` 完成。库在内部处理 TAR 结构和 LZ 压缩，因此您只需几行代码即可得到一个 `*.tar.lz` 文件。此方法在 Windows、Linux 和 macOS 上均可运行，无需任何本机依赖。

## 什么是 tar.lz 压缩？
`tar.lz` 是使用 LZMA 算法（通常简称为 **LZ**）压缩的 TAR 归档。它将 TAR 的文件分组简洁性与 LZ 的高压缩率相结合，非常适合备份文件、软件分发或任何对带宽敏感的场景。

## 为什么使用 Aspose.Zip for .NET？
Aspose.Zip 提供纯托管、跨平台的解决方案，可在无需外部工具的情况下创建 TAR、ZIP 和基于 LZ 的归档，支持超过 30 种归档格式，并在大文件上实现高达 30 % 的更佳压缩率，同时提供详细的异常信息以实现稳健的错误处理。它还能无缝集成 .NET 日志框架，并提供详细的进度事件。

## 前提条件
在开始之前，请确保您拥有：

- **Aspose.Zip for .NET** 库 – 从 [here](https://releases.aspose.com/zip/net/) 下载。  
- 包含要归档文件的文件夹。该文件夹的路径将存储在 `dataDir` 变量中（您将在第 3 步中设置）。

## 导入命名空间
添加所需的命名空间，以便编译器知道我们将使用的类所在位置。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 如何创建 tar.lz 归档 – 步骤指南

### 步骤 1：压缩单个文件
第一个示例展示了最基本的场景——将一个文件添加到 TAR 归档中，然后保存为 **tar.lz** 文件。

`TarArchive` 类表示一个可以在单个归档中容纳多个文件的 TAR 容器。  

**说明**

- `new TarArchive()` 创建一个空的 TAR 容器。  
- `CreateEntry` 将 `dataDir` 中的文件 `alice29.txt` 添加进去。  
- `SaveLzipped` 将归档写入磁盘并应用 LZ 压缩，生成 `archive.tar.lz`。

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### 步骤 2：在一个归档中压缩多个文件
通常您需要将多个文件打包在一起。只需在保存前为每个文件调用 `CreateEntry`。这演示了 **add files to tar lz** 并有效地 **compress multiple files tar**。

**说明**

- 代码遵循与步骤 1 相同的模式，但添加了第二个条目 (`lcet10.txt`)。  
- 您可以根据需要多次调用 `CreateEntry`；库会自动处理内部的 TAR 结构。

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### 步骤 3：指定文档目录
将占位符替换为实际的源文件所在路径。上述示例会使用此路径。

**说明**

- 将 `dataDir` 设置为完整的文件夹路径，例如 `@"C:\MyFiles\"`。  
- 将目录保存在变量中使代码更易复用和维护。

```csharp
string dataDir = "Your Document Directory";
```

## 常见问题与故障排除
| 症状 | 可能原因 | 解决办法 |
|---------|--------------|-----|
| `FileNotFoundException` 在运行示例时 | `dataDir` 指向不存在的文件夹或文件名拼写错误 | 验证路径和文件名；为安全起见使用 `Path.Combine`。 |
| 输出文件为 **0 KB** | `archive.SaveLzipped` 在添加任何条目之前被调用 | 确保在调用 `SaveLzipped` 之前至少有一次 `CreateEntry` 调用。 |
| 压缩速度似乎很慢 | 默认缓冲区大小处理大文件 | 如果性能关键，可考虑分块处理文件或使用异步 I/O。 |

## 结论
现在，您已经了解了使用 Aspose.Zip for .NET **压缩 tar.lz** 文件的方法，无论是处理单个文档还是文件集合。此 **tar.lz compression example** 展示了一种简洁、可用于生产的 **创建 tar lz 归档** 文件方式，便于传输或存储。您可以在添加所有所需条目后调用 `SaveLzipped`，使用相同的 API 将文件压缩为 tar.lz。

## 常见问答

**Q:** 我可以使用 Aspose.Zip for .NET 压缩任意大小的文件吗？  
**A:** 可以，库能够处理小文件和超大文件；只需确保有足够的内存和磁盘空间用于临时 TAR 结构。

**Q:** 代码是否兼容最新的 Aspose.Zip 版本？  
**A:** 示例针对当前版本；请始终保持 NuGet 包为最新，以获取错误修复和新功能。

**Q:** 是否有许可方面的考虑？  
**A:** 生产环境需要商业许可证。请参阅 [Aspose website](https://purchase.aspose.com/buy) 上的许可详情。

**Q:** 我可以在商业项目中使用它吗？  
**A:** 当然——拥有有效许可证后，您可以将该库嵌入任何商业应用程序。

**Q:** 如果遇到问题，我可以在哪里获取帮助？  
**A:** 访问 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 获取社区支持和官方帮助。

---

**最后更新：** 2026-07-04  
**测试环境：** Aspose.Zip for .NET（最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Zip for .NET 创建 tar 归档并向 tar 添加文件](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [如何使用 Aspose.Zip for .NET 压缩 tar 并创建 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [使用 Aspose.Zip 向 tar 添加文件并创建 tarxz 归档](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}