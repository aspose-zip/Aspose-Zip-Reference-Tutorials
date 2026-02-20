---
date: 2026-02-15
description: 学习如何使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarZ——一步一步的高效 .NET 文件处理指南。
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 将文件添加到 tar 并压缩为 TarZ
url: /zh/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将文件添加到 tar 并使用 Aspose.Zip for .NET 压缩为 TarZ

## 介绍

如果您需要**将文件添加到 tar**，然后将归档压缩为 TarZ 格式，Aspose.Zip for .NET 可以让整个过程变得轻而易举。在本教程中，我们将逐步演示每一步——从设置项目、创建 tar 归档、添加文件，到最终保存为压缩的 .tar.z 文件。完成后，您将拥有一个可在任何 .NET 应用程序中直接使用的可复用代码片段。

## 快速答复
- **处理 tar 创建的库是什么？** Aspose.Zip for .NET  
- **代码行数是多少？** 大约 15 行（不包括注释）  
- **测试是否需要许可证？** 有免费试用版；生产环境需要许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+  
- **我可以压缩文件夹，而不仅仅是文件吗？** 可以——您可以使用循环添加整个目录。

## 什么是 **将文件添加到 tar**？

将文件添加到 tar 归档会将它们打包成一个单一的、未压缩的容器，并保留目录结构和文件元数据。Tar 是一种经典的 Unix 格式，且是许多压缩工作流的基础，包括本指南中使用的 TarZ 格式。

## 为什么在压缩为 TarZ 之前先将文件添加到 tar？

- **可移植性** – tar 归档可跨平台使用，无需担心单个文件的处理。  
- **速度** – 创建 tar 容器速度快；随后进行的 Z‑压缩仅专注于减小体积。  
- **兼容性** – 许多旧工具在进行 gzip‑式压缩前需要先有 `.tar`，这正是 `.tar.z` 所提供的。  

### 这对 .NET 开发者为何重要

使用 tar 容器可以让您的 .NET 代码保持简洁且可预测。您可以在内存中生成归档，直接流式传输到响应，或存储到磁盘，而无需处理临时 zip 文件。这种模式特别适用于构建流水线、日志聚合，或需要将一组配置文件发送到基于 Linux 的服务的场景。

## 先决条件

在深入代码之前，请确保您已经：

- 已安装 **Aspose.Zip for .NET**。请从官方站点[此处](https://releases.aspose.com/zip/net/)下载。  
- 在机器上有一个文件夹，里面包含您想要归档的文件。请将占位符路径替换为实际目录。

## 导入命名空间

在 C# 文件的顶部添加所需的 `using` 语句：

```csharp
using System;
using Aspose.Zip.Tar;
```

> **专业提示：** 如果需要动态构建路径，请使用 `Path.Combine`；它可以避免在不同操作系统上缺少路径分隔符。

## 分步指南

### 步骤 1：定义文档目录

```csharp
string dataDir = "Your Document Directory";
```

> **此步骤重要原因：** `dataDir` 充当您将要添加的每个文件的基础位置。将其保存在单一变量中，使代码易于维护并可在多个归档之间复用。

### 步骤 2：创建 Tar 归档并添加文件

#### 2.1：创建 Tar 归档实例

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> `using` 块确保 `TarArchive` 对象得到正确释放，释放任何文件句柄或内存缓冲区。

#### 2.2：向归档添加文件  

在 `using` 块内部，添加您想要包含的每个文件：

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

您可以根据需要多次调用 `CreateEntry`，或通过循环遍历目录以编程方式添加文件。例如，使用 `foreach (var file in Directory.GetFiles(dataDir))` 循环可以在保留相对路径的同时处理任意数量的文件。

#### 2.3：保存压缩的 TarZ 文件  

添加完所有条目后，将 tar 归档压缩为 `.tar.z` 格式：

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

生成的 `archive.tar.z` 文件将位于您在 `dataDir` 中指定的同一文件夹中。现在，您可以将这个单一的压缩包发送到任何支持 TarZ 的系统。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **未找到文件** | 路径错误或缺少文件扩展名 | 验证 `dataDir` 以路径分隔符结尾且文件名正确。 |
| **访问被拒绝** | 目标文件夹权限不足 | 以适当权限运行应用程序或选择可写目录。 |
| **压缩文件大于预期** | 原始文件已压缩（例如图片、视频） | TarZ 最适用于文本或日志文件；考虑保持已压缩文件不变。 |

### 常见陷阱需注意
- **缺少结尾斜杠** – 如果 `dataDir` 未以 `\` 或 `/` 结尾，字符串拼接将产生无效路径。  
- **大型目录** – 添加成千上万的文件可能会消耗大量内存；考虑流式写入条目或使用直接写入文件流的 `TarArchive` 重载。  
- **编码问题** – 非 ASCII 文件名可能需要显式的编码处理；Aspose.Zip 默认支持 UTF‑8，但请在目标平台上进行验证。  

## 常见问答

**问：我可以使用 Aspose.Zip for .NET 压缩整个文件夹吗？**  
**答：** 当然可以。使用 `Directory.GetFiles` 循环并对每个文件调用 `CreateEntry`，保留相对路径。

**问：Aspose.Zip for .NET 有试用版吗？**  
**答：** 有，您可以通过下载免费试用版[此处](https://releases.aspose.com/)来体验 Aspose.Zip for .NET 的功能。

**问：在哪里可以找到 Aspose.Zip for .NET 的完整文档？**  
**答：** 文档可在[此处](https://reference.aspose.com/zip/net/)获取，提供关于库功能和使用的详细信息。

**问：如何获取 Aspose.Zip for .NET 的支持？**  
**答：** 请访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 寻求帮助，分享经验，并与社区交流。

**问：我可以获取 Aspose.Zip for .NET 的临时许可证吗？**  
**答：** 可以，如果您需要临时许可证，可在[此处](https://purchase.aspose.com/temporary-license/)获取。

## 结论

您现在已经学习了如何使用 Aspose.Zip for .NET **将文件添加到 tar** 并将结果压缩为 TarZ 归档。这种方法为您提供了一个干净、可移植的包，便于传输、存储或进一步处理。欢迎将此代码片段用于批量处理目录、集成到构建流水线，或与其他 Aspose 组件结合，实现更丰富的文档工作流。

---

**最后更新：** 2026-02-15  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}