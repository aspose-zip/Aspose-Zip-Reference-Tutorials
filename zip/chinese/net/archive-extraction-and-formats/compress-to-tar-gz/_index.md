---
date: 2026-06-19
description: 了解如何使用 Aspose.Zip for .NET 将多个文件添加到 tar 并压缩为 tar.gz —— 一种快速、跨平台的构建 TarGz
  存档的方法。
keywords:
- add multiple files to tar
- compress files to tar.gz
- Aspose.Zip .NET
- tar archive .NET
- tar.gz creation
linktitle: 将文件添加到 tar
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to add multiple files to tar and compress files to tar.gz
    using Aspose.Zip for .NET – a fast, cross‑platform way to build TarGz archives.
  headline: Add multiple files to tar and create tar.gz archive with Aspose.Zip for
    .NET
  type: TechArticle
- questions:
  - answer: Yes, it works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET
      5–10 projects.
    question: Is Aspose.Zip for .NET compatible with all .NET applications?
  - answer: Visit the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      to request a trial license.
    question: How can I obtain a temporary license for Aspose.Zip for .NET?
  - answer: The library is optimized for large files; there is no hard size limit
      other than the available system memory, and it can stream archives larger than
      100 GB.
    question: Are there any file‑size limitations?
  - answer: Use the community‑driven support forum [here](https://forum.aspose.com/c/zip/37)
      for help from Aspose engineers and other developers.
    question: Where can I get support?
  - answer: Absolutely—download the free trial from the [Aspose Zip releases page](https://releases.aspose.com/zip/net/).
    question: Can I try Aspose.Zip for .NET for free?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 将多个文件添加到 tar 并创建 tar.gz 存档
url: /zh/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 将多个文件添加到 tar 并创建 tar.gz 存档

## 简介

在现代 .NET 应用程序中，**adding multiple files to tar** 和随后 **compressing files to tar.gz** 是常见需求——无论是打包日志文件、为云存储准备数据，还是为 Linux 服务器创建部署包。Aspose.Zip for .NET 提供了简洁、高性能的 API，允许您构建 tar 存档，添加任意数量的文件，并可选地将其压缩为 tar.gz 文件——全部无需外部工具。在本指南中，我们将完整演示工作流，从项目设置到可用于生产的 `archive.tar.gz`。

## 快速答案

- **应该使用哪个库？** Aspose.Zip for .NET – it supports tar, tar.gz, zip and many other formats.  
- **如何将多个文件添加到 tar？** Call `TarArchive.CreateEntry` for each file you want to include.  
- **我可以直接压缩为 tar.gz 吗？** Yes—invoke `SaveGzipped` on the `TarArchive` instance.  
- **生产环境是否需要许可证？** A valid Aspose license is required for non‑trial use.  
- **支持哪些 .NET 版本？** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.

## 什么是“add multiple files to tar”？

将多个文件添加到 tar 存档是指将多个文件（可选地包括目录）打包到一个未压缩的容器中，同时保留其原始层次结构和元数据。生成的 `.tar` 文件随后可以使用 gzip 压缩，生成 `tar.gz` 存档，这在分发和备份中被广泛使用。

## 为什么使用 Aspose.Zip 将文件压缩为 tar.gz？

Aspose.Zip 在内存中处理整个 tar 和 gzip 过程，消除了对本机工具的需求。得益于基于流的架构，它能够处理 **高达 500 GB 的存档**，而无需将整个文件加载到内存中。该库支持 **50 多种输入和输出格式**，可在 Windows、Linux 和 macOS 上运行，并提供诸如加密、密码保护和自定义条目属性等附加功能——全部通过单一的 .NET API 实现。

## 先决条件

在开始之前，请确保您具备：

- 基本的 .NET 开发经验。  
- Visual Studio（或任何首选的 IDE）。  
- 已安装 Aspose.Zip for .NET – 请参阅官方文档 [here](https://reference.aspose.com/zip/net/)。  
- 从 [this link](https://releases.aspose.com/zip/net/) 下载 Aspose.Zip 库。

## 导入命名空间

在 .NET 项目中，导入公开 tar 相关类的命名空间：

```csharp
using System;
using Aspose.Zip.Tar;
```

## 使用 Aspose.Zip for .NET 将多个文件添加到 tar 的方法

使用 Aspose.Zip，您首先加载源文件夹，实例化一个 `TarArchive`，然后遍历每个文件，调用 `CreateEntry` 将其添加到存档中。所有条目添加完毕后，调用 `SaveGzipped` 生成压缩的 `archive.tar.gz`。整个流程只需几行简洁、类型安全的 .NET 代码。

### 步骤 1：设置文档目录

定义包含您想要归档文件的文件夹。

```csharp
string dataDir = "Your Document Directory";
```

> **专业提示：** 使用 `Path.Combine` 构建路径，以避免平台特定的分隔符问题。  
> `Path.Combine` 方法安全地使用操作系统的适当分隔符连接目录和文件名。

### 步骤 2：创建 TarGz 存档

现在我们将创建 tar 存档，添加条目，并在一次流畅的操作中进行压缩。

#### 2.1 初始化 TarArchive

`TarArchive` 类是 Aspose.Zip 的顶层对象，表示内存中的 tar 容器。实例化它会准备一个空的存档，准备接受条目。

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 添加文件 – “add multiple files to tar”的核心

`CreateEntry` 在 tar 存档内部创建一个新条目。该方法接受 **entry name**（tar 内的路径）和 **source file path**（磁盘上的源文件路径）。重复调用它即可添加任意数量的文件。

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

每次调用 `CreateEntry` 都会添加一个文件；您可以遍历目录集合，以极少的代码添加数十或数百个文件。

#### 2.3 保存为 Gzipped Tar（如何将文件压缩为 tar.gz）

`SaveGzipped` 将 tar 内容写入 gzip 流，生成紧凑的 `archive.tar.gz` 文件，可用于分发或存储。

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

该方法会自动处理 gzip 头部和尾部，使您无需额外步骤即可获得符合标准的 tar.gz。

## 常见使用场景

| 场景 | 为何“add multiple files to tar”有帮助 |
|----------|----------------------------------------|
| **日志聚合** | 在上传到云存储之前，将每日日志打包成单个存档。 |
| **部署包** | 从 Windows 构建流水线为 Linux 服务器创建可移植的 tar.gz 包。 |
| **数据备份** | 在保持备份体积小的同时，保留文件夹层次结构和元数据。 |

## 常见问题与解决方案

- **文件未找到错误** – Ensure `dataDir` ends with the appropriate path separator or use `Path.Combine`.  
- **大文件导致内存压力** – Use the stream‑based overload of `CreateEntry` (`CreateEntry(string entryName, Stream source)`) to avoid loading entire files into memory.  
- **Gzip 输出损坏** – Verify that the `TarArchive` is disposed (via a `using` block) before calling `SaveGzipped`.  

## 常见问答

**Q: Aspose.Zip for .NET 是否兼容所有 .NET 应用程序？**  
A: 是的，它适用于 .NET Framework 2.0–4.8.1、 .NET Core 2.0–3.1 和 .NET 5–10 项目。

**Q: 如何获取 Aspose.Zip for .NET 的临时许可证？**  
A: 访问 [temporary‑license page](https://purchase.aspose.com/temporary-license/) 以请求试用许可证。

**Q: 是否存在文件大小限制？**  
A: 该库针对大文件进行了优化；除可用系统内存外没有硬性大小限制，并且可以流式处理大于 100 GB 的存档。

**Q: 在哪里可以获得支持？**  
A: 使用社区驱动的支持论坛 [here](https://forum.aspose.com/c/zip/37) 获取 Aspose 工程师和其他开发者的帮助。

**Q: 我可以免费试用 Aspose.Zip for .NET 吗？**  
A: 当然——从 [Aspose Zip releases page](https://releases.aspose.com/zip/net/) 下载免费试用版。

## 结论

现在您已经了解如何使用 Aspose.Zip for .NET **将多个文件添加到 tar**、创建 tar 存档，并 **将文件压缩为 tar.gz**。此方法消除了外部依赖，提供对存档内容的完整控制，并能扩展到非常大的数据集。探索诸如加密、自定义条目属性和流式 API 等额外功能，以进一步提升归档工作流。

---

**最后更新：** 2026-06-19  
**测试版本：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.Zip for .NET 压缩多个文件为 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 存档](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [如何使用 Aspose.Zip for .NET 压缩 tar 并创建 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}