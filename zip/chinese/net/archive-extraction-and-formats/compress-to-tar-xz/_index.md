---
date: 2025-12-05
description: 了解如何在 .NET 中创建 tarxz 存档以及如何使用 Aspose.Zip for .NET 压缩 tarxz 文件。请遵循本分步指南，实现高效的存储和传输。
language: zh
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 .NET 中使用 Aspose.Zip 创建 tarxz 压缩文件
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip 在 .NET 中创建 tarxz 存档

## 介绍

如果您需要 **创建 tarxz 存档 .net**，Aspose.Zip for .NET 能让整个过程简洁且可靠。无论是打包日志、配置文件，还是其他任何资产用于存储或传输，使用 TarXz 格式压缩都能在保持熟悉的 tar 结构的同时提供高压缩率。在本教程中，我们将逐步演示完整的操作步骤——配有代码片段——帮助您自信地在 .NET 应用程序中集成 tarxz 创建功能。

## 快速答疑
- **主要类是什么？** `TarArchive` 来自 `Aspose.Zip.Tar`
- **如何压缩 tarxz？** 在添加条目后使用 `SaveXzCompressed`
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6
- **需要许可证吗？** 是的，生产环境需要有效的 Aspose.Zip 许可证
- **典型实现时间？** 大约 5‑10 分钟

## 什么是 TarXz 存档？

**TarXz 存档** 将传统的 Unix `tar` 容器与 XZ 压缩相结合。tar 部分将多个文件打包成单一流，而 XZ 提供强大的无损压缩。该格式因能够保留目录结构且相较于普通 tar 或 zip 能实现更小的文件体积，广泛用于分发源代码、备份以及大型数据集。

## 为什么要使用 Aspose.Zip 在 .NET 中创建 tarxz 存档？

- **高压缩率** – XZ 通常比 gzip 小 30‑50 %。
- **跨平台兼容** – TarXz 文件可在 Linux、macOS 和 Windows 上打开。
- **简洁 API** – Aspose.Zip 抽象了底层细节，让您专注业务逻辑。
- **无需外部工具** – 所有操作均在 .NET 进程内完成，适合云环境或 CI 流水线。

## 前置条件

在开始之前，请确保您已具备：

- 已安装 **Aspose.Zip for .NET**（可从官方 [Aspose.Zip 文档](https://reference.aspose.com/zip/net/) 下载）。
- 包含待归档文件的文件夹。示例中该文件夹通过 `dataDir` 变量引用。
- 有效的 Aspose.Zip 许可证（评估版可选，生产环境必需）。

## 导入命名空间

首先，导入提供 TarXz 功能的命名空间。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 创建 tarxz 存档的分步指南

### 步骤 1：初始化 `TarArchive`

创建一个新的 `TarArchive` 实例，用于保存待压缩的文件。

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **小贴士：** `using` 语句可确保归档在使用完毕后正确释放，释放任何非托管资源。

### 步骤 2：向归档添加文件

将每个需要包含的文件加入归档。示例中添加了两个文本文件，您可以根据需要添加任意数量的条目。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **为什么重要：** 在压缩之前先添加条目，可让 Aspose.Zip 先构建 tar 容器，然后在一次操作中应用 XZ 压缩。

### 步骤 3：使用 XZ 压缩保存归档

最后，使用 XZ 压缩将 tar 归档写入磁盘。生成的文件扩展名为 `.tar.xz`。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **结果：** 您现在拥有一个完整压缩的 `archive.tar.xz` 文件，可在任何支持 TarXz 的平台上进行传输、存储或解压。

## 常见问题与解决方案

| 问题 | 原因 | 解决办法 |
|------|------|----------|
| **“File not found” 异常** | `dataDir` 路径不正确 | 确认目录路径以反斜杠 (`\`) 结尾，或使用 `Path.Combine`。 |
| **内存占用过大** | 大文件在内存中压缩 | 使用流模式的 `TarArchive`（接受 `Stream` 参数的 `SaveXzCompressed` 重载）。 |
| **许可证未生效** | 缺少许可证文件 | 在应用启动时加载许可证：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## 常见问答

**Q: Aspose.Zip 是否兼容所有 .NET 环境？**  
A: 是的，Aspose.Zip 支持 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。详细信息请参阅 [文档](https://reference.aspose.com/zip/net/)。

**Q: 如何获取 Aspose.Zip 的临时许可证？**  
A: 您可以在 [Aspose 临时许可证页面](https://purchase.aspose.com/temporary-license/) 申请临时许可证。

**Q: 是否有其他归档格式的示例？**  
A: 当然——请在 [Aspose.Zip API 参考](https://reference.aspose.com/zip/net/) 中查阅完整示例集。

**Q: 哪里可以获取帮助或讨论问题？**  
A: 加入 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 与社区和官方人员交流。

**Q: 在购买前可以免费试用 Aspose.Zip 吗？**  
A: 可以，免费试用版可在 [Aspose.Zip 下载页面](https://releases.aspose.com/zip/net) 获取。

## 结论

通过上述步骤，您已经掌握了 **如何压缩 tarxz** 文件，更重要的是，了解了如何使用 Aspose.Zip **在 .NET 中创建 tarxz 存档**。此方法能够生成紧凑、可移植的包，轻松集成到任何 .NET 工作流中——无论是桌面工具、Web 服务还是自动化 CI/CD 流水线。

---

**最后更新：** 2025-12-05  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}