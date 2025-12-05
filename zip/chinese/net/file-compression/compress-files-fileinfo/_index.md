---
date: 2025-12-05
description: 了解如何使用 Aspose.Zip for .NET 创建 ZIP 压缩包并向其中添加文件。本分步指南展示了在 ASP.NET 项目中如何使用
  FileInfo 对文件进行压缩。
language: zh
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 创建 Zip 存档 – 使用 FileInfo 压缩文件
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 创建 Zip 存档

## 介绍

如果您需要以编程方式 **创建 zip 存档**，Aspose.Zip for .NET 为您提供了一个简洁、高性能的 API，适用于任何 .NET（包括 ASP.NET）应用程序。在本教程中，我们将演示如何使用 `FileInfo` 类压缩文件，向您展示 **如何向 zip 添加文件**，并解释为何这种方式是现代 .NET 项目的理想选择。让我们开始吧！

## 快速回答
- **创建 zip 存档的最简方法是什么？** 使用 Aspose.Zip 的 `Archive` 类配合 `FileInfo` 对象。  
- **可以一次添加多个文件吗？** 可以——只需为每个文件创建一个 `FileInfo` 并调用 `CreateEntry`。  
- **ASP.NET 需要特殊许可证吗？** 生产环境需要商业版 Aspose.Zip 许可证；免费试用可用于评估。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **API 是否线程安全？** 是的，只要每个线程使用各自的 `Archive` 实例。

## 什么是 Zip 存档以及为何要创建它？
Zip 存档将一个或多个文件打包成单个压缩容器。这可以减少存储空间、加快网络传输速度，并简化分发。无论是交付日志、导出报告，还是为客户端打包资源，掌握 **如何创建 zip 存档** 的编程技巧都是每位 .NET 开发者的宝贵技能。

## 为什么使用 Aspose.Zip 向 Zip 添加文件？
- **零外部依赖** —— 纯 .NET 实现。  
- **对压缩级别和编码（ASCII、UTF‑8 等）拥有完整控制**。  
- **支持大文件**（> 4 GB）和密码保护。  
- **在 .NET Framework、.NET Core 和 .NET 5+ 上保持一致的 API**。

## 前置条件

在开始编写代码之前，请确保您已：

1. 安装 **Aspose.Zip for .NET**。从 [Aspose.Zip 下载页面](https://releases.aspose.com/zip/net/)获取最新包。  
2. 在机器上准备好包含待压缩文件的文件夹（例如 `alice29.txt` 和 `fields.c`）。  

## 引入命名空间

在任何需要处理 zip 存档的 C# 文件中，添加以下 `using` 语句：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

这些命名空间为您提供 `Archive` 类、保存选项以及标准 I/O 实用工具。

## 步骤指南

### 步骤 1：设置文档目录

首先，定义保存源文件的文件夹。将占位符替换为系统中的绝对或相对路径：

```csharp
string dataDir = "Your Document Directory";
```

> **小技巧：** 使用 `Path.Combine` 以跨平台方式构建路径。

### 步骤 2：打开用于写入的 Zip 文件

创建指向输出 zip 文件的 `FileStream`。该流以 **Create** 模式打开，会覆盖同名的已有文件：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步骤 3：为每个源文件准备 `FileInfo` 对象

`FileInfo` 让 Aspose.Zip 直接访问磁盘上的物理文件。为每个要压缩的文件创建一个实例：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **为何使用 `FileInfo`？** 它避免将整个文件加载到内存中，对大文件尤为友好。

### 步骤 4：创建 Archive 并添加条目

实例化 `Archive` 对象，然后对每个 `FileInfo` 调用 `CreateEntry`。第一个参数是文件在 zip 中的名称，第二个参数是源 `FileInfo`：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 步骤 5：使用所需编码保存 Zip 存档

最后，将存档持久化到前面打开的 `FileStream`。这里我们使用 ASCII 编码来保存条目名称，如果文件名包含非 ASCII 字符，可切换为 UTF‑8：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

当 `using` 块结束时，流会自动关闭，zip 文件即可使用。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **空 zip 文件** | `FileInfo` 指向不存在的路径 | 核实 `dataDir` 和文件名；使用 `File.Exists` 在创建条目前进行检查。 |
| **文件名编码不正确** | 对非 ASCII 名称使用默认编码 | 在 `ArchiveSaveOptions` 中设置 `Encoding = Encoding.UTF8`。 |
| **大文件导致 OutOfMemoryException** | 将整个文件加载到内存 | `FileInfo` 采用流式读取；确保未在其他地方将文件读取为字节数组。 |
| **权限被拒绝** | 应用程序对输出文件夹没有写入权限 | 以合适的权限运行应用或选择可写目录。 |

## 常见问答

**问：我可以为 zip 存档添加密码保护吗？**  
答：可以。在调用 `Save` 之前，创建 `Archive` 后设置 `archive.Password = "yourPassword"`。

**问：是否可以更新已有的 zip 文件？**  
答：Aspose.Zip 支持使用 `Archive.Open` 打开现有存档，然后添加新条目。

**问：如何在 ASP.NET MVC 控制器中压缩文件？**  
答：同样的代码即可使用，只需确保将输出流作为 `FileResult` 返回给客户端。

**问：Aspose.Zip 支持哪些加密算法？**  
答：它支持标准的 ZipCrypto 和 AES‑256 加密。

**问：如果需要递归压缩文件夹怎么办？**  
答：遍历 `Directory.GetFiles`（以及子文件夹），为每个文件创建 `FileInfo`，然后加入存档。

## 现有 FAQ 部分（保持不变）

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## 结论

现在，您已经掌握了使用 Aspose.Zip for .NET **创建 zip 存档**、**向 zip 添加文件** 的方法，并了解了为何该方案是 ASP.NET 及其他 .NET 应用的理想选择。尝试不同的压缩级别、编码和加密选项，以满足您的具体需求。祝压缩愉快！

---

**最后更新：** 2025-12-05  
**测试环境：** Aspose.Zip for .NET 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}