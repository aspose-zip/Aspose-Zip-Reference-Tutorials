---
date: 2026-07-18
description: 了解如何使用 Aspose.Zip for .NET 将文件夹添加到 zip 并将文件添加到 zip。本分步指南展示了在 ASP.NET
  项目中如何使用 FileInfo 压缩文件。
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: 使用 FileInfo 压缩文件
og_description: 使用 Aspose.Zip for .NET 将文件夹添加到 zip。了解如何创建 zip 存档、将文件添加到 zip，以及在 ASP.NET
  中高效压缩文件夹。
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: 将文件夹添加到 Zip – 使用 Aspose.Zip for .NET 压缩文件
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: 使用 Aspose.Zip for .NET 将文件夹添加到 Zip – 使用 FileInfo 压缩文件
url: /zh/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将文件夹添加到 Zip 使用 Aspose.Zip for .NET

## 介绍

如果您需要以编程方式 **add folder to zip**，Aspose.Zip for .NET 提供了一个简洁、高性能的 API，适用于任何 .NET（包括 ASP.NET）应用程序。在本教程中，我们将演示使用 `FileInfo` 类压缩文件，向您展示如何 **add files to zip**，并解释为何此方法非常适合现代 .NET 项目。我们还将覆盖 **add folder to zip** 的具体步骤，以便您能够一次性打包整个目录。让我们开始吧！

## 快速回答
- **创建 zip 存档的最简方法是什么？** 使用 Aspose.Zip 的 `Archive` 类结合 `FileInfo` 对象。  
- **我可以一次添加多个文件吗？** 可以——只需为每个文件创建一个 `FileInfo` 并调用 `CreateEntry`。  
- **我需要为 ASP.NET 购买特殊许可证吗？** 生产环境需要商业 Aspose.Zip 许可证；免费试用可用于评估。  
- **支持哪些 .NET 版本？** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.  
- **API 是线程安全的吗？** 是的，只要每个线程使用各自的 `Archive` 实例即可。

## 什么是 Zip 存档以及为何创建它？

Zip 存档将一个或多个文件打包成单个压缩容器。这可以减少存储空间，加快网络传输，并简化分发。无论是交付日志、导出报告，还是为客户打包资源，掌握以编程方式 **how to create zip archive** 文件的技巧对任何 .NET 开发者都是宝贵的技能。

## 为什么使用 Aspose.Zip 将文件添加到 Zip？

Aspose.Zip 提供纯 .NET 解决方案，消除外部依赖，同时让开发者对压缩、编码和安全性拥有细粒度的控制。它支持大文件、密码保护，并在所有受支持的 .NET 版本中保持一致，成为传统和现代应用的可靠选择。  

- **零外部依赖** – 纯 .NET 实现。  
- **对压缩级别和编码的完整控制**（ASCII、UTF‑8 等）。  
- **支持大于 4 GB 的文件** 并提供密码保护。  
- **跨 50 多个 .NET 版本的一致 API** – 从 .NET Framework 2.0 到 .NET 10。  

## 前置条件

在深入代码之前，请确保您已拥有：

1. 已安装 **Aspose.Zip for .NET**。从 [Aspose.Zip download page](https://releases.aspose.com/zip/net/) 下载最新包。  
2. 机器上包含您想压缩的文件的文件夹（例如 `alice29.txt` 和 `fields.c`）。  

## 导入命名空间

在任何需要处理 zip 存档的 C# 文件中，添加以下 `using` 语句：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

这些命名空间让您可以访问 `Archive` 类、保存选项以及标准 I/O 实用程序。

## 步骤指南

### 步骤 1：设置文档目录

首先，定义保存源文件的文件夹。将占位符替换为系统上的绝对或相对路径：

```csharp
string dataDir = "Your Document Directory";
```

> **小贴士：** 使用 `Path.Combine` 以跨平台方式构建路径。

### 步骤 2：打开用于写入的 Zip 文件

创建指向输出 zip 文件的 `FileStream`。该流以 **Create** 模式打开，会覆盖同名的已有文件：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步骤 3：为每个源文件准备 `FileInfo` 对象

`FileInfo` 为 Aspose.Zip 提供对磁盘上物理文件的直接访问。为每个要压缩的文件创建一个实例：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **为何使用 `FileInfo`？** 它避免将整个文件加载到内存中，这对大文件尤为有用。

### 步骤 4：创建存档并添加条目

`Archive` 类是 Aspose.Zip 的核心对象，表示内存中的 zip 容器。实例化一个 `Archive` 对象，然后对每个 `FileInfo` 调用 `CreateEntry`。第一个参数是文件在 zip 中的名称，第二个参数是源 `FileInfo`：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

`CreateEntry` 方法向存档添加新的文件条目，将条目名称与源 `FileInfo` 关联，以便在保存存档时直接从磁盘流式读取数据。

### 步骤 5：使用所需编码保存 Zip 存档

最后，将存档持久化到之前打开的 `FileStream`。这里我们使用 ASCII 编码作为条目名称，但如果文件名包含非 ASCII 字符，可以切换为 UTF‑8：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

当 `using` 块结束时，流会自动关闭，zip 文件即可使用。

## 如何使用 Aspose.Zip 将文件夹添加到 Zip？

加载目标目录，枚举所有文件，并使用包含文件夹名称的相对路径添加每个文件。此方法让您能够 **add folder to zip**，无需手动列出每个文件。通过在条目名称中保留文件夹层次结构，生成的存档在解压时能够保持原始目录结构，这对许多部署场景至关重要。

1. 使用 `DirectoryInfo` 指向要压缩的文件夹。  
2. 调用 `GetFiles("*", SearchOption.AllDirectories)` 递归检索所有文件。  
3. 对每个文件，创建 `FileInfo` 并使用类似 `"MyFolder/Report.pdf"` 的路径调用 `CreateEntry`。  

由于 API 使用 `FileInfo`，它会直接从磁盘流式读取每个文件，即使文件夹包含数百兆字节，也能保持低内存使用。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **空 zip 文件** | `FileInfo` 指向不存在的路径 | 验证 `dataDir` 和文件名；在创建条目前使用 `File.Exists` 检查。 |
| **文件名编码不正确** | 对非 ASCII 名称使用默认编码 | 在 `ArchiveSaveOptions` 中设置 `Encoding = Encoding.UTF8`。 |
| **大文件导致 OutOfMemoryException** | 将整个文件加载到内存中 | `FileInfo` 流式读取文件；确保未在其他位置将文件读取到字节数组中。 |
| **权限被拒绝** | 应用程序没有对输出文件夹的写权限 | 以适当的权限运行应用，或选择可写目录。 |

## 常见问题解答

**问：我可以一次性将整个文件夹添加到 zip 存档吗？**  
答：没有单一调用的方法，但使用 `DirectoryInfo` 枚举文件并通过 `CreateEntry` 逐个添加，同样可以高效实现。

**问：Aspose.Zip 支持密码保护吗？**  
答：是的，您可以在保存之前为 `Archive` 对象设置密码，以加密整个存档。

**问：Aspose.Zip 能处理多大的 zip 文件？**  
答：该库能够处理大于 4 GB 的文件，并且可以创建超过 10 GB 的存档，而无需将整个存档加载到内存中。

**问：API 与 .NET 6 和 .NET 8 兼容吗？**  
答：完全兼容。Aspose.Zip 支持 .NET 5 到 .NET 10，覆盖所有当前的 LTS 版本。

**问：有哪些压缩级别可供选择？**  
答：您可以选择 `CompressionLevel.NoCompression`、`Fast`、`Normal` 或 `Maximum`，以在速度和体积之间取得平衡。

## 更多资源

- 下载最新的 Aspose.Zip 包： [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- 购买生产使用许可证： [purchase page](https://purchase.aspose.com/buy)  
- 从社区获取帮助： [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- 免费试用 Aspose.Zip： [free trial here](https://releases.aspose.com/)  
- 获取评估用临时许可证： [this link](https://purchase.aspose.com/temporary-license/)

## 结论

您现在已经了解了使用 Aspose.Zip for .NET **how to add folder to zip** 和 **how to create zip archive** 文件的方法，掌握了 **add files to zip** 的技巧，并明白了为何此方法非常适合 ASP.NET 及其他 .NET 应用。尝试不同的压缩级别、编码和加密选项，以满足您的精确需求。祝压缩愉快！

---

**最后更新：** 2026-07-18  
**测试环境：** Aspose.Zip for .NET 24.12 (latest)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.Zip for .NET 压缩文件夹](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – 使用 Aspose.Zip for .NET 轻松压缩多个文件](/zip/net/file-compression/compress-multiple-files/)
- [创建 Zip 存档 .NET – 使用 Aspose.Zip 进行文件压缩](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}