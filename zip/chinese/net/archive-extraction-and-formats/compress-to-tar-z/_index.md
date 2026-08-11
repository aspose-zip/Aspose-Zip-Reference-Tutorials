---
date: 2026-05-30
description: 了解如何使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarZ——一步步指南，帮助实现高效的 .NET 文件处理。
keywords:
- add files to tar
- add directory to tar
- compress folders to tar
- compress files .net
linktitle: 压缩为 TarZ
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to add files to tar and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: Add files to tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/),
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarZ
url: /zh/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将文件添加到 tar 并使用 Aspise.Zip for .NET 压缩为 TarZ

## 介绍

如果您需要**add files to tar**并随后将归档压缩为 TarZ 格式，Aspose.Zip for .NET 让整个过程变得轻松。在本教程中，我们将逐步演示每一步——从设置项目、创建 tar 归档、添加文件，到最终保存为压缩的 .tar.z 文件。完成后，您将拥有一个可复用的代码片段，可直接嵌入任何 .NET 应用程序，无论是处理少量配置文件还是整个目录树。

## 快速回答
- **处理 tar 创建的库是什么？** Aspose.Zip for .NET  
- **代码行数是多少？** 大约 15 行（不包括注释）  
- **测试是否需要许可证？** 有免费试用版；生产环境需要许可证。  
- **支持的 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 和 .NET 5–10  
- **我可以压缩文件夹而不仅是文件吗？** 是的——您可以使用循环添加整个目录。  

## 什么是 **add files to tar**？

**add files to tar** 操作将选定的文件打包到单个未压缩的 tar 容器中，同时保留目录层次结构和元数据。  
在进行任何额外压缩（如 TarZ）之前，首先需要将文件加载到 tar 归档中，因为 tar 格式提供了确定性、跨平台的包，压缩算法可以高效地对其进行处理。

## 为什么在压缩为 TarZ 之前先添加文件到 tar？

首先创建 tar 容器可以将打包逻辑与压缩步骤分离，从而带来三个可衡量的好处。通过将这两个阶段分开，您可以获得可预测、可重复的归档，能够独立压缩，这使得评估压缩比率以及在不同压缩算法之间复用同一 tar 变得更容易。  
1. **可移植性** – `.tar` 文件可以在任何类 Unix 系统上解压，无需额外库。  
2. **速度** – Tar 创建本质上是流复制操作；随后进行的 Z 压缩仅专注于减小体积，通常可削减原始数据的 30‑70 %。  
3. **兼容性** – 许多传统工具（例如 `tar`、`gzip`）在应用 gzip‑style 压缩前都需要先有 `.tar`，这正是 `.tar.z` 扩展名所表示的。  

### 为什么这对 .NET 开发者很重要

使用 tar 容器可以让您的 .NET 代码保持简洁且可预测。您可以在内存中生成归档，直接流式传输到响应，或存储到磁盘，而无需处理临时 zip 文件。这种模式特别适用于构建流水线、日志聚合，或在需要将一组配置文件发送到基于 Linux 的服务时。

## 前提条件

在深入代码之前，请确保您已具备以下条件：

