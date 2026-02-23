---
date: 2026-02-23
description: 了解如何使用 Aspose.Zip 在 .NET 中将文件添加到 tar 并压缩为 tarxz 档案。请遵循此分步指南，实现高效的存储和传输。
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 归档
url: /zh/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将文件添加到 tar 并使用 Aspose.Zip 创建 tarxz 存档

## Introduction

如果您需要 **将文件添加到 tar**，然后 **在 .net 中创建 tarxz 存档**，Aspose.Zip for .NET 使过程简洁可靠。无论是打包日志、配置文件，还是其他任何资产用于存储或传输，压缩为 TarXz 格式可在保持熟悉的 tar 结构的同时提供高压缩率。在本教程中，我们将逐步演示完整的步骤——包括代码片段——让您能够自信地在 .NET 应用程序中集成 tarxz 创建。

## Quick Answers
- **主要类是什么？** `TarArchive` from `Aspose.Zip.Tar`
- **如何压缩 tarxz？** Use `SaveXzCompressed` after adding entries
- **支持的 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **需要许可证吗？** Yes, a valid Aspose.Zip license for production
- **典型实现时间？** ~5‑10 minutes

## What is a TarXz archive?

**TarXz archive** 将传统的 Unix `tar` 容器与 XZ 压缩相结合。tar 部分将多个文件打包成单一流，而 XZ 提供强大的无损压缩。该格式因能够保留目录结构且相较于普通 tar 或 zip 能实现更小的文件体积，而在分发源代码、备份和大数据集时广受欢迎。

## Why create tarxz archive .net with Aspose.Zip?

- **高压缩比** – XZ 通常比 gzip 小 30‑50 %。
- **跨平台兼容性** – TarXz 文件可在 Linux、macOS 和 Windows 上打开。
- **简洁的 API** – Aspose.Zip 抽象了底层细节，让您专注于业务逻辑。
- **无需外部工具** – 所有操作都在 .NET 进程内部运行，适合云或 CI 流水线。

## Prerequisites

在开始之前，请确保您已拥有：

- **Aspose.Zip for .NET** installed (download from the official [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- 包含您想要归档文件的文件夹。在下面的示例中，该文件夹通过 `dataDir` 变量引用。  
- 有效的 Aspose.Zip 许可证（评估可选，生产必需）。

## Import Namespaces

首先，导入提供 TarXz 功能的命名空间。

```csharp
using System;
using Aspose.Zip.Tar;
```

## How to add files to tar using Aspose.Zip

下面是逐步指南，展示如何在压缩之前 **将文件添加到 tar**。

### Step 1: Initialize a `TarArchive`

创建一个新的 `TarArchive` 实例，用于保存您想要压缩的文件。

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **提示：** `using` 语句确保归档正确释放，释放任何非托管资源。

### Step 2: Add Files to the Archive

将每个想要包含的文件添加进去。在本例中我们添加了两个文本文件，但您可以根据需要添加任意数量的条目。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **为什么重要：** 在压缩之前添加条目，使 Aspose.Zip 先构建 tar 容器，然后在一次操作中应用 XZ 压缩。

### Step 3: Save the Archive with XZ Compression

最后，使用 XZ 压缩将 tar 归档写入磁盘。生成的文件将具有 `.tar.xz` 扩展名。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **结果：** 您现在拥有一个完整压缩的 `archive.tar.xz` 文件，可在任何支持 TarXz 的平台上进行传输、存储或解压。

## How to compress tarxz files with Aspose.Zip

上述过程本质上就是 **如何压缩 tarxz** 文件：您首先将文件添加到 tar 容器（`add files to tar`），然后调用 `SaveXzCompressed`。这种单调用方式消除了对外部命令行工具的需求，并将所有操作保留在 .NET 代码库中。

## Common Issues & Solutions

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **“File not found” 异常** | `dataDir` 路径不正确 | 确认目录路径以反斜杠 (`\`) 结尾，或使用 `Path.Combine`。 |
| **内存占用大** | 在内存中压缩的文件非常大 | 在流模式下使用 `TarArchive`（接受 `Stream` 的 `SaveXzCompressed` 重载）。 |
| **许可证未应用** | 缺少许可证文件 | 在应用程序启动时加载许可证：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Frequently Asked Questions

**Q: Aspose.Zip 是否兼容所有 .NET 环境？**  
A: 是的，Aspose.Zip 支持 .NET Framework 4.5+、.NET Core 3.1+ 和 .NET 5/6+。详情请参阅 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 如何获取 Aspose.Zip 的临时许可证？**  
A: 您可以从 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 请求临时许可证。

**Q: 是否有其他归档格式的示例？**  
A: 当然——请在 [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) 中查看完整示例集。

**Q: 在哪里可以获取帮助或讨论问题？**  
A: 加入 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 的讨论，获取社区支持和官方答复。

**Q: 在购买前我可以免费试用 Aspose.Zip 吗？**  
A: 可以，免费试用可在 [Aspose.Zip download page](https://releases.aspose.com/zip/net) 获取。

## Conclusion

通过遵循上述步骤，您现在了解了 **如何将文件添加到 tar** 和 **压缩 tarxz** 文件，更重要的是，了解了如何使用 Aspose.Zip **在 .net 中创建 tarxz 存档**。这种方法为您提供了一个紧凑、可移植的包，可无缝集成到任何 .NET 工作流中——无论是构建桌面工具、Web 服务，还是自动化 CI/CD 流水线。

---

**最后更新：** 2026-02-23  
**测试版本：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}