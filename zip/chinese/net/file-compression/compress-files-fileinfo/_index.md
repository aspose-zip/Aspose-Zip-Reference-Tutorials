---
date: 2026-02-28
description: 了解如何使用 Aspose.Zip for .NET 将文件夹添加到 zip 并将文件添加到 zip。本分步指南展示了如何在 ASP.NET
  项目中使用 FileInfo 压缩文件。
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 将文件夹添加到 Zip – 使用 FileInfo 压缩文件
url: /zh/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 将文件夹添加到 Zip

## 介绍

如果您需要以编程方式 **创建 zip 存档**，Aspose.Zip for .NET 为您提供了一个简洁、高性能的 API，能够在任何 .NET（包括 ASP.NET）应用程序中运行。在本教程中，我们将演示如何使用 `FileInfo` 类压缩文件，向您展示 **如何将文件添加到 zip**，并解释为何这种方法非常适合现代 .NET 项目。我们还会介绍 **如何将文件夹添加到 zip**，让您一次性打包整个目录。让我们开始吧！

## 快速答案
- **创建 zip 存档的最简方法是什么？** 使用 Aspose.Zip 的 `Archive` 类结合 `FileInfo` 对象。  
- **可以一次添加多个文件吗？** 可以——只需为每个文件创建一个 `FileInfo` 并调用 `CreateEntry`。  
- **ASP.NET 需要特殊许可证吗？** 生产环境需要商业 Aspose.Zip 许可证；免费试用可用于评估。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **API 是线程安全的吗？** 是的，只要每个线程使用各自的 `Archive` 实例。

## 什么是 Zip 存档以及为何要创建它？
Zip 存档将一个或多个文件打包成单个压缩容器。这可以减少存储空间、加快网络传输速度，并简化分发。无论是交付日志、导出报告，还是为客户打包资源，掌握 **如何以编程方式创建 zip 存档** 对任何 .NET 开发者都是一项宝贵技能。

## 为什么使用 Aspose.Zip 将文件添加到 Zip？
- **零外部依赖** —— 纯 .NET 实现。  
- **可完全控制压缩级别和编码**（ASCII、UTF‑8 等）。  
- **支持大文件**（> 4 GB）和密码保护。  
- **在 .NET Framework、.NET Core 和 .NET 5+ 上保持一致的 API**。

## 前置条件

在开始编写代码之前，请确保您已具备：

