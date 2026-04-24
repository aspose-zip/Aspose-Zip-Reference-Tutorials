---
date: 2026-04-24
description: 学习如何在 .NET 中使用 Aspose.Zip 压缩 tar 并创建 TarBz2 存档。本分步指南展示了如何将文件添加到 tar 并高效生成
  tarbz2 文件。
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: 压缩为 TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 压缩 tar 并创建 TarBz2
url: /zh/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 压缩 tar 并创建 TarBz2

## 介绍

在本教程中，您将学习 **如何压缩 tar** 存档并将其转换为紧凑的 **TarBz2** 文件，使用 **Aspose.Zip** 库 for .NET。无论您是在构建备份工具、发布部署包，还是仅需一个轻量级的分发捆绑，下面的步骤将指导您将文件添加到 tar、应用 Bzip2 压缩，并生成可直接分享的存档。

在开始之前，请确保您已具备本指南后面列出的先决条件，以便顺利跟随操作。

## 快速答疑
- **应该使用哪个库？** Aspose.Zip for .NET  
- **实现需要多长时间？** 大约 5‑10 分钟  
- **我需要许可证吗？** 生产环境需要临时许可证；提供免费试用  
- **我可以压缩多个文件吗？** 可以——随意向 tar 存档添加任意数量的条目  
- **它兼容 .NET 6+ 吗？** 当然，Aspose.Zip 支持 .NET Framework 和 .NET Core/5/6  

## 什么是 TarBz2 存档？

**TarBz2** 文件将传统的 **tar** 容器（保留目录结构和文件元数据）与 **Bzip2** 压缩相结合，生成高度压缩的 `.tar.bz2` 包。该格式在类 Unix 系统中很受欢迎，因为它在压缩率和解压速度之间提供了良好的平衡。

## 为什么使用 Aspose.Zip 将文件压缩为 TarBz2？

- **速度与简洁** – 单行 API 调用即可处理 tar 创建和 Bzip2 压缩。  
- **跨平台** – 在 Windows、Linux 和 macOS .NET 运行时上均可工作。  
- **细粒度控制** – 选择要包含的文件，设置自定义条目名称，并直接流式写入磁盘。  
- **强大的 .NET 支持** – 适用于 **tar archive .net** 场景，从控制台应用到 Web 服务皆可。  

## 前置条件

- **Aspose.Zip for .NET** – 从官方网站下载最新包： [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – 包含您想要归档文件的文件夹。在示例中我们使用变量 `dataDir` 来引用它。

> **技巧提示：** 将源文件保存在专用文件夹中，以避免意外包含不需要的文件。

## 导入命名空间

首先，导入所需的命名空间，以便访问 Aspose.Zip 的 Tar 和 Bzip2 类。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 步骤 1：设置 Document Directory

定义指向包含您要归档文件的文件夹的路径。

```csharp
string dataDir = "Your Document Directory";
```

> 将 `"Your Document Directory"` 替换为指向源文件夹的绝对或相对路径。

## 步骤 2：将文件添加到 tar 并创建 TarBz2 存档

该过程的核心是创建 `TarArchive`，添加条目，然后使用 `Bzip2Archive` 包装。下面的代码演示了 **如何创建 tar** 并将其压缩为 **TarBz2**，采用简洁的 disposable‑pattern 方式。

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

- `CreateEntry` **将文件添加到 tar** – 您可以对每个需要归档的文件调用此方法。  
- `bz2.SetSource(archive)` 告诉 Bzip2 存档压缩整个 tar 流。  
- `bz2.Save(...)` 将最终的 **TarBz2** 文件写入磁盘。

**提示：** 若要批量 **将文件添加到 tar**，只需在调用 `bz2.Save` 之前为每个文件重复使用 `archive.CreateEntry`。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **File not found** 错误 | `dataDir` 路径错误或缺少文件扩展名 | 检查完整路径并确保文件存在。 |
| **Empty archive** | `bz2.Save` 前未添加任何条目 | 至少调用一次 `CreateEntry`。 |
| **Permission denied** | 应用程序没有对输出文件夹的写入权限 | 以适当的权限运行应用程序或选择可写目录。 |

## 常见问答

**Q: Aspose.Zip 是否兼容所有 .NET 应用程序？**  
A: 是的。它兼容 .NET Framework、.NET Core、.NET 5/6 以及更高版本的运行时。

**Q: 我可以同时压缩多个文件吗？**  
A: 当然。保存存档前，对每个文件调用 `CreateEntry`。

**Q: 在哪里可以找到更多文档？**  
A: 详细文档可在 [here](https://reference.aspose.com/zip/net/) 查看。

**Q: 如何获取 Aspose.Zip 的临时许可证？**  
A: 您可以在 [here](https://purchase.aspose.com/temporary-license/) 申请。

**Q: 是否提供免费试用？**  
A: 有，您可以在 [here](https://releases.aspose.com/) 下载试用版。

## 结论

您现在已经学习了 **如何压缩 tar**，将文件添加进去，并使用 Aspose.Zip for .NET 将结果包装为 Bzip2 流，从而生成 **TarBz2** 存档。此方法快速、可靠，适用于所有现代 .NET 平台。欢迎尝试更大的文件集、自定义条目名称，或将代码集成到您自己的备份或部署流水线中。

如果您遇到任何问题，Aspose.Zip 社区随时提供帮助——只需前往 [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37)。

---

**最后更新：** 2026-04-24  
**测试环境：** Aspose.Zip for .NET（最新发布）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}