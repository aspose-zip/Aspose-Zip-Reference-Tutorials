---
date: 2026-08-07
description: 了解如何使用 Aspose.Zip 在 .NET 中将文件添加到 tar 并生成 TarBz2 存档。分步指南展示 tar 创建、Bzip2
  压缩以及最佳实践技巧。
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: 压缩为 TarBz2
og_description: 使用 Aspose.Zip 在 .NET 中将文件添加到 tar 并生成 TarBz2 存档。本指南涵盖 tar 创建、Bzip2
  压缩以及故障排除技巧。
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: 使用 Aspose.Zip 将文件添加到 tar 并创建 TarBz2 存档
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: 使用 Aspose.Zip 将文件添加到 tar 并创建 TarBz2 存档
url: /zh/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将文件添加到 tar 并使用 Aspose.Zip 创建 TarBz2 压缩包

在本教程中，您将学习 **如何将文件添加到 tar** 存档并使用 **Aspose.Zip** .NET 库将其压缩为紧凑的 **TarBz2** 文件。无论是构建备份工具、发布部署包，还是需要轻量级的分发捆绑，下面的步骤将指导您将文件添加到 tar 容器、应用 Bzip2 压缩，并生成可直接分享的归档文件。

## 快速答案
- **应该使用哪个库？** Aspose.Zip for .NET  
- **实现大概需要多长时间？** 约 5‑10 分钟  
- **是否需要许可证？** 生产环境需要临时许可证；提供免费试用版  
- **可以压缩多个文件吗？** 可以——随意向 tar 归档中添加条目  
- **兼容 .NET 6+ 吗？** 完全兼容，Aspose.Zip 支持 .NET Framework 与 .NET Core/5/6  

## 什么是 TarBz2 归档？

TarBz2 文件将传统的 **tar** 容器（保留目录结构和文件元数据）与 **Bzip2** 压缩相结合，生成高度压缩的 `.tar.bz2` 包。该格式在类 Unix 系统中广受欢迎，因为它在压缩率和解压速度之间取得了良好平衡。

## 为什么使用 Aspose.Zip 将文件压缩为 TarBz2？

Aspose.Zip 能在 **两次 API 调用** 内生成 TarBz2 归档，并高效处理流。它支持 **50+ 种归档和压缩格式**，可处理高达 **2 GB** 的文件而无需将整个归档加载到内存中，且可在 Windows、Linux 和 macOS 的 .NET 运行时上运行。库还提供对条目名称、时间戳和压缩级别的细粒度控制，适用于控制台工具和 Web 服务。

## 前置条件

- **Aspose.Zip for .NET** – 从官方站点下载最新包： [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **文档目录** – 包含待归档文件的文件夹。在示例中我们使用变量 `dataDir` 来引用它。

> **专业提示：** 将源文件放在专用文件夹中，以避免意外包含不需要的文件。

## 导入命名空间

首先导入所需的命名空间，以便访问 Aspose.Zip 的 Tar 和 Bzip2 类。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步骤 1：设置文档目录

定义指向存放待归档文件的文件夹的路径。

```csharp
string dataDir = "Your Document Directory";
```

> 将 `"Your Document Directory"` 替换为源文件夹的绝对或相对路径。

## 步骤 2：将文件添加到 tar 并创建 TarBz2 归档

`TarArchive` 表示一个内存中的 tar 容器，可容纳多个文件条目。  
`Bzip2Archive` 使用 Bzip2 算法压缩流。  
`CreateEntry` 方法将文件作为新条目添加到 tar 归档中。

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **将文件添加到 tar** —— 对每个需要归档的文件调用此方法。  
- `bz2.SetSource(archive)` 告诉 Bzip2 归档压缩整个 tar 流。  
- `bz2.Save(...)` 将最终的 **TarBz2** 文件写入磁盘。

**技巧：** 若要批量 **将文件添加到 tar**，只需在调用 `bz2.Save` 之前对每个文件重复执行 `archive.CreateEntry`。

## 如何将文件添加到 tar？

加载源目录，创建 `TarArchive` 实例，使用 `CreateEntry` 为每个文件添加条目，然后将 tar 流包装进 `Bzip2Archive` 并调用 `Save`。这种两步模式可以添加任意数量的文件，并在一次流畅的操作中生成 `.tar.bz2` 文件，省去临时文件或外部工具的需求。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **未找到文件** 错误 | `dataDir` 路径错误或缺少文件扩展名 | 核实完整路径并确保文件存在。 |
| **归档为空** | 在 `bz2.Save` 之前未添加条目 | 至少调用一次 `CreateEntry`。 |
| **权限被拒绝** | 应用程序没有对输出文件夹的写入权限 | 以适当权限运行程序或选择可写目录。 |

## 常见问答

**问：Aspose.Zip 是否兼容所有 .NET 应用？**  
答：兼容。它支持 .NET Framework、.NET Core、.NET 5/6 以及更高版本的运行时。

**问：能否同时压缩多个文件？**  
答：完全可以。在保存归档之前，对每个文件调用 `CreateEntry` 即可。

**问：在哪里可以找到更多文档？**  
答：详细文档请参阅 **Aspose.Zip .NET API 参考**： [Aspose.Zip .NET API 参考](https://reference.aspose.com/zip/net/)。

**问：如何获取 Aspose.Zip 的临时许可证？**  
答：您可以在此 **请求临时许可证**： [请求临时许可证](https://purchase.aspose.com/temporary-license/)。

**问：是否提供免费试用？**  
答：提供，**可从 Aspose 发布页面下载试用版**： [下载试用版](https://releases.aspose.com/)。

## 结论

现在您已经掌握了 **如何将文件添加到 tar**，使用 Bzip2 压缩 tar 流，并利用 Aspose.Zip for .NET 生成 **TarBz2** 归档。该方法快速、内存高效，适用于所有现代 .NET 平台。欢迎尝试更大的文件集、自定义条目名称，或将代码集成到您自己的备份或部署流水线中。

如果遇到任何问题，Aspose.Zip 社区随时提供帮助——只需前往 **Aspose.Zip 支持论坛**： [Aspose.Zip 支持论坛](https://forum.aspose.com/c/zip/37)。

---

**最后更新：** 2026-08-07  
**测试环境：** Aspose.Zip for .NET（最新发布）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Zip for .NET 创建 tar 归档并添加文件](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 归档](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [使用 Aspose.Zip 将文件添加到 tar 并压缩为 TarZ](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}