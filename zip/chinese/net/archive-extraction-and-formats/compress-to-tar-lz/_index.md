---
date: 2025-12-01
description: 学习如何在 .NET 中使用 Aspose.Zip 压缩 tar.lz 文件，并轻松创建 tar.lz 存档。
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

在现代 .NET 开发中，高效地打包文件可以显著降低部署体积并加快网络传输速度。**如何压缩 tar.lz** 是在需要轻量级、LZ 压缩的 TAR 归档时的常见需求。在本教程中，我们将通过 Aspose.Zip 库一步步演示 **tar.lz 压缩示例**，帮助你快速在自己的应用程序中创建 tar.lz 归档。

## 快速答案
- **应该使用哪个库？** Aspose.Zip for .NET。
- **实现大概需要多长时间？** 基本示例约 5‑10 分钟。
- **需要许可证吗？** 免费试用可用于测试；生产环境需商业许可证。
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **可以一次压缩多个文件吗？** 可以——在保存之前只需添加更多条目。

## 什么是 tar.lz 压缩？
`tar.lz` 是使用 LZMA 算法（通常简称 **LZ**）压缩的 TAR 归档。它将 TAR 的文件分组简洁性与 LZ 的高压缩率相结合，非常适合备份文件、软件包分发或任何对带宽有要求的场景。

## 为什么使用 Aspose.Zip for .NET？
Aspose.Zip 将归档创建的底层细节抽象为简洁的面向对象 API。你将获得：

* **零外部依赖** – 纯 .NET 实现。  
* **跨平台支持** – 可在 Windows、Linux 和 macOS 上运行。  
* **内置 LZ 压缩** – 无需安装额外的本地工具。  
* **强大的错误处理** – 异常信息描述性强，便于调试。

## 前置条件
在开始之前，请确保你已经：

- **Aspose.Zip for .NET** 库 – 从 [here](https://releases.aspose.com/zip/net/) 下载。  
- 一个包含待归档文件的文件夹。该文件夹的路径将存储在 `dataDir` 变量中（将在第 3 步设置）。

## 导入命名空间
添加所需的命名空间，以便编译器能够找到我们将使用的类。

```csharp
using System;
using Aspose.Zip.Tar;
```

## 如何创建 tar.lz 归档 – 步骤指南

### 步骤 1：压缩单个文件
第一个示例展示最基本的场景——将一个文件添加到 TAR 归档中，然后保存为 **tar.lz** 文件。

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
- `CreateEntry` 将位于 `dataDir` 下的文件 `alice29.txt` 添加进去。  
- `SaveLzipped` 将归档写入磁盘并应用 LZ 压缩，生成 `archive.tar.lz`。

### 步骤 2：在同一归档中压缩多个文件
通常需要将多个文件打包在一起。只需在保存之前为每个文件调用一次 `CreateEntry`。

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

- 代码遵循步骤 1 的相同模式，只是额外添加了第二个条目 (`lcet10.txt`)。  
- 你可以根据需要多次调用 `CreateEntry`；库会自动处理内部的 TAR 结构。

### 步骤 3：指定文档目录
将占位符替换为实际的源文件所在路径。该路径将在上述示例中使用。

```csharp
string dataDir = "Your Document Directory";
```

**说明**

- 将 `dataDir` 设置为完整的文件夹路径，例如 `@"C:\MyFiles\"`。  
- 将目录保存在变量中可以提升代码的可复用性和可维护性。

## 常见问题与故障排除
| 症状 | 可能原因 | 解决方案 |
|------|----------|----------|
| 运行示例时出现 `FileNotFoundException` | `dataDir` 指向不存在的文件夹或文件名拼写错误 | 检查路径和文件名；使用 `Path.Combine` 以确保安全。 |
| 输出文件为 **0 KB** | 在添加任何条目之前调用了 `archive.SaveLzipped` | 确保在调用 `SaveLzipped` 前至少执行一次 `CreateEntry`。 |
| 压缩速度慢 | 大文件使用默认缓冲区大小 | 如性能关键，可考虑分块处理文件或使用异步 I/O。 |

## 结论
现在你已经掌握了使用 Aspose.Zip for .NET **压缩 tar.lz** 文件的方法，无论是单个文档还是文件集合。此 **tar.lz 压缩示例** 展示了一种简洁、可用于生产环境的方式来创建轻量级归档，便于传输或存储。

## 常见问答

**问：** 是否可以使用 Aspose.Zip for .NET 压缩任意大小的文件？  
**答：** 可以，库能够处理小文件和超大文件；只需确保有足够的内存和磁盘空间用于临时的 TAR 结构。

**问：** 代码是否兼容最新的 Aspose.Zip 版本？  
**答：** 示例针对当前版本编写；请始终保持 NuGet 包为最新，以获取错误修复和新功能。

**问：** 有哪些授权注意事项？  
**答：** 生产环境需要商业许可证。详细授权信息请参阅 [Aspose 网站](https://purchase.aspose.com/buy)。

**问：** 可以在商业项目中使用吗？  
**答：** 完全可以——拥有有效许可证后，您可以在任何商业应用中嵌入该库。

**问：** 如果遇到问题，在哪里获取帮助？  
**答：** 访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区支持和官方帮助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-01  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose