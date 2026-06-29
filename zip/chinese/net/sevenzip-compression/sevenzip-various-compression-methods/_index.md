---
date: 2026-06-29
description: 了解如何使用 Aspose.Zip for .NET 将文件夹压缩为 7z，涵盖 LZMA2、BZip2 和 Store 等七种压缩方法。非常适合以编程方式创建
  7z 存档。
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip 多种压缩方法
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何将文件夹压缩为 7z – Aspose.Zip for .NET 教程
url: /zh/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何将文件夹压缩为 7z – Aspose.Zip for .NET 教程

## 介绍

如果您需要在 .NET 应用程序中以编程方式 **compress folder to 7z** 存档，那么您来对地方了。Aspose.Zip for .NET 使生成 Seven Zip 存档变得简单，支持所有支持的压缩算法，无论您是想打包整个目录以供分发，还是仅需要可靠的 **seven zip archive .net** 解决方案。在本指南中，我们将介绍三种流行的压缩方法——LZMA2、BZip2 和 Store（无压缩），并展示如何仅用几行 C# 代码生成 7z 文件。

## 快速答复
- **应该使用哪个库？** Aspose.Zip for .NET 提供了最完整的 Seven Zip 功能集。  
- **哪种压缩方法提供最佳比例？** LZMA2 通常在混合数据上提供最高的压缩率。  
- **我可以创建不进行任何压缩的 7z 吗？** 是的——使用 Store（无压缩）方法。  
- **开发需要许可证吗？** 提供免费试用；生产环境需要许可证。  
- **这与 .NET 6/7 兼容吗？** 完全兼容——Aspose.Zip 支持 .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 和 .NET 5–10。

## Seven Zip 压缩方法有哪些？

Seven Zip 支持多种算法，每种算法针对不同场景进行优化。**LZMA2** 提供最高的压缩比（通常比 BZip2 小 30‑40 %），**BZip2** 在保持对更广泛的旧工具支持的同时提供稳健的压缩，而 **Store** 则仅存档文件而不压缩，完美保留原始时间戳。

## 前置条件

在开始之前，请确保您具备：

- 具备 C# 和 Visual Studio 的基础知识。  
- 已安装 Aspose.Zip for .NET 库。可从官方下载页面 **[here](https://releases.aspose.com/zip/net/)** 获取。  
- 一个包含要归档文件的文件夹 (`dataDir`)。

## 导入命名空间

首先，将所需的命名空间添加到您的 C# 文件中：

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

这些类让您能够访问压缩设置和存档处理功能。

## LZMA2 压缩 – 如何创建具有最高压缩率的 7z

`Archive` 类表示可以包含多个文件的 7z 存档。  
LZMA2 算法在受支持的方法中提供最高的压缩比。它通过将输入划分为块并应用复杂的字典压缩来实现。在 Aspose.Zip 中，您在向 `Archive` 对象添加文件之前，将 `CompressionMethod` 设置为 `CompressionMethod.Lzma2`。

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **专业提示：** 当源文件大于 1 MB 时，LZMA2 效果最佳。对于许多小文件，BZip2 可能更快。

## BZip2 压缩 – 均衡的选择

`Archive` 类表示可以包含多个文件的 7z 存档。  
BZip2 提供稳健的压缩，并对旧工具具有良好的兼容性。它使用 Burrows‑Wheeler 变换和 Huffman 编码来减小体积。在 Aspose.Zip 中，配置 `Archive` 实例时选择 `CompressionMethod.BZip2`，这在大多数文本和二进制文件中平衡了速度和压缩比。

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 在保持合理速度的同时提供稳健的压缩，是当目标环境不支持 LZMA2 时的良好备选方案。

## Store（无压缩） – 当大小不重要时

`Archive` 类表示可以包含多个文件的 7z 存档。  
Store 方法在不压缩数据的情况下创建存档。它仅将原始文件复制到 7z 容器中，保留时间戳和目录结构。要在 Aspose.Zip 中使用它，请在添加要打包的文件之前，将 `Archive` 的 `CompressionMethod` 设置为 `CompressionMethod.Store`。

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

如果您只需将文件打包在一起而不改变其大小，请使用 Store 方法——这对于保留原始时间戳或在实时解压存档时非常适用。

## 如何向 7z 添加文件？

通过创建 `Archive` 实例、设置所需的 `CompressionMethod`，并调用 `AddAllFiles(dataDir)`，即可向 7z 存档添加文件。该方法递归扫描指定文件夹，保留存档内的目录层次结构。此方法让您在初始设置后仅用一行代码即可 **compress folder to 7z**。

## 常见使用场景

| 场景 | 推荐方法 |
|----------|--------------------|
| 分发大型安装程序 | LZMA2 |
| 使用旧工具共享日志 | BZip2 |
| 打包文件以便快速提取 | Store（无压缩） |
| 在 Web 服务中需要实时 **compress folder to 7z** | LZMA2（最佳比例） |

## 故障排除与技巧

- **存档中缺少文件？** 请确认 `dataDir` 指向正确的目录，并且进程具有读取权限。  
- **在较旧的 7‑Zip 版本上打开存档失败？** 请使用 BZip2 或 Store，因为 LZMA2 可能需要更新的解压库。  
- **性能瓶颈？** 对于大规模数据集，考虑流式写入存档，而不是将所有条目加载到内存中。

## 常见问题

**问：我可以在 .NET 中使用 Aspose.Zip 处理任何类型的文件吗？**  
答：是的，Aspose.Zip 支持广泛的文件格式，几乎可以压缩和解压任何文件类型。

**问：Aspose.Zip for .NET 是否提供免费试用？**  
答：是的，您可以在 **[here](https://releases.aspose.com/)** 获取免费试用。

**问：在哪里可以找到 Aspose.Zip for .NET 的文档？**  
答：完整的 API 参考可在 **[here](https://reference.aspose.com/zip/net/)** 获取。

**问：如何获取 Aspose.Zip for .NET 的临时许可证？**  
答：临时许可证可在 **[here](https://purchase.aspose.com/temporary-license/)** 获取。

**问：在哪里可以获得 Aspose.Zip for .NET 的支持？**  
答：您可以在 **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** 上寻求支持。

---

**Last Updated:** 2026-06-29  
**Tested With:** Aspose.Zip for .NET 24.12  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [压缩文件 c# – 使用 Aspose.Zip for .NET 创建 7z 存档](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [如何使用 Aspose.Zip for .NET 压缩文件夹](/zip/net/directory-and-folder-compression/compress-directory/)
- [如何在 Aspose.Zip for .NET 中压缩 LZMA](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}