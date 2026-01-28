---
date: 2026-01-28
description: 了解如何使用 Aspose.Zip for .NET 创建 tar.gz 存档、向 tar 添加文件并进行压缩——一种快速、可靠的文件归档方式。
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 创建 tar.gz 压缩包并向 tar 添加文件
url: /zh/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 将文件添加到 tar 并创建 TarGz

## 简介

在现代 .NET 应用程序中，快速且可靠地 **add files to tar** 是常见需求——无论是打包日志、为云存储准备数据，还是构建部署包。Aspose.Zip for .NET 为您提供简洁、高性能的 API 来 **add files to tar**，随后将归档压缩为广泛使用的 **tar.gz** 格式。在本教程中，您将学习如何从零开始一步步 **create tar.gz archive**，使用 Aspose.Zip .NET 库。

## 快速答复
- **应该使用哪个库？** Aspose.Zip for .NET  
- **如何将文件添加到 tar？** Use `TarArchive.CreateEntry` for each file.  
- **可以直接压缩为 tar.gz 吗？** Yes—call `SaveGzipped`.  
- **生产环境需要许可证吗？** A valid Aspose license is required for non‑trial use.  
- **支持的 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 什么是 “add files to tar”？

将文件添加到 tar 归档意味着将多个文件打包到一个未压缩的容器中。tar 格式保留目录结构和文件元数据，非常适合在可选压缩（例如 gzip）之前进行归档，以 **create tar.gz archive**。

## 为什么使用 Aspose.Zip 将文件压缩为 tar.gz？

- **无需外部工具** – 一切在您的 .NET 代码中运行。  
- **高性能** – 基于流的 API 高效处理大文件。  
- **跨平台** – 在 Windows、Linux 和 macOS 上均可运行。  
- **功能丰富** – 支持加密、密码保护和自定义条目属性。  

## 先决条件

在开始之前，请确保您拥有：

- 基本的 .NET 开发经验。  
- Visual Studio（或任何您偏好的 IDE）。  
- 已安装 Aspose.Zip for .NET – 请参阅官方文档 [here](https://reference.aspose.com/zip/net/)。  
- 从 [this link](https://releases.aspose.com/zip/net/) 下载 Aspose.Zip 库。  

## 导入命名空间

在您的 .NET 项目中，导入提供 tar 相关类的命名空间：

```csharp
using System;
using Aspose.Zip.Tar;
```

## 如何使用 Aspose.Zip for .NET 创建 tar.gz 归档

### 步骤 1：设置文档目录

首先，将代码指向包含您想要归档的文件的文件夹。

```csharp
string dataDir = "Your Document Directory";
```

> **专业提示：** 构建路径时使用 `Path.Combine`，以避免平台特定的分隔符问题。

### 步骤 2：初始化 TarArchive

创建一个将保存条目的 `TarArchive` 实例。

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

### 步骤 3：添加文件 – “add files to tar” 的核心

在 `using` 块内部，添加您想要包含在归档中的每个文件。

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

每个 `CreateEntry` 调用接受 **entry name**（文件在 tar 中的显示名称）和磁盘上的 **source file path**。

### 步骤 4：保存为 Gzipped Tar（如何将文件压缩为 tar.gz）

最后，将 tar 内容写入 gzip 流，以生成紧凑的 `archive.tar.gz`。

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` 在一次流畅的调用中同时处理 tar 打包和 gzip 压缩。

## 常见使用场景

| 场景 | 为什么 “add files to tar” 有帮助 |
|----------|------------------------------|
| **日志聚合** | 在上传到云存储之前，将每日日志打包成单个归档。 |
| **部署包** | 从 Windows 构建流水线为 Linux 服务器创建可移植的 tar.gz 包。 |
| **数据备份** | 在保持备份体积小的同时，保留文件夹层次结构和元数据。 |

## 常见问题及解决方案

- **文件未找到错误** – 确保 `dataDir` 以适当的路径分隔符结尾，或使用 `Path.Combine`。  
- **大文件导致内存压力** – 使用基于流的重载（`CreateEntry` 搭配 `Stream`）以避免将整个文件加载到内存中。  
- **Gzip 输出损坏** – 在调用 `SaveGzipped` 前确认归档已关闭（`using` 块）。  

## 常见问题

**Q: Aspose.Zip for .NET 是否兼容所有 .NET 应用程序？**  
A: 是的，它适用于 .NET Framework、.NET Core 和 .NET 5/6/7 项目。

**Q: 如何获取 Aspose.Zip for .NET 的临时许可证？**  
A: 访问 [temporary‑license page](https://purchase.aspose.com/temporary-license/) 以请求试用许可证。

**Q: 是否存在文件大小限制？**  
A: 该库针对大文件进行了优化；除系统可用内存外，没有硬性大小限制。

**Q: 我可以在哪里获得支持？**  
A: 使用社区驱动的支持论坛 [here](https://forum.aspose.com/c/zip/37) 获取 Aspose 工程师和其他开发者的帮助。

**Q: 我可以免费试用 Aspose.Zip for .NET 吗？**  
A: 当然可以——从 [Aspose Zip releases page](https://releases.aspose.com/zip/net) 下载免费试用版。

## 结论

您现在已经学习了 **how to add files to tar**，创建 tar 归档并使用 Aspose.Zip for .NET 将其压缩为 **tar.gz**。此方法消除了外部依赖，为您提供对归档内容的细粒度控制，并能够扩展到大规模数据集。欢迎探索 Aspose.Zip 的其他功能，如加密、自定义条目属性和流式 API，以进一步提升归档工作流。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-28  
**测试环境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose