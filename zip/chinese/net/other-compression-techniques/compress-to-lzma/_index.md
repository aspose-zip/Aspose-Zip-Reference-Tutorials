---
date: 2026-06-24
description: 了解如何在 Aspose.Zip for .NET 中压缩 LZMA，以优化存储和数据传输效率。
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: 压缩为 LZMA
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 Aspose.Zip for .NET 中压缩 LZMA
url: /zh/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Zip for .NET 中压缩 LZMA

## 介绍

在本教程中，您将学习 **如何在 Aspose.Zip for .NET 中压缩 LZMA**，这是一项优化存储空间和提升数据传输效率的关键技能。LZMA（Lempel‑Ziv‑Markov 链算法）相比传统 ZIP 可实现高达 70 % 更小的压缩包，同时保持快速解压，适用于带宽受限的场景。

## 快速回答
- **需要的库是什么？** Aspose.Zip for .NET  
- **本指南涵盖哪种算法？** LZMA 压缩  
- **我需要许可证吗？** 临时许可证足以进行测试；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 和 .NET 5–10  
- **实现大约需要多长时间？** 对于基本文件通常在 10 分钟以内。  

## 什么是 LZMA 压缩？

LZMA 是一种高比率无损压缩算法，采用字典压缩和范围编码。它可以将文本文件压缩 30‑70 %，同时保持与 ZIP 相当的解压速度。对于大规模数据集，LZMA 可降低存储成本并加快网络传输，而不牺牲数据完整性。

## 为什么在 LZMA 中使用 Aspose.Zip？

Aspose.Zip 支持 **5 种压缩算法**（ZIP、Deflate、BZIP2、LZMA 和 ZSTD），并且能够在不将整个文件加载到内存的情况下处理高达 **4 GB** 的压缩包。该库在普通服务器上可在 **2 秒** 内处理数百页的文档，兼具性能和可扩展性。

## 前置条件

在开始之前，请确保您具备以下条件：

- Aspose.Zip for .NET：确保已安装 Aspose.Zip 库。您可以在[此处](https://reference.aspose.com/zip/net/)找到文档。  
- 文档目录：选择或创建一个包含您要压缩文件的文件夹。  

## 导入命名空间

在 C# 文件的顶部添加所需的命名空间，以便访问 Aspose.Zip 的 LZMA 功能：

```csharp
using System;
using Aspose.Zip.LZMA;
```

## 如何设置压缩的源文件夹？

指定保存待归档文件的文件夹。提供专用的源目录可确保仅处理预期文件，降低意外包含不需要数据的风险，并在同一项目中处理多个压缩任务时简化路径管理。

```csharp
string dataDir = "Your Document Directory";
```

## 如何使用 LZMA 压缩文件？

`LzmaArchive` 是 Aspose.Zip 用于创建和管理 LZMA 压缩包的类。

创建 `LzmaArchive` 实例，指向源文件，然后调用 `Save` 生成 `.lzma` 压缩包。此两行代码模式完成整个压缩工作流，内部处理流管理，并生成可用于分发或存储的紧凑文件。

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## 如何确认压缩成功？

`Console.WriteLine` 将一行文本写入标准输出控制台。

压缩包保存后，使用 `Console.WriteLine` 输出简短的确认信息。此即时反馈帮助开发者验证压缩步骤已成功完成，简化自动化构建期间的调试，并在将该例程集成到更大的应用或脚本时提供清晰的状态信息。

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## 常见问题及解决方案

- **文件未找到** – 确认路径字符串使用双反斜杠 (`\\`) 或逐字字符串 (`@"C:\\Path"`)。  
- **内存不足** – Aspose.Zip 会流式处理数据，但极大文件可能需要提升进程的内存限制。  
- **许可证未生效** – 确保在任何 Aspose.Zip 操作之前调用 `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");`。  

## 常见问答

**问：我可以将多个文件压缩到同一个 LZMA 压缩包吗？**  
答：可以。在调用 `archive.Save()` 之前，对每个文件调用 `archive.AddFile()`。

**问：有没有办法为 LZMA 设置压缩级别？**  
答：`LzmaArchive` 类使用默认压缩级别，能够在速度和体积之间取得良好平衡。如果需要细粒度控制，可通过 `LzmaEncoder` 使用高级设置。

**问：生成的 .lzma 文件能在非 Windows 平台上使用吗？**  
答：当然可以。LZMA 格式与平台无关，任何支持 LZMA 的工具都可以解压该压缩包。

**问：如何使用 Aspose.Zip 解压 LZMA 压缩包？**  
答：使用带有压缩包路径的 `LzmaArchive` 构造函数，然后调用 `ExtractToDirectory()` 提取其内容。

**问：Aspose.Zip 是否支持流式压缩以避免将整个文件加载到内存？**  
答：支持。您可以通过将 `Stream` 对象传递给 `SetSource()` 和 `Save()` 方法来使用流式处理。

---

**最后更新：** 2026-06-24  
**测试环境：** Aspose.Zip for .NET（撰写时的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.Zip for .NET 压缩文件](/zip/net/file-compression/compress-file/)
- [如何使用 Aspose.Zip for .NET 打开 GZip 压缩包及其他压缩技术](/zip/net/other-compression-techniques/)
- [compress files c# – 使用 Aspose.Zip for .NET 创建 7z 压缩包](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}