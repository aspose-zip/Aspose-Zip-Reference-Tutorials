---
date: 2026-11-18
description: 了解如何使用 Aspose.Zip 在 .NET 中将文件添加到 tar 并压缩为 tarxz 存档。遵循本分步指南，实现高效的存储和传输。
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: 压缩为 TarXz
og_description: 使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 存档。了解如何在 .NET 中快速将文件压缩为 TarXz，实现高压缩效率和跨平台兼容性。
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: 使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 存档
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: 使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 存档
url: /zh/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将文件添加到 tar 并使用 Aspose.Zip 创建 tarxz 存档

## 介绍

如果您需要 **add files to tar** 并随后 **create a tarxz archive .net**，Aspose.Zip for .NET 使该过程简洁可靠。无论是打包日志、配置文件，还是其他任何用于存储或传输的资产，压缩为 TarXz 格式都能在保持熟悉的 tar 结构的同时提供高压缩率。在本教程中，我们将逐步演示完整的操作步骤——包括代码片段——让您能够自信地在 .NET 应用程序中集成 tarxz 创建。完成后，您将了解为何 “add files to tar” 是实现紧凑、跨平台包的第一步。

## 快速答案
- **主要类是什么？** `TarArchive` 来自 `Aspose.Zip.Tar`
- **如何压缩为 tarxz？** 在添加条目后调用 `SaveXzCompressed`
- **支持哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 和 .NET 5–10
- **是否需要许可证？** 是的，生产使用需要有效的 Aspose.Zip 许可证
- **实现时间？** 基本存档大约需要 5‑10 分钟

## 什么是 TarXz 存档？

TarXz 存档将传统的 Unix `tar` 容器与 XZ 压缩相结合。tar 部分将多个文件打包成单一流，而 XZ 提供强大的无损压缩。该格式因能够保留目录结构并实现比普通 tar 或 zip 更小的文件大小，而广泛用于分发源代码、备份和大型数据集。

## 为什么使用 Aspose.Zip 在 .net 中创建 tarxz 存档？

使用 Aspose.Zip 创建 TarXz 存档提供了无需外部工具的快速单步解决方案。文件比 gzip 小 30‑50 %，且可直接在 .NET 中处理超过 20 种存档格式。该库在不将整个文件加载到内存的情况下处理大型存档，非常适合云服务和 CI 流水线。它还支持超过 50 种输入和输出格式。

## 前提条件

在开始之前，请确保您已拥有：

- 已安装 **Aspose.Zip for .NET**（从官方 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 下载）。  
- 包含要归档文件的文件夹。在下面的示例中，该文件夹由 `dataDir` 变量引用。  
- 有效的 Aspose.Zip 许可证（评估可选，生产环境必需）。

## 导入命名空间

您只需导入提供 TarXz 功能的命名空间。除核心 Aspose.Zip 库外，无需其他额外包。

## 如何使用 Aspose.Zip 将文件添加到 tar

`TarArchive` 是 Aspose.Zip 中表示 tar 容器的类。您可以通过创建 `TarArchive` 实例，然后对每个要包含的文件调用其 `AddEntry` 方法，指定源路径和可选的条目名称，将文件添加到 tar 存档中。该存档在内存中构建 tar 容器，准备进行后续的 XZ 压缩。

```csharp
using System;
using Aspose.Zip.Tar;
```

> **小贴士：** `using` 语句确保归档正确释放，释放任何非托管资源。

### 步骤 1：初始化 `TarArchive`

在 `using` 块中创建 `TarArchive` 对象，以便在操作完成时自动释放所有非托管资源。

```csharp
using (TarArchive archive = new TarArchive())
{
```

### 步骤 2：将文件添加到存档

添加您希望包含的每个文件。在本示例中我们添加了两个文本文件，但您可以根据需要添加任意数量的条目。`AddEntry` 方法接受完整的文件路径以及可选的将在 tar 中显示的条目名称。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **为什么重要：** 在压缩之前添加条目，使 Aspose.Zip 先构建 tar 容器，然后在一步中应用 XZ 压缩。

### 步骤 3：使用 XZ 压缩保存存档

`SaveXzCompressed` 方法在一步中将 tar 存档写入文件并应用 XZ 压缩，生成可供分发的 `.tar.xz` 文件。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **结果：** 您现在拥有一个完整压缩的 `archive.tar.xz` 文件，可在任何支持 TarXz 的平台上进行传输、存储或解压。

## 如何使用 Aspose.Zip 压缩 tarxz 文件

使用 Aspose.Zip 压缩为 tarxz 是一个两步过程，但通过单个方法调用封装：首先 **add files to tar**，然后调用 `SaveXzCompressed`。这消除了对外部命令行工具的需求，并将整个工作流保持在您的 .NET 代码库中。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **“文件未找到”异常** | `dataDir` 路径不正确 | 确保目录路径以反斜杠 (`\`) 结尾，或使用 `Path.Combine`。 |
| **内存使用过大** | 在内存中压缩非常大的文件 | 在流模式下使用 `TarArchive`（接受 `Stream` 的 `SaveXzCompressed` 重载）。 |
| **许可证未应用** | 缺少许可证文件 | 在应用程序启动时加载许可证：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## 常见问题

**Q: Aspose.Zip 是否兼容所有 .NET 环境？**  
A: 是的，Aspose.Zip 支持 .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 和 .NET 5–10。详情请参阅 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 如何获取 Aspose.Zip 的临时许可证？**  
A: 您可以在 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 请求临时许可证。

**Q: 是否有其他存档格式的示例？**  
A: 当然——请在 [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) 中查看完整示例集。

**Q: 在哪里可以获取帮助或讨论问题？**  
A: 加入 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 进行社区支持和官方答复的讨论。

**Q: 我可以在购买前免费试用 Aspose.Zip 吗？**  
A: 可以，免费试用可在 [Aspose.Zip download page](https://releases.aspose.com/zip/net) 获得。

## 结论

通过遵循上述步骤，您现在了解了 **how to add files to tar** 和 **compress tarxz** 文件，更重要的是，了解了如何使用 Aspose.Zip **create tarxz archive .net**。此方法为您提供了紧凑、可移植的包，可无缝集成到任何 .NET 工作流中——无论是构建桌面工具、Web 服务，还是自动化 CI/CD 流水线。

---

**最后更新：** 2026-11-18  
**已测试：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

## 相关教程

- [使用 Aspose.Zip for .NET 创建 tar 存档并添加文件到 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [如何使用 Aspose.Zip for .NET 压缩 tar 并创建 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [如何使用 Aspose.Zip for .NET 压缩多个文件为 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}