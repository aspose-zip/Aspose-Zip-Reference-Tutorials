---
date: 2025-12-25
description: 学习如何使用 Aspose.Zip for .NET 创建 7z 文件，涵盖 LZMA2、BZip2 和 Store 等七种压缩方法。非常适用于将文件夹压缩为
  7z 的场景。
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何创建 7z 文件 – Aspose.Zip for .NET 教程
url: /zh/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何创建 7z 文件 – Aspose.Zip for .NET 教程

## 介绍

如果您需要在 .NET 应用程序中**以编程方式创建 7z**压缩包，您来对地方了。Aspose.Zip for .NET 能轻松生成使用任意受支持压缩算法的 7z（Seven Zip）归档，无论您是想**将文件夹压缩为 7z**以便分发，还是仅需要一个可靠的**seven zip archive .net**解决方案。本指南将演示三种常用的压缩方式——LZMA2、BZip2 和 Store（无压缩），并展示如何仅用几行 C# 代码生成 7z 文件。

## 快速答案
- **应该使用哪个库？** Aspose.Zip for .NET 提供最完整的 Seven Zip 功能集。  
- **哪种压缩方式比例最高？** 对于混合数据，LZMA2 通常能提供最高的压缩率。  
- **可以创建不进行压缩的 7z 吗？** 可以——使用 Store（无压缩）方式。  
- **开发阶段需要许可证吗？** 提供免费试用版；生产环境需要许可证。  
- **是否兼容 .NET 6/7？** 完全兼容——Aspose.Zip 支持 .NET Framework、.NET Core 以及 .NET 5 以上版本。

## 七 Zip 压缩方法有哪些？

Seven Zip 支持多种算法，每种都针对不同场景进行优化：

* **LZMA2** – 高压缩率，适用于大型混合类型文件。  
* **BZip2** – 稳定的压缩效果，但速度慢于 LZMA2；在需要兼容旧工具时很有用。  
* **Store** – 不进行压缩；当只需要归档而不需要减小体积（例如保留原始文件时间戳）时非常合适。

了解这些**seven zip compression methods**有助于为项目选择合适的设置。

## 前置条件

在开始之前，请确保您已具备：

- 基本的 C# 和 Visual Studio 知识。  
- 已安装 Aspose.Zip for .NET 库。可从官方下载页面**[此处](https://releases.aspose.com/zip/net/)**获取。  
- 一个包含待归档文件的文件夹（`dataDir`）。

## 导入命名空间

首先，在 C# 文件中添加所需的命名空间：

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

这些类为您提供压缩设置和归档处理的访问权限。

## LZMA2 压缩 – 如何创建最高比例的 7z

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

> **小技巧：** 当源文件大于 1 MB 时，LZMA2 效果最佳。对于大量小文件，BZip2 可能更快。

## BZip2 压缩 – 均衡的选择

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 在保持合理速度的同时提供稳固的压缩率，是在目标环境不支持 LZMA2 时的良好备选。

## Store（无压缩） – 当大小不重要时

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

如果您只需要将文件打包在一起而不改变其大小——例如保留原始时间戳或在运行时即时解压——请使用 Store 方法。

## 常见使用场景

| 场景 | 推荐方法 |
|----------|--------------------|
| 分发大型安装程序 | LZMA2 |
| 与旧版工具共享日志 | BZip2 |
| 打包文件以便快速提取 | Store（无压缩） |
| 在 Web 服务中**实时将文件夹压缩为 7z** | LZMA2（获得最佳比例） |

## 故障排除与技巧

- **归档中缺少文件？** 检查 `dataDir` 是否指向正确目录，并确认进程拥有读取权限。  
- **在旧版 7‑Zip 中无法打开归档？** 使用 BZip2 或 Store，因为 LZMA2 可能需要更新的解压库。  
- **性能瓶颈？** 对于海量数据，考虑使用流式写入归档，而不是一次性将所有条目加载到内存。

## 常见问题

**问：Aspose.Zip for .NET 能处理任何类型的文件吗？**  
答：可以，Aspose.Zip 支持广泛的文件格式，几乎可以压缩和解压任意文件类型。

**问：Aspose.Zip for .NET 有免费试用吗？**  
答：有，您可以在**[此处](https://releases.aspose.com/)**获取免费试用。

**问：在哪里可以找到 Aspose.Zip for .NET 的文档？**  
答：完整的 API 参考位于**[此处](https://reference.aspose.com/zip/net/)**。

**问：如何获取 Aspose.Zip for .NET 的临时许可证？**  
答：临时许可证可在**[此处](https://purchase.aspose.com/temporary-license/)**获取。

**问：在哪里可以获得 Aspose.Zip for .NET 的技术支持？**  
答：您可以在**[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)**寻求帮助。

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**最后更新：** 2025-12-25  
**测试环境：** Aspose.Zip for .NET 24.12  
**作者：** Aspose  

---