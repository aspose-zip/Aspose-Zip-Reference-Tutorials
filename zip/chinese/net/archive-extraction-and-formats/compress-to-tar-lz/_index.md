---
date: 2026-02-02
description: 学习如何在 .NET 中使用 Aspose.Zip 压缩 tar.lz 文件——一步步轻松压缩 tar.lz 档案的指南。
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 压缩 tar.lz
url: /zh/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 压缩 tar.lz

在现代 .NET 开发中，高效地打包文件可以显著减小部署体积并加快网络传输时间。**如何压缩 tar.lz** 是在需要轻量级、LZ 压缩的 TAR 归档时的常见需求。在本教程中，我们将通过一个清晰的、逐步的 **tar.lz 压缩示例**，使用 Aspose.Zip 库，帮助您快速在自己的应用程序中创建 tar.lz 归档。

## 快速回答
- **应该使用哪个库？** Aspose.Zip for .NET。  
- **实现需要多长时间？** 基本示例大约 5‑10 分钟。  
- **我需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持哪些NET 5/6/7。  
- **。

## 什么是 tar.lz 压缩？
`tar.lz` 是使用 LZMA 算法（通常简称为 **LZ**）压缩的 TAR 归档。它将 TAR 的文件分组简洁性与 LZ 的高压缩比相结合，非常适合备份文件、软件包分发或任何对带宽有要求的场景。

## 为什么使用 Aspose.Zip for .NET？
Aspose.Zip 抽象了归档创建的底层细节，提供简洁的面向对象 API。您将获得：

* **零外部依赖** – 纯 .NET 实现。  
* **跨平台支持** – 在 Windows、Linux 和 macOS 上均可运行。  
* **内置 LZ 压缩** – 无需安装额外的本地工具。  
* **强大的错误处理** – 异常信息描述性强，便于调试。

## 前置条件
在开始之前，请确保您已拥有：

- **Aspose.Zip for .NET** 库 – 从 [此处](https://releases.aspose.com/zip/net/) 下载。  
- 包含待归档文件的文件夹。该文件夹的路径将存储在 `dataDir` 变量中（将在第 3 步中设置）。

## 导入命名空间
添加所需的命名空间，以便编译器知道我们将使用的类所在位置。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 使用 Aspose.Zip 压缩 tar.lz – 步骤指南

### 步骤 1：创建 tar.lz 归档 – 压缩单个文件
第一个示例展示了最基本的场景——将一个文件添加到 TAR 归档中，然后保存为 **tar.lz** 文件。

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**说明**

- `new TarArchive()` 创建一个空的 TAR 容器。  
- `CreateEntry` 从您的 `dataDir` 添加文件 `alice29.txt`。  
- `SaveLzipped` 将归档写入磁盘并应用 LZ 压缩，生成 `archive.tar.lz`。

### 步骤 2：压缩多个文件 tar.lz – 添加多个条目
通常您需要将多个文件打包在一起。只需在保存之前为每个文件调用 `CreateEntry`。

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**说明**

- 代码遵循与步骤 1 相同的模式，但添加了第二个条目 (`lcet10.txt`)。  
- 您可以根据需要多次调用 `CreateEntry`；库会自动处理内部的 TAR 结构。

### 步骤 3：指定文档目录 – 创建 tar.lz 归档的生成路径
将占位符替换为实际的源文件所在路径。上述示例会使用此路径。

```csharp
string dataDir = "Your Document Directory";
```

**说明**

- 将 `dataDir` 设置为完整的文件夹路径，例如 `@"C:\MyFiles\"`。  
- 将目录保存在变量中可以使代码更易复用和维护。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| `FileNotFoundException` 在运行示例时出现 | `dataDir` 指向不存在的文件夹或文件名拼写错误 | 检查路径和文件名；为安全起见使用 `Path.Combine`。 |
| 输出文件为 **0 KB** | `archive.SaveLzipped` 在添加任何条目之前被调用 | 确保在 `SaveLzipped` 之前至少调用一次 `CreateEntry`。 |
| 压缩速度慢 | 使用默认缓冲区大小处理大文件 | 如果性能关键，可考虑分块处理文件或使用异步 I/O。 |

## 常见问答

**Q:** 我可以使用 Aspose.Zip for .NET 压缩任意大小的文件吗？  
**A:** 可以，库能够处理小文件和非常够的内存和磁盘空间用于临时的 TAR 结构。

**Q:** 该代码兼容最新的 Aspose.Zip 版本吗？  
**A:** 示例针对当前版本；请始终保持 NuGet 包为最新，以获取错误修复和新功能。

**Q:** 是否有许可方面的考虑？  
**A:** 生产环境需要商业许可证。请参阅 [Aspose 网站](https://purchase.aspose.com/buy) 上的许可详情。

**QA:** 入该 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区支持和官方帮助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-02-02  
**测试环境：** Aspose.Zip for .NET（最新版本）  
**作者：** Aspose