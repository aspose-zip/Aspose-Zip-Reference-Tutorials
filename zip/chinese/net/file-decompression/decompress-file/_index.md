---
date: 2025-12-12
description: 了解如何使用 Aspose.Zip 快速解压 .NET 文件。针对 .NET 档案解压和 C# 从档案中提取的逐步指南。
linktitle: Decompressing a File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 在 .NET 中解压文件
url: /zh/net/file-decompression/decompress-file/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 解压文件 .NET

## 介绍

在 .NET 开发领域，学习如何**高效解压文件 .NET**对于性能关键的应用至关重要。Aspose.Zip for .NET 提供了简洁、高性能的 API，让您在不处理底层流管理的情况下完成 .NET 存档提取。在本教程中，我们将演示一个完整的 **Aspose.Zip 提取** 场景——打开 Lzip 存档并仅用几行 C# 代码将其内容解压。

## 快速答案
- **哪个库处理 .NET 存档提取？** Aspose.Zip for .NET  
- **哪个方法在 C# 中提取 Lzip 存档？** `LzipArchive.Extract`  
- **生产环境需要许可证吗？** 是的，非评估使用必须购买商业许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **基本提取需要多长时间？** 对于小文件通常在一秒以内。

## 什么是 “decompress file .NET”？
在 .NET 中解压文件指的是读取压缩存档（如 ZIP、LZIP、GZIP），并将其原始内容写回文件系统。Aspose.Zip 抽象了这些复杂性，让您专注于业务逻辑，而无需关心压缩算法。

## 为什么使用 Aspose.Zip 进行 .NET 存档提取？
- **零依赖** – 无外部本机二进制文件。  
- **丰富的格式支持** – ZIP、GZIP、TAR、LZIP 等。  
- **线程安全 API** – 适用于 Web 服务和后台任务。  
- **全面的文档** 和 **Aspose.Zip 教程** 资源。

## 先决条件

- **Aspose.Zip for .NET** – 安装 NuGet 包或下载库。您可以在[此处](https://reference.aspose.com/zip/net/)找到文档。  
- **开发环境** – Visual Studio 2022、.NET 6 SDK，或任何支持 C# 的 IDE。  
- **你的文档目录** – 磁盘上的文件夹，存放压缩文件 (`archive.lz`) 并用于保存解压后的文件。

## 导入命名空间

首先，导入文件 I/O 和 Aspose.Zip Lzip 支持所需的命名空间：

```csharp
using System;
using System.IO;
using Aspose.Zip.Lzip;
```

## .NET 存档提取：设置工作文件夹

```csharp
string dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为包含 `archive.lz` 的绝对或相对路径。将路径保存在变量中可以使代码更易复用和维护。

## 步骤 1：使用 C# 打开并提取 Lzip 存档

**c# extract from archive** 操作的核心是一段简短的 `using` 代码块，它打开 Lzip 文件并将解压后的数据写入新文件。

```csharp
//ExStart: OpenLzipArchive
using (var archive = new LzipArchive(Path.Combine(dataDir, "archive.lz")))
{
    using (var extracted = File.Create(Path.Combine(dataDir, "output.txt")))
    {
        archive.Extract(extracted);
    }
}
//ExEnd: OpenLzipArchive
Console.WriteLine("Successfully Opened Lzip Archive");
```

此代码片段演示了 **extract lzip archive c#** 模式：

1. **创建** 指向源文件的 `LzipArchive` 实例。  
2. **创建** 目标文件 (`output.txt`)。  
3. **调用** `Extract` 写入解压后的字节。  
4. `using` 语句确保所有流自动关闭。

## 常见问题及解决方案

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| `FileNotFoundException` | `dataDir` 路径错误 | 验证文件夹路径并确保 `archive.lz` 存在。 |
| `UnauthorizedAccessException` | 写入权限不足 | 以适当的权限运行应用或选择可写文件夹。 |
| 输出文件为空 | 存档损坏或不是 Lzip 文件 | 确认源文件是有效的 Lzip 存档；如有需要可使用 `LzipArchive.IsValid`。 |

## 常见问题

**问：Aspose.Zip 与所有 .NET 应用程序兼容吗？**  
**答：** 是的，Aspose.Zip for .NET 可与桌面、Web、云和微服务项目等兼容。

**问：我可以在个人和商业项目中使用 Aspose.Zip 吗？**  
**答：** 当然可以。该库提供灵活的许可模式，支持评估、个人和商业使用。

**问：如何获取 Aspose.Zip for .NET 的支持？**  
**答：** 访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 提问并与社区交流。

**问：是否提供免费试用？**  
**答：** 是的，您可以通过[此处](https://releases.aspose.com/)下载免费试用版，体验 Aspose.Zip for .NET 的功能。

**问：在哪里购买 Aspose.Zip for .NET？**  
**答：** 前往[购买页面](https://purchase.aspose.com/buy)获取许可证。

## 结论

您现在已经掌握了如何使用 Aspose.Zip 的简洁 API **解压文件 .NET**。这种方法简化了 .NET 存档提取，减少了样板代码，并能很好地扩展到大规模应用。欲了解更深入的场景——如受密码保护的存档、多文件提取或自定义压缩级别——请参考完整的[文档](https://reference.aspose.com/zip/net/)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2025-12-12  
**测试环境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

---