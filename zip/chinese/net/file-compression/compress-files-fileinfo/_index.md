---
date: 2026-02-05
description: 学习如何使用 Aspose.Zip 在 C# 中压缩多个文件并创建 .NET ZIP 存档。本分步指南展示了在 ASP.NET 项目中使用
  FileInfo 进行文件压缩。
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 在 C# 中压缩多个文件
url: /zh/net/file-compression/compress-files-fileinfo/
weight: 11
---

/products-backtop-button >}}

Make sure to keep shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 在 C# 中压缩多个文件

## 介绍

如果您需要以编程方式 **zip multiple files c#**，Aspose.Zip for .NET 为您提供了一个简洁、高性能的 API，适用于任何 .NET（包括 ASP.NET）应用程序。在本教程中，我们将演示如何使用 `FileInfo` 类压缩文件，向您展示如何 **add files to zip**，并解释为何此方法非常适合现代 .NET 项目。让我们开始吧！

## 快速答案
- **What is the easiest way to create a zip archive?** 使用 Aspose.Zip 的 `Archive` 类结合 `FileInfo` 对象。  
- **Can I add multiple files at once?** 可以——只需为每个文件创建一个 `FileInfo` 并调用 `CreateEntry`。  
- **Do I need a special license for ASP.NET?** 生产环境需要商业 Aspose.Zip 许可证；免费试用可用于评估。  
- **Which .NET versions are supported?** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **Is the API thread‑safe?** 是的，只要每个线程使用各自的 `Archive` 实例。  
- **How to zip files c# without loading them into memory?** 使用 `FileInfo` 对象——它们直接流式传输数据。  

## 如何在 C# 中压缩多个文件

ZIP 存档将一个或多个文件打包成单个压缩容器。这可以减少存储空间、加快网络传输并简化分发。无论是交付日志、导出报告，还是为客户打包资源，掌握 **how to zip files c#** 的编程方法都是每位 .NET 开发者的宝贵技能。

## 为什么使用 Aspose.Zip 来 Add Files to Zip？

- **Zero external dependencies** – 纯 .NET 实现。  
- **Full control over compression level and encoding**（ASCII、UTF‑8 等）。  
- **Supports large files**（> 4 GB）以及密码保护。  
- **Consistent API across .NET Framework, .NET Core, and .NET 5+**。  

## 前提条件

在深入代码之前，请确保您已拥有：

1. 已安装 **Aspose.Zip for .NET**。从 [Aspose.Zip download page](https://releases.aspose.com/zip/net/) 下载最新包。  
2. 您机器上的一个文件夹，里面包含要压缩的文件（例如 `alice29.txt` 和 `fields.c`）。  

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

首先，定义保存源文件的文件夹。将占位符替换为系统上的绝对或相对路径：

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** 使用 `Path.Combine` 以跨平台方式构建路径。

### 步骤 2：打开 Zip 文件进行写入

创建指向输出 zip 文件的 `FileStream`。该流以 **Create** 模式打开，会覆盖同名的已有文件：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步骤 3：为每个源文件准备 `FileInfo` 对象

`FileInfo` 为 Aspose.Zip 提供对磁盘上物理文件的直接访问。为每个要压缩的文件创建一个实例：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** 它避免将整个文件加载到内存中，这对大文件尤其有帮助。

### 步骤 4：创建 Archive 并添加条目

实例化一个 `Archive` 对象，然后对每个 `FileInfo` 调用 `CreateEntry`。第一个参数是文件在 zip 中的名称，第二个参数是源 `FileInfo`：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 步骤 5：使用所需编码保存 Zip 存档

最后，将存档持久化到之前打开的 `FileStream`。这里我们使用 ASCII 编码作为条目名称，但如果文件名包含非 ASCII 字符，可以切换为 UTF‑8：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

当 `using` 块结束时，流会自动关闭，zip 文件即可使用。

## 常见问题与解决方案

| Issue | Cause | Fix |
|-------|-------|-----|
| **Empty zip file** | `FileInfo` 指向不存在的路径 | 验证 `dataDir` 和文件名；在创建条目前使用 `File.Exists` 检查。 |
| **Incorrect filename encoding** | 使用默认编码处理非 ASCII 名称 | 在 `ArchiveSaveOptions` 中设置 `Encoding = Encoding.UTF8`。 |
| **OutOfMemoryException on large files** | 将整个文件加载到内存中 | `FileInfo` 会流式读取文件；确保未在其他地方将文件读取为字节数组。 |
| **Permission denied** | 应用程序没有对输出文件夹的写权限 | 以适当权限运行应用或选择可写目录。 |

## 常见问题解答

**Q: 我可以为 zip 存档添加密码保护吗？**  
A: 可以。在创建 `Archive` 后，在调用 `Save` 之前设置 `archive.Password = "yourPassword"`。

**Q: 能否更新已有的 zip 文件？**  
A: Aspose.Zip 支持使用 `Archive.Open` 打开已有存档，然后添加新条目。

**Q: 如何在 ASP.NET MVC 控制器中压缩文件？**  
A: 代码相同，只需确保将输出流作为 `FileResult` 返回给客户端。

**Q: Aspose.Zip 支持哪些加密算法？**  
A: 它支持标准的 ZipCrypto 和 AES‑256 加密。

**Q: 如果需要递归压缩文件夹怎么办？**  
A: 遍历 `Directory.GetFiles`（以及子文件夹），为每个文件创建 `FileInfo`，然后将其添加到存档中。

## Existing FAQ Section (kept unchanged)

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

现在，您已经了解了使用 Aspose.Zip for .NET **how to zip multiple files c#** 的方法，掌握了 **add files to zip** 的技巧，并明白了为何此方法非常适合 ASP.NET 以及其他 .NET 应用。尝试不同的压缩级别、编码和加密选项，以满足您的具体需求。祝压缩愉快！

---

**最后更新：** 2026-02-05  
**测试环境：** Aspose.Zip for .NET 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}