- 已安装 **Aspose.Zip for .NET**。从官方网站[此处](https://releases.aspose.com/zip/net/)下载。  
- 您机器上有一个文件夹，包含要归档的文件。将占位符路径替换为实际目录。

## 导入命名空间

在 C# 文件顶部添加所需的 `using` 语句：

```csharp
using System;
using Aspose.Zip.Tar;
```

> **小贴士：** 如果需要动态构建路径，请使用 `Path.Combine`；它可以避免在不同操作系统上缺少路径分隔符。

## 如何使用 Aspose.Zip for .NET 将文件添加到 tar？

加载源目录，创建 `TarArchive` 实例，添加每个文件（或整个子目录），最后使用 TarZ 压缩标志调用 `Save`。此端到端流程仅需几行代码，并在所有受支持的 .NET 运行时上运行。

### 定义锚点

`TarArchive` 类是 Aspose.Zip 的核心对象，表示可向其添加条目的 tar 容器。

### 步骤指南

### 步骤 1：定义文档目录

```csharp
string dataDir = "Your Document Directory";
```

> **此步骤重要原因：** `dataDir` 充当您将要添加的每个文件的基础位置。将其保存在单一变量中，使代码易于维护并可在多个归档之间复用。

### 步骤 2：创建 Tar 归档并添加文件

#### 2.1：创建 Tar 归档实例

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> `using` 块确保 `TarArchive` 对象得到正确释放，释放任何文件句柄或内存缓冲区。

#### 2.2：向归档添加文件  

`CreateEntry` 将文件添加到 tar 归档中，指定其名称和内容流。  

在 `using` 块内部，添加您想要包含的每个文件：

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

您可以根据需要重复使用 `CreateEntry` 添加任意数量的文件，或通过循环遍历目录以编程方式添加它们。例如，`foreach (var file in Directory.GetFiles(dataDir))` 循环可让您在保留相对路径的同时处理任意数量的文件。

#### 2.3：保存压缩的 TarZ 文件  

`Save` 将归档写入磁盘并应用所选的压缩格式。  

添加完所有条目后，将 tar 归档压缩为 `.tar.z` 格式：

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

生成的 `archive.tar.z` 文件将位于您在 `dataDir` 中指定的同一文件夹中。现在，您可以将此单个压缩包发送到任何支持 TarZ 的系统。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **文件未找到** | 路径错误或缺少文件扩展名 | 确认 `dataDir` 以路径分隔符结尾且文件名正确。 |
| **访问被拒绝** | 目标文件夹权限不足 | 以适当的权限运行应用程序或选择可写目录。 |
| **压缩文件大于预期** | 原始文件已压缩（例如图像、视频） | TarZ 最适用于文本或日志文件；考虑保持已压缩的文件不变。 |

### 常见陷阱需注意
- **缺少结尾斜杠** – 如果 `dataDir` 未以 `\` 或 `/` 结尾，字符串拼接将产生无效路径。  
- **大型目录** – 添加成千上万的文件可能会消耗内存；考虑流式写入条目或使用直接写入文件流的 `TarArchive` 重载。  
- **编码问题** – 非 ASCII 文件名可能需要显式的编码处理；Aspose.Zip 默认遵循 UTF‑8，但请在目标平台上进行验证。  

## 常见问题

**Q: 我可以使用 Aspose.Zip for .NET 压缩整个文件夹吗？**  
A: 当然可以。使用 `Directory.GetFiles` 循环并对每个文件调用 `CreateEntry`，保留相对路径。

**Q: Aspose.Zip for .NET 有试用版吗？**  
A: 有，您可以通过下载免费试用版[此处](https://releases.aspose.com/)来了解 Aspose.Zip for .NET 的功能。

**Q: 在哪里可以找到 Aspose.Zip for .NET 的完整文档？**  
A: 文档可在[此处](https://reference.aspose.com/zip/net/)获取，提供库功能和使用的详细信息。

**Q: 如何获取 Aspose.Zip for .NET 的支持？**  
A: 请访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 寻求帮助、分享经验并与社区交流。

**Q: 我可以为 Aspose.Zip for .NET 获取临时许可证吗？**  
A: 可以，如果您需要临时许可证，可在[此处](https://purchase.aspose.com/temporary-license/)获取。

## 结论

您现在已经学习了如何使用 Aspose.Zip for .NET **add files to tar** 并将结果压缩为 TarZ 归档。此方法为您提供了一个干净、可移植的包，便于传输、存储或进一步处理。欢迎将此代码片段用于批量处理目录、集成到构建流水线，或与其他 Aspose 组件结合，实现更丰富的文档工作流。

---

**最后更新：** 2026-05-30  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
