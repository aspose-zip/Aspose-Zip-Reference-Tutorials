---
date: 2026-02-20
description: 学习如何使用 Aspose.Zip for .NET 创建 tar 存档、向 tar 添加文件并压缩为 tar.gz —— 一种快速、跨平台的构建
  TarGz 存档的方式。
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 创建 tar 存档并向 tar 添加文件
url: /zh/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

Make sure not to translate URLs.

Also keep markdown formatting.

Also note "Ensure proper RTL formatting if needed" but Chinese is LTR, ignore.

Now produce the translated content.

Let's translate:

Title: "Create tar archive and add files to tar with Aspose.Zip for .NET" => "使用 Aspose.Zip for .NET 创建 tar 存档并向 tar 添加文件"

Introduction: translate.

Will keep **text** formatting.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 创建 tar 存档并向 tar 添加文件

## 介绍

在现代 .NET 应用程序中，**创建 tar 存档** 和 **向 tar 添加文件** 快速且可靠是常见需求——无论是打包日志、为云存储准备数据，还是构建部署包。Aspose.Zip for .NET 为您提供简洁、高性能的 API 来 **向 tar 添加文件**，随后将存档压缩为广泛使用的 **tar.gz** 格式。在本指南中，我们将从项目设置到生成可直接发布的 `archive.tar.gz`，完整演示整个过程。

## 快速答疑
- **应该使用哪个库？** Aspose.Zip for .NET  
- **如何向 tar 添加文件？** 对每个文件使用 `TarArchive.CreateEntry`。  
- **可以直接压缩为 tar.gz 吗？** 可以——调用 `SaveGzipped`。  
- **生产环境需要许可证吗？** 非试用使用必须拥有有效的 Aspose 许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是 “向 tar 添加文件”？
向 tar 存档添加文件是指将多个文件打包到一个未压缩的容器中。tar 格式保留目录结构和文件元数据，非常适合作为后续可选压缩（例如 gzip）的归档方式，以 **创建 tar.gz 存档**。

## 为什么使用 Aspose.Zip 将文件压缩为 tar.gz？
- **无需外部工具** – 所有操作均在 .NET 代码内部完成。  
- **高性能** – 基于流的 API 能高效处理大文件。  
- **跨平台 tar** – 在 Windows、Linux、macOS 上均可无缝运行。  
- **功能丰富** – 支持加密、密码保护和自定义条目属性。

## 前置条件

在开始之前，请确保您具备：

- 基础的 .NET 开发经验。  
- Visual Studio（或任意您喜欢的 IDE）。  
- 已安装 Aspose.Zip for .NET – 请参阅官方文档 [here](https://reference.aspose.com/zip/net/)。  
- 从 [this link](https://releases.aspose.com/zip/net/) 下载的 Aspose.Zip 库。

## 导入命名空间

在 .NET 项目中，导入提供 tar 相关类的命名空间：

```csharp
using System;
using Aspose.Zip.Tar;
```

## 使用 Aspose.Zip for .NET 向 tar 添加文件的步骤

### 步骤 1：设置文档目录

首先，将代码指向包含待归档文件的文件夹。

```csharp
string dataDir = "Your Document Directory";
```

> **专业提示：** 构建路径时使用 `Path.Combine`，可避免平台特定的分隔符问题。

### 步骤 2：创建 TarGz 存档

接下来，我们将在一次流畅的调用链中创建 tar 存档、添加条目并进行压缩。

#### 2.1 初始化 TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 添加文件 – “向 tar 添加文件” 的核心

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

每次调用 `CreateEntry` 都需要提供 **条目名称**（文件在 tar 中的显示路径）和磁盘上的 **源文件路径**。您可以多次调用 `CreateEntry`，在同一个存档中 **添加多个文件到 tar**。

#### 2.3 保存为 Gzipped Tar（如何压缩为 tar.gz）

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` 将 tar 内容写入 gzip 流，生成紧凑的 `archive.tar.gz` 文件，可直接用于分发。

## 常见使用场景

| 场景 | “向 tar 添加文件” 的价值 |
|----------|------------------------------|
| **日志聚合** | 在上传至云存储前，将每日日志打包为单个存档。 |
| **部署包** | 从 Windows 构建流水线生成可在 Linux 服务器上使用的便携 tar.gz 包。 |
| **数据备份** | 保留文件夹层级和元数据，同时保持备份体积较小。 |

## 常见问题与解决方案

- **文件未找到错误** – 确保 `dataDir` 以正确的路径分隔符结尾，或使用 `Path.Combine`。  
- **大文件导致内存压力** – 使用基于流的重载（`CreateEntry` 搭配 `Stream`）以避免一次性加载整个文件。  
- **Gzip 输出损坏** – 在调用 `SaveGzipped` 前，确保已正确关闭存档（`using` 块）。

## 常见问答

**问：Aspose.Zip for .NET 是否兼容所有 .NET 应用程序？**  
答：是的，它可在 .NET Framework、.NET Core 以及 .NET 5/6/7 项目中使用。

**问：如何获取 Aspose.Zip for .NET 的临时许可证？**  
答：访问 [temporary‑license page](https://purchase.aspose.com/temporary-license/) 申请试用许可证。

**问：是否存在文件大小限制？**  
答：库已针对大文件进行优化，除系统可用内存外没有硬性大小限制。

**问：在哪里可以获得支持？**  
答：可在社区支持论坛 [here](https://forum.aspose.com/c/zip/37) 向 Aspose 工程师和其他开发者寻求帮助。

**问：可以免费试用 Aspose.Zip for .NET 吗？**  
答：当然可以——从 [Aspose Zip releases page](https://releases.aspose.com/zip/net) 下载免费试用版。

## 结论

您现在已经掌握了使用 Aspose.Zip for .NET **创建 tar 存档**、向其中 **添加文件** 并压缩为 **tar.gz** 的完整流程。这种方式消除了外部依赖，提供对存档内容的细粒度控制，并能够扩展至大规模数据集。欢迎进一步探索 Aspose.Zip 的其他功能，如加密、自定义条目属性以及流式 API，以进一步提升归档工作流。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-02-20  
**测试环境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose