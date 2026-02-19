---
date: 2026-02-12
description: 学习如何使用 Aspose.Zip for .NET 在 .NET 中创建未压缩的 zip。本指南将向您展示如何在不进行压缩的情况下压缩文件、以未压缩方式存储文件，以及高效管理归档。
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 创建未压缩的 zip
url: /zh/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 创建未压缩的 zip .net

在现代 .NET 开发中，**创建未压缩的 zip .net** 可以显著提升归档速度并保持文件大小可预测。当您需要**在不压缩的情况下压缩文件**——例如，为了符合监管规定或加快下游处理——Aspose.Zip for .NET 提供了简洁直观的 API。在本教程中，我们将逐步演示创建未压缩 ZIP 存档、添加文件以及将该解决方案集成到您的应用程序中的完整步骤。

## 快速答案
- **“未压缩的 zip” 是什么意思？** 它是一个 ZIP 存档，其中每个条目都使用 “store” 方法存储，保持原始文件字节不变。  
- **为什么要避免压缩？** 为了加快归档速度，保持下游处理所需的原始文件大小，或满足禁止数据更改的监管要求。  
- **哪个 Aspose.Zip 类处理此功能？** `ArchiveEntrySettings` 与 `StoreCompressionSettings` 结合使用。  
- **我需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持的 .NET 版本？** .NET Framework、.NET Core、.NET 5/6/7 及更高版本。  

## 什么是 create uncompressed zip .net？
创建未压缩的 ZIP 意味着使用 *store* 压缩方法将每个文件添加到 ZIP 容器中。文件在字节上与原始文件完全相同，这在您需要快速归档或保持数据不变时非常理想。

## 为什么在不压缩的情况下使用 Aspose.Zip 处理 zip 文件？
- **速度：** 不会运行 CPU 密集型的压缩算法。  
- **可预测的大小：** 存档大小等于原始文件总和加上最小的 ZIP 开销。  
- **兼容性：** 生成的 ZIP 可在任何标准解压工具中使用。  
- **灵活性：** 如有需要，仍可在同一存档中混合压缩和未压缩的条目。  

## 前提条件
- **Aspose.Zip for .NET** – 已集成到您的项目中。请参阅官方[文档](https://reference.aspose.com/zip/net/)了解安装步骤。  
- **.NET 开发环境** – Visual Studio、VS Code 或您喜欢的任何 IDE。  
- **文档目录** – 您机器上包含要归档文件的文件夹（例如，“Your Document Directory”）。  

## 导入命名空间
在编写任何代码之前，导入所需的命名空间，以便编译器知道在哪里找到 Aspose 类。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 步骤 1：设置文档目录
定义源文件所在的路径。将占位符替换为系统中实际的文件夹路径。

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：创建无压缩的 Zip 存档
本教程的核心——我们创建一个使用 `StoreCompressionSettings` 配置的 `Archive` 实例。这告诉 Aspose.Zip 对每个条目进行 *store*（即不压缩）。

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **专业提示：** 如果您需要在 **将文件保存到 zip** 时对部分文件进行压缩而对其他文件保持未压缩，请为每个文件创建单独的 `ArchiveEntrySettings` 实例，并将它们添加到同一个 `Archive` 中。

## 常见问题及解决方案
| 问题 | 出现原因 | 解决办法 |
|-------|----------------|-----|
| **未找到文件** | `dataDir` 路径不正确或缺少文件扩展名。 | 验证路径并确保文件存在。使用 `Path.Combine` 进行更安全的拼接。 |
| **访问被拒绝** | 进程没有读取源文件或写入 ZIP 的权限。 | 使用适当的权限运行应用程序，或选择具有写入权限的文件夹。 |
| **ZIP 中文件大小异常** | 存档使用了默认压缩方式创建。 | 确保向 `ArchiveEntrySettings` 传递 `new StoreCompressionSettings()`。 |

## 常见问题解答

**问：我可以对特定文件类型进行压缩，而对其他文件保持未压缩吗？**  
答：可以，您可以为每个文件创建不同的 `ArchiveEntrySettings`，并在同一存档中混合压缩和未压缩的条目。

**问：Aspose.Zip for .NET 是否兼容 .NET Core 和 .NET 5/6？**  
答：完全兼容。该库支持 .NET Framework、.NET Core、.NET Standard 以及最新的 .NET 版本。

**问：在归档过程中应如何处理异常？**  
答：将归档代码放在 `try‑catch` 块中，并记录异常细节。这可确保优雅的失败并便于调试。

**问：Aspose.Zip 是否支持多线程归档？**  
答：是的，您可以并行处理多个文件并将其添加到存档中，但请记住 `Archive` 对象本身不是线程安全的；在添加条目时需要同步访问。

**问：我能在不进行重大代码更改的情况下将 Aspose.Zip 集成到现有项目中吗？**  
答：完全可以。该 API 设计为简单的即插即用。请参考官方[文档](https://reference.aspose.com/zip/net/)获取迁移指南。

---

**最后更新：** 2026-02-12  
**测试环境：** Aspose.Zip for .NET（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}