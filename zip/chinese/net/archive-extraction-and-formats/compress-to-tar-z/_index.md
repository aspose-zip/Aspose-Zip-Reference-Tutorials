---
date: 2025-11-29
description: 学习如何使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarZ——一步步指南，帮助实现高效的 .NET 文件处理。
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarZ
url: /zh/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将文件添加到 tar 并压缩为 TarZ 使用 Aspose.Zip for .NET

## 介绍

如果您需要 **add files to tar** 并随后将归档压缩为 TarZ 格式，Aspose.Zip for .NET 能让整个过程轻松无忧。在本教程中，我们将逐步演示从项目设置、创建 tar 归档、添加文件，到最终保存为压缩的 .tar.z 文件。完成后，您将拥有一个可在任何 .NET 应用程序中直接使用的可复用代码片段。

## 快速回答
- **处理 tar 创建的库是什么？** Aspose.Zip for .NET  
- **代码行数是多少？** 大约 15 行（不包括注释）  
- **测试是否需要许可证？** 有免费试用版；生产环境需要许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+  
- **我可以压缩文件夹而不仅仅是文件吗？** 可以——可以使用循环添加整个目录。

## 什么是 **add files to tar**？

将文件添加到 tar 存档会将它们打包成一个单一的未压缩容器，保留目录结构和文件元数据。Tar 是一种经典的 Unix 格式，且是许多压缩工作流的基础，包括本指南中使用的 TarZ 格式。

## 为什么在压缩为 TarZ 之前先将文件添加到 tar？

- **可移植性** – tar 存档可跨平台使用，无需担心单个文件的处理。  
- **速度** – 创建 tar 容器速度快；随后进行的 Z‑压缩仅专注于减小体积。  
- **兼容性** – 许多旧工具在进行 gzip‑式压缩前需要先有 `.tar`，这正是 `.tar.z` 所提供的。

## 先决条件

在深入代码之前，请确保您已拥有：

- **Aspose.Zip for .NET** 已安装。请从官方网站 [here](https://releases.aspose.com/zip/net/) 下载。  
- 机器上包含要归档文件的文件夹。将占位路径替换为实际目录。

## 导入命名空间

在 C# 文件顶部添加所需的 `using` 语句：

```csharp
using System;
using Aspose.Zip.Tar;
```

## 分步指南

### 步骤 1：定义文档目录

```csharp
string dataDir = "Your Document Directory";
```

> **技巧提示：** 如果需要动态构建路径，请使用 `Path.Combine`；它可以避免不同操作系统上路径分隔符缺失的问题。

### 步骤 2：创建 Tar 存档并添加文件

#### 2.1：创建 Tar 存档实例

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2：向存档添加文件  

在 `using` 块内部，添加您想要包含的每个文件：

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

您可以根据需要多次调用 `CreateEntry`，或通过遍历目录以编程方式添加文件。

#### 2.3：保存压缩的 TarZ 文件  

添加完所有条目后，将 tar 存档压缩为 `.tar.z` 格式：

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

生成的 `archive.tar.z` 文件将位于您在 `dataDir` 中指定的同一文件夹中。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **未找到文件** | 路径错误或缺少文件扩展名 | 确认 `dataDir` 以路径分隔符结尾且文件名正确。 |
| **访问被拒绝** | 目标文件夹权限不足 | 以适当权限运行应用程序或选择可写目录。 |
| **压缩文件大于预期** | 原始文件已压缩（如图片、视频） | TarZ 最适用于文本或日志文件；考虑保持已压缩文件不变。 |

## 常见问题

**问：我可以使用 Aspose.Zip for .NET 压缩整个文件夹吗？**  
**答：** 当然可以。使用 `Directory.GetFiles` 循环并对每个文件调用 `CreateEntry`，保留相对路径。

**问：Aspose.Zip for .NET 有试用版吗？**  
**答：** 有，您可以通过下载免费试用版 [here](https://releases.aspose.com/) 来了解 Aspose.Zip for .NET 的功能。

**问：在哪里可以找到 Aspose.Zip for .NET 的完整文档？**  
**答：** 文档可在 [here](https://reference.aspose.com/zip/net/) 查看，提供库功能和使用的详细信息。

**问：如何获取 Aspose.Zip for .NET 的支持？**  
**答：** 请访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 寻求帮助，分享经验并与社区交流。

**问：我可以获取 Aspose.Zip for .NET 的临时许可证吗？**  
**答：** 可以，如果需要临时许可证，请在 [here](https://purchase.aspose.com/temporary-license/) 获取。

## 结论

您现在已经学习了如何 **add files to tar** 并使用 Aspose.Zip for .NET 将结果压缩为 TarZ 存档。此方法为您提供了一个干净、可移植的包，便于传输、存储或进一步处理。欢迎将此代码片段用于批量处理目录、集成到构建流水线，或与其他 Aspose 组件结合，实现更丰富的文档工作流。

---

**最后更新：** 2025-11-29  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}