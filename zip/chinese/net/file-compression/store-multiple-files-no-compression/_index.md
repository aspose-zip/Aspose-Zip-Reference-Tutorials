---
date: 2026-05-30
description: 了解如何在 .NET 中使用 Aspose.Zip for .NET 创建无压缩的 zip。本指南向您展示如何在不进行压缩的情况下压缩文件、以未压缩方式存储文件以及高效管理归档。
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: 在不压缩的情况下存储多个文件
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 在 .NET 中使用 Aspose.Zip 创建无压缩的 zip
url: /zh/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 创建无压缩的 zip

在现代 .NET 开发中，**创建无压缩的 zip** 可以显著提升归档速度并保持文件大小可预测。当您需要**无压缩地压缩文件**——例如满足监管规则、加快下游处理或确保原始字节序列保持不变时，Aspose.Zip for .NET 提供了简洁直观的 API。本教程将逐步演示如何创建无压缩的 ZIP 存档、添加文件，并将解决方案集成到您的应用程序中。

## 快速答案
- **“无压缩 zip” 是什么意思？** 它是一个 ZIP 存档，其中每个条目使用 “store” 方法存储，保持原始文件字节不变。  
- **为什么要避免压缩？** 为了加快归档速度，保持下游处理所需的原始文件大小，或满足禁止数据更改的监管要求。  
- **哪个 Aspose.Zip 类处理此操作？** `ArchiveEntrySettings` 与 `StoreCompressionSettings` 结合使用。  
- **我需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持的 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10。  

## 什么是无压缩的 zip？
**无压缩的 Zip** 是一种 ZIP 存档，其中每个文件条目使用 *store* 方法，即数据原样复制到存档中，不使用任何压缩算法。这导致存档的大小基本上等于原始文件的总和加上少量 ZIP 开销。

## 为什么在无压缩 zip 文件中使用 Aspose.Zip？
Aspose.Zip 针对高性能归档进行了优化，允许您在不使用压缩算法开销的情况下即时存储文件。它保证完整的 ZIP 兼容性，允许您混合存储和压缩条目，并提供一个抽象底层 ZIP 结构的简洁 API，使实现快速且可靠。

## 前提条件
- **Aspose.Zip for .NET** – 已集成到您的项目中。请参阅官方[文档](https://reference.aspose.com/zip/net/)了解安装步骤。  
- **.NET 开发环境** – Visual Studio、VS Code 或您喜欢的任何 IDE。  
- **文档目录** – 您机器上的一个文件夹，包含要归档的文件（例如，“Your Document Directory”）。

## 导入命名空间
在编写任何代码之前，导入所需的命名空间，以便编译器知道在哪里找到 Aspose 类。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 步骤 1：设置文档目录
定义源文件所在的路径。将占位符替换为系统上的实际文件夹。

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：创建无压缩的 Zip 存档
本教程的核心——我们创建一个使用 `StoreCompressionSettings` 配置的 `Archive` 实例。`Archive` 代表一个可以容纳多个条目的 ZIP 容器。`StoreCompressionSettings` 指定条目应以无压缩方式存储。这告诉 Aspose.Zip *存储*（即不压缩）每个条目。

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **专业提示：** 如果您需要在 **保存文件到 zip** 时对部分文件进行压缩而对其他文件保持无压缩，请为每个文件创建单独的 `ArchiveEntrySettings` 实例并将它们添加到同一个 `Archive` 中。

## 如何在 .NET 中创建无压缩的 zip？
加载源文件，实例化 `Archive` 对象，并使用 `new StoreCompressionSettings()` 的 `ArchiveEntrySettings` 添加每个文件。整个操作只需三行代码，并且运行时间与文件总大小呈线性关系，为您提供最快的归档体验。

### 步骤详解
1. **创建存档** – 使用目标流或文件路径实例化 `Archive`。  
2. **配置条目设置** – 对每个文件，创建 `ArchiveEntrySettings` 对象并将 `new StoreCompressionSettings()` 赋给其 `Compression` 属性。  
3. **添加条目** – 对每个文件调用 `archive.Add(entrySettings)`，随后使用 `archive.Save()` 完成。

## 常见问题及解决方案
| 问题 | 产生原因 | 解决方案 |
|-------|----------------|-----|
| **未找到文件** | `dataDir` 路径不正确或缺少文件扩展名。 | 验证路径并确保文件存在。使用 `Path.Combine` 进行更安全的拼接。 |
| **访问被拒绝** | 进程没有读取源文件或写入 ZIP 的权限。 | 使用适当的权限运行应用程序，或选择具有写入权限的文件夹。 |
| **ZIP 中出现意外文件大小** | 存档使用了默认压缩创建。 | 确保向 `ArchiveEntrySettings` 传递 `new StoreCompressionSettings()`。 |

## 常见问答

**问：我可以对特定文件类型进行压缩，同时对其他文件保持无压缩存储吗？**  
**答：可以，您可以为每个文件创建不同的 `ArchiveEntrySettings`，并在同一存档中混合压缩和无压缩的条目。**

**问：Aspose.Zip for .NET 是否兼容 .NET Core 和 .NET 5/6？**  
**答：完全兼容。该库支持 .NET Framework、.NET Core、.NET Standard 以及最新的 .NET 版本。**

**问：在归档过程中应如何处理异常？**  
**答：将归档代码放在 `try‑catch` 块中并记录异常细节。这可确保优雅的失败并便于调试。**

**问：Aspose.Zip 是否支持多线程归档？**  
**答：是的，您可以并行处理多个文件并将它们添加到存档中，但请记住 `Archive` 对象本身不是线程安全的；在添加条目时需要同步访问。**

**问：我能否在不进行重大代码更改的情况下将 Aspose.Zip 集成到现有项目中？**  
**答：当然可以。API 设计为简单的即插即用。请参阅官方[文档](https://reference.aspose.com/zip/net/)获取迁移指南。**

**最后更新：** 2026-05-30  
**测试环境：** Aspose.Zip for .NET（撰写时的最新版本）  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}