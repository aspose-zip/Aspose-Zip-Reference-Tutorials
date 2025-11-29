---
date: 2025-11-29
description: 学习如何在 .NET 中使用 Aspose.Zip 将文件添加到 tar 并压缩为 tarbz2 格式。本分步指南展示了如何高效创建 tarbz2
  存档。
language: zh
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarBz2
url: /net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarBz2

## 介绍

欢迎阅读我们的完整指南，**如何将文件添加到 tar** 并使用 Aspose.Zip for .NET 将其压缩为 TarBz2 格式。无论您是在构建备份工具、交付部署包，还是仅仅需要一个紧凑的归档用于分发，本教程都将通过清晰的解释和实用技巧一步步带您完成。

在开始之前，请确保您已准备好所有必需的内容。

## 快速答疑
- **应该使用哪个库？** Aspose.Zip for .NET
- **实现大概需要多长时间？** 约 5‑10 分钟
- **需要许可证吗？** 生产环境需要临时许可证；提供免费试用版
- **可以压缩多个文件吗？** 可以——向 Tar 归档中添加任意数量的条目
- **兼容 .NET 6+ 吗？** 完全兼容，Aspose.Zip 支持 .NET Framework 与 .NET Core/5/6

## 什么是 “add files to tar”？
将文件添加到 **tar**（Tape Archive）会创建一个未压缩的单一容器，保留目录结构和文件元数据。当随后使用 Bzip2 压缩时，得到的就是 **tar.bz2**（TarBz2）归档——非常适合高效存储和传输。

## 为什么使用 Aspose.Zip 将文件压缩为 TarBz2？
- **速度与简洁** – 一行 API 调用即可完成 tar 创建和 Bzip2 压缩。
- **跨平台** – 在 Windows、Linux 和 macOS 的 .NET 运行时上均可运行。
- **细粒度控制** – 选择要包含的文件、设置自定义条目名称，并直接流式写入磁盘。

## 前置条件

- **Aspose.Zip for .NET** – 从官方站点下载最新包：[https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **文档目录** – 包含待归档文件的文件夹。在示例中我们使用变量 `dataDir` 来引用它。

> **专业提示：** 将源文件放在专用文件夹中，以避免意外包含不需要的文件。

## 导入命名空间

首先，导入所需的命名空间，以便访问 Aspose.Zip 的 Tar 和 Bzip2 类。

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

> 将 `"Your Document Directory"` 替换为指向源文件夹的绝对或相对路径。

## 步骤 2：将文件添加到 tar 并创建 TarBz2 归档

核心流程是创建 `TarArchive`，添加条目，然后使用 `Bzip2Archive` 包装它。下面的代码演示了 **如何以简洁的 disposable‑pattern 方式创建 tarbz2**。

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

- `CreateEntry` 将每个文件添加到 **tar** 容器。  
- `bz2.SetSource(archive)` 告诉 Bzip2 归档压缩整个 tar 流。  
- `bz2.Save(...)` 将最终的 **tar.bz2** 文件写入磁盘。

**提示：** 若要 **批量压缩文件为 tarbz2**，只需对每个文件重复调用 `archive.CreateEntry` 即可。

## 常见问题与解决方案

| 问题 | 原因 | 解决办法 |
|-------|--------|-----|
| **File not found** 错误 | `dataDir` 路径错误或缺少文件扩展名 | 核实完整路径并确保文件存在。 |
| **Empty archive** | 在 `bz2.Save` 之前未添加任何条目 | 至少调用一次 `CreateEntry`。 |
| **Permission denied** | 应用程序对输出文件夹没有写入权限 | 以适当权限运行应用或选择可写目录。 |

## 常见问答

**Q: Aspose.Zip 是否兼容所有 .NET 应用？**  
A: 是的。它兼容 .NET Framework、.NET Core、.NET 5/6 以及更高版本的运行时。

**Q: 能否一次性压缩多个文件？**  
A: 完全可以。在保存归档前，对每个文件调用 `CreateEntry` 即可。

**Q: 在哪里可以找到更多文档？**  
A: 详细文档请访问 [here](https://reference.aspose.com/zip/net/)。

**Q: 如何获取 Aspose.Zip 的临时许可证？**  
A: 您可以在 [here](https://purchase.aspose.com/temporary-license/) 申请。

**Q: 是否提供免费试用？**  
A: 提供，您可以在 [here](https://releases.aspose.com/) 下载试用版。

## 结论

现在，您已经学会了如何 **将文件添加到 tar**，再通过 Bzip2 流包装，使用 Aspose.Zip for .NET 生成 **TarBz2** 归档。这一技术快速、可靠，适用于所有现代 .NET 平台。欢迎尝试更大的文件集合、自定义条目名称，或将代码集成到您自己的备份或部署流水线中。

如果遇到任何问题，Aspose.Zip 社区随时提供帮助——只需前往 [Aspose.Zip 支持论坛](https://forum.aspose.com/c/zip/37)。

---

**最后更新：** 2025-11-29  
**测试环境：** Aspose.Zip for .NET（最新发布）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}