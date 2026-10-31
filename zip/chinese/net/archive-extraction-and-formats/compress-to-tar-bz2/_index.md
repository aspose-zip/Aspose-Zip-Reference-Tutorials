---
date: 2026-10-31
description: 了解如何在 .NET 中使用 Aspose.Zip 创建 tar 存档并将其压缩为 TarBz2 文件。分步指南展示 tar 创建、Bzip2
  压缩以及最佳实践技巧。
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: 压缩为 TarBz2
og_description: 了解如何使用 Aspose.Zip for .NET 创建 tar 存档并将其压缩为 TarBz2 文件。分步指南涵盖 tar 创建、Bzip2
  压缩以及最佳实践技巧。
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: 使用 .NET 创建 tar 存档并压缩为 TarBz2
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
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
title: 如何使用 .NET 创建 tar 存档并压缩为 TarBz2
url: /zh/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 .NET 创建 tar 存档并压缩为 TarBz2

在本教程中，您将学习 **如何创建 tar 存档** 文件，然后使用 **Aspose.Zip** 库 for .NET 将其压缩为紧凑的 **TarBz2** 包。无论您是在构建备份工具、准备部署包，还是需要轻量级的分发格式，下面的步骤将指导您将文件添加到 tar 容器、应用 Bzip2 压缩，并写入最终的 `.tar.bz2` 文件。

## 快速答案
- **应该使用哪个库？** Aspose.Zip for .NET  
- **实现需要多长时间？** 大约 5‑10 分钟  
- **我需要许可证吗？** 生产环境需要临时许可证；提供免费试用  
- **我可以压缩多个文件吗？** 是 – 可以向 tar 存档添加任意数量的条目  
- **它兼容 .NET 6+ 吗？** 完全兼容，Aspose.Zip 支持 .NET Framework 和 .NET Core/5/6  

## 什么是 TarBz2 存档？

TarBz2 文件将传统的 **tar** 容器（保留目录结构和文件元数据）与 **Bzip2** 压缩相结合，生成高度压缩的 `.tar.bz2` 包。该格式在类 Unix 系统中很受欢迎，因为它在压缩率和解压速度之间提供了良好的平衡。

## 为什么使用 Aspose.Zip 将文件压缩为 TarBz2？

Aspose.Zip 可以在 **两次 API 调用** 中生成 TarBz2 存档，同时高效处理流。它支持 **50 多种存档和压缩格式**，能够处理高达 **2 GB** 的文件而无需将整个存档加载到内存中，并可在 Windows、Linux 和 macOS .NET 运行时上运行。该库还提供对条目名称、时间戳和压缩级别的细粒度控制，使其既适用于控制台工具，也适用于 Web 服务。

## 前提条件

- **Aspose.Zip for .NET** – 从官方网站下载最新的包： [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – 包含您想要归档的文件的文件夹。在示例中我们使用变量 `dataDir` 引用它。

> **提示:** 将源文件保存在专用文件夹中，以避免意外包含不需要的文件。

## 导入命名空间

首先，导入所需的命名空间，以便访问 Aspose.Zip 的 Tar 和 Bzip2 类。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步骤 1：设置文档目录

定义指向包含您想要归档文件的文件夹的路径。

```csharp
string dataDir = "Your Document Directory";
```

> 将 `"Your Document Directory"` 替换为指向源文件夹的绝对或相对路径。

## 步骤 2：将文件添加到 tar 并创建 TarBz2 存档

`TarArchive` 类表示内存中的 tar 容器，而 `Bzip2Archive` 使用 Bzip2 算法压缩流。  
`CreateEntry` 方法向 tar 存档添加新的文件条目。

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

- `CreateEntry` **adds files to tar** – 您可以为存档中需要的每个文件调用此方法。  
- `bz2.SetSource(archive)` 告诉 Bzip2 存档压缩整个 tar 流。  
- `bz2.Save(...)` 将最终的 **TarBz2** 文件写入磁盘。

**提示:** 若要批量 **将文件添加到 tar**，只需在调用 `bz2.Save` 之前为每个文件重复 `archive.CreateEntry`。

## 如何将文件添加到 tar？

加载源目录，创建 `TarArchive` 实例，使用 `CreateEntry` 添加每个文件，然后将 tar 流包装在 `Bzip2Archive` 中并调用 `Save`。这种两步模式可以添加任意数量的文件，并在单一流畅的过程中生成 `.tar.bz2` 文件，省去临时文件或外部工具的需求。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **未找到文件** 错误 | `dataDir` 路径错误或缺少文件扩展名 | 验证完整路径并确保文件存在。 |
| **空存档** | `bz2.Save` 之前未添加任何条目 | 至少调用一次 `CreateEntry`。 |
| **权限被拒绝** | 应用程序没有对输出文件夹的写权限 | 以适当的权限运行应用程序或选择可写目录。 |

## 常见问答

**Q: Aspose.Zip 是否兼容所有 .NET 应用程序？**  
A: 是的。它兼容 .NET Framework、.NET Core、.NET 5/6 以及更高版本的运行时。

**Q: 我可以同时压缩多个文件吗？**  
A: 当然可以。在保存存档之前为每个文件调用 `CreateEntry`。

**Q: 我在哪里可以找到更多文档？**  
A: 详细文档可在 **Aspose.Zip .NET API 参考** 中找到： [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: 我如何获取 Aspose.Zip 的临时许可证？**  
A: 您可以在此 **请求临时许可证**： [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: 是否提供免费试用？**  
A: 是的，**从 Aspose 发布页面下载试用版**： [download a trial version](https://releases.aspose.com/).

您也可以 [下载试用版](https://releases.aspose.com/).

## 结论

您现在已经了解 **如何创建 tar 存档**，使用 Bzip2 压缩 tar 流，并使用 Aspose.Zip for .NET 生成 **TarBz2** 存档。该方法快速、内存高效，并可在所有现代 .NET 平台上运行。欢迎尝试更大的文件集、自定义条目名称，或将代码集成到您自己的备份或部署流水线中。

如果您遇到任何问题，Aspose.Zip 社区随时提供帮助——只需前往 **Aspose.Zip 支持论坛**： [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37)。

---

**最后更新：** 2026-10-31  
**测试环境：** Aspose.Zip for .NET (latest release)  
**作者：** Aspose  

## 相关教程

- [使用 Aspose.Zip for .NET 创建 tar 存档并添加文件到 tar](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 存档](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarZ](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}