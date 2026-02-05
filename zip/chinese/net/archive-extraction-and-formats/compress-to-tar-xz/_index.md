---
date: 2026-02-05
description: 学习如何在 .NET 中使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 压缩包。本指南展示了如何高效地将文件压缩为
  tarxz。
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 在 .NET 中使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 归档
url: /zh/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何将文件添加到 tar，使用 Aspise.Zip 在 .NET 中创建 tarxz 压缩包

## 介绍

如果您需要 **add files to tar**，然后使用 .NET 将其压缩为 tarxz 归档，Aspose.Zip for .NET 能让整个过程简洁且可靠。无论是打包日志、配置文件，还是其他任何用于存储或传输的资产，使用 TarXz 格式压缩都能在保持熟悉的 tar 结构的同时实现高压缩率。在本教程中，我们将逐步演示完整的操作步骤——包括代码片段——帮助您自信地在 .NET 应用程序中集成 tarxz 创建。

## 快速答案
- **What is the primary class?** `TarArchive` from `Aspose.Zip.Tar`
- **How to compress tarxz?** Use `SaveXzCompressed` after adding entries
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **License needed?** Yes, a valid Aspose.Zip license for production
- **Typical implementation time?** ~5‑10 minutes

## 什么是 TarXz 压缩包？

**TarXz 压缩包** 将传统的 Unix `tar` 容器与 XZ 压缩相结合。tar 部分将多个文件打包成单一流，而 XZ 提供强大的无损压缩。该格式因能够保留目录结构且比普通 tar 或 zip 获得更小的文件体积，广泛用于分发源代码、备份以及大型数据集。

## 为什么使用 Aspose.Zip 将文件添加到 tar 并压缩为 tarxz？

- **高压缩比** – XZ 通常比 gzip 小 30‑50 %。  
- **跨平台兼容** – TarXz 文件可在 Linux、macOS 和 Windows 上打开。  
- **简洁 API** – Aspose.Zip 抽象了底层细节，让您专注业务逻辑。  
- **无需外部工具** – 所有操作均在 .NET 进程内完成，适合云端或 CI 流水线。  

## 先决条件

在开始之前，请确保您已具备：

- **Aspose.Zip for .NET** 已安装（可从官方 [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) 下载）。  
- 包含待归档文件的文件夹。下面示例中，该文件夹通过 `dataDir` 变量引用。  
- 有效的 Aspose.Zip 许可证（评估可选，生产环境必需）。

## 导入命名空间

首先，导入提供 TarXz 功能的命名空间。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 如何使用 Aspose.Zip 将文件添加到 tar

### 步骤 1：初始化 `TarArchive`

创建一个新的 `TarArchive` 实例，用于保存您想压缩的文件。

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **专业提示：** `using` 语句确保归档正确释放，释放任何非托管资源。

### 步骤 2：将文件添加到归档

将每个需要包含的文件加入。示例中我们添加了两个文本文件，您可以根据需要添加任意数量的条目。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **重要原因：** 在压缩之前添加条目，使 Aspose.Zip 先构建 tar 容器，然后在一次步骤中应用 XZ 压缩。

### 步骤 3：使用 XZ 压缩保存归档

最后，使用 XZ 压缩将 tar 归档写入磁盘。生成的文件将拥有 `.tar.xz` 扩展名。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **结果：** 您现在拥有一个完整压缩的 `archive.tar.xz` 文件，可在任何支持 TarXz 的平台上进行传输、存储或解压。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **“File not found” 异常** | `dataDir` 路径不正确 | 确认目录路径以反斜杠 (`\`) 结尾，或使用 `Path.Combine`。 |
| **Large memory usage** | 大文件在内存中压缩 | 使用流模式的 `TarArchive`（接受 `Stream` 的 `SaveXzCompressed` 重载）。 |
| **License not applied** | 缺少许可证文件 | 在应用启动时加载许可证：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## 常见问题解答

**Q: Aspose.Zip 是否兼容所有 .NET 环境？**  
A: 是的，Aspose.Zip 支持 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。详情请参阅 [documentation](https://reference.aspose.com/zip/net/)。

**Q: 如何获取 Aspose.Zip 的临时许可证？**  
A: 您可以在 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 申请临时许可证。

**Q: 是否有其他归档格式的示例？**  
A: 当然——请在 [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) 中查看完整示例集。

**Q: 哪里可以获取帮助或讨论问题？**  
A: 加入 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 与社区和官方人员交流。

**Q: 在购买前可以免费试用 Aspose.Zip 吗？**  
A: 可以，免费试用请前往 [Aspose.Zip download page](https://releases.aspose.com/zip/net)。

## 结论

通过上述步骤，您已经掌握了 **如何将文件添加到 tar** 并使用 Aspose.Zip 在 .NET 中 **创建 tarxz 归档**。这种方法能够生成紧凑、可移植的包，可无缝集成到任何 .NET 工作流中——无论是桌面工具、Web 服务，还是自动化 CI/CD 流水线。

---

**最后更新：** 2026-02-05  
**已测试：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}