1. 已安装 **Aspose.Zip for .NET**。从 [Aspose.Zip 下载页面](https://releases.aspose.com/zip/net/) 获取最新包。  
2. 本机上有一个文件夹，里面存放您想压缩的文件（例如 `alice29.txt` 和 `fields.c`）。  

## 导入命名空间

在任何需要处理 zip 存档的 C# 文件中，添加以下 `using` 语句：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

这些命名空间为您提供 `Archive` 类、保存选项以及标准 I/O 实用程序的访问权限。

## 步骤指南

### 步骤 1：设置文档目录

首先，定义保存源文件的文件夹。将占位符替换为系统中的绝对或相对路径：

```csharp
string dataDir = "Your Document Directory";
```

> **小贴士：** 使用 `Path.Combine` 以跨平台方式构建路径。

### 步骤 2：打开用于写入的 Zip 文件

创建指向输出 zip 文件的 `FileStream`。该流以 **Create** 模式打开，会覆盖同名的已有文件：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步骤 3：为每个源文件准备 `FileInfo` 对象

`FileInfo` 让 Aspose.Zip 直接访问磁盘上的物理文件。为每个需要压缩的文件创建一个实例：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **为何使用 `FileInfo`？** 它避免将整个文件加载到内存中，特别适用于大文件。

### 步骤 4：创建 Archive 并添加条目

实例化 `Archive` 对象，然后对每个 `FileInfo` 调用 `CreateEntry`。第一个参数是文件在 zip 中的名称，第二个参数是源 `FileInfo`：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 步骤 5：使用所需编码保存 Zip 存档

最后，将存档持久化到之前打开的 `FileStream`。这里我们使用 ASCII 编码来保存条目名称，但如果文件名包含非 ASCII 字符，可切换为 UTF‑8：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

当 `using` 块结束时，流会自动关闭，zip 文件即可使用。

## 如何使用 Aspose.Zip 将文件夹添加到 Zip

如果您需要 **将文件夹添加到 zip** 而不是单个文件，过程非常简单：

1. 使用 `DirectoryInfo.GetFiles`（以及可选的 `GetDirectories` 用于递归）**枚举文件夹**。  
2. 为每个发现的文件 **创建 `FileInfo`**。  
3. 使用包含文件夹名称的相对路径调用 `CreateEntry`，例如 `"MyFolder/Report.pdf"`。  

由于 API 与 `FileInfo` 配合使用，您无需将整个文件加载到内存中，这对大目录尤为安全。此技巧同样适用于 **zip multiple files asp.net** 场景——在运行时生成报告集并将其作为单个存档交付。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **空的 zip 文件** | `FileInfo` 指向不存在的路径 | 验证 `dataDir` 与文件名；在创建条目前使用 `File.Exists` 检查。 |
| **文件名编码不正确** | 使用默认编码处理非 ASCII 名称 | 在 `ArchiveSaveOptions` 中设置 `Encoding = Encoding.UTF8`。 |
| **大文件导致 OutOfMemoryException** | 将整个文件加载到内存 | `FileInfo` 会流式读取文件；确保未在其他地方将文件读取为字节数组。 |
| **权限被拒绝** | 应用程序对输出文件夹没有写权限 | 以适当权限运行应用或选择可写目录。 |

## 常见问答

**Q: 能为 zip 存档添加密码保护吗？**  
A: 可以。在调用 `Save` 之前，创建 `Archive` 后设置 `archive.Password = "yourPassword"`。

**Q: 能否更新已有的 zip 文件？**  
A: Aspose.Zip 支持使用 `Archive.Open` 打开现有存档，然后添加新条目。

**Q: 如何在 ASP.NET MVC 控制器中压缩文件？**  
A: 同样的代码即可使用，只需确保将输出流作为 `FileResult` 返回给客户端。

**Q: Aspose.Zip 支持哪些加密算法？**  
A: 支持标准的 ZipCrypto 和 AES‑256 加密。

**Q: 如果需要递归压缩文件夹该怎么办？**  
A: 遍历 `Directory.GetFiles`（以及子文件夹），为每个文件创建 `FileInfo`，然后添加到存档中。

## 其他 FAQ

**Q: 如何为大数据集创建 .net zip 存档？**  
A: 使用 `FileInfo` 对象进行流式处理，并在 `ArchiveSaveOptions` 中设置 `CompressionLevel` 以获得最佳性能。

**Q: 能在 .NET Core Web API（zip files asp.net core）中使用 Aspose.Zip 吗？**  
A: 完全可以——该库与 .NET Core 3.1 及更高版本兼容。

**Q: 有没有办法在不编写自定义循环的情况下将文件夹添加到 zip？**  
A: Aspose.Zip 没有单独的 “add folder” 方法，但使用 `DirectoryInfo` 进行遍历轻量且可完全控制条目名称。

**Q: zip 存档的密码保护会影响压缩速度吗？**  
A: 启用加密会带来少量开销，但对大多数使用场景影响微乎其微。

**Q: 商业部署需要什么许可证？**  
A: 生产环境需要付费的 Aspose.Zip 许可证；开发和测试可使用免费试用版。

## 现有 FAQ 部分（保持不变）

### FAQ's

#### Q1: Aspose.Zip 是否兼容所有文件类型？

A1: Aspose.Zip 支持广泛的文件类型，确保在压缩时具有多样性。

#### Q2: 我可以在商业项目中使用 Aspose.Zip 吗？

A2: 当然！访问我们的 [purchase page](https://purchase.aspose.com/buy) 了解许可证选项。

#### Q3: 如何获取 Aspose.Zip 的支持？

A3: 加入我们的社区，访问 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) 获取帮助和讨论。

#### Q4: 是否提供免费试用？

A4: 是的，您可以在此获取 [free trial here](https://releases.aspose.com/)。

#### Q5: 如何获取 Aspose.Zip 的临时许可证？

A5: 请访问 [this link](https://purchase.aspose.com/temporary-license/) 了解获取临时许可证的信息。

## 结论

现在，您已经掌握了 **如何将文件夹添加到 zip**、**如何创建 zip 存档**、**如何将文件添加到 zip**，以及为何此方法是 ASP.NET 和其他 .NET 应用的理想选择。尝试不同的压缩级别、编码和加密选项，以便根据实际需求定制存档。祝您压缩愉快！

---

**最后更新：** 2026-02-28  
**测试环境：** Aspose.Zip for .NET 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}