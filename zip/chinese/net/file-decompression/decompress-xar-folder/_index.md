---
date: 2025-12-17
description: 了解如何使用 Aspose.Zip for .NET 提取 Xar 存档并将其解压到文件夹。请按照本分步指南操作。
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 将 Xar 解压到文件夹
url: /zh/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 将 Xar 解压到文件夹

## 介绍

如果您是一名 .NET 开发者，正在寻找可靠的 **how to extract xar** 方法，Aspose.Zip for .NET 提供了简洁、高性能的 API。在本教程中，我们将完整演示将 Xar 存档解压到文件夹的过程，说明此方法为何能为您节省时间，并展示您需要运行的完整代码。

## 快速答案
- **库的功能是什么？** 它可以在不使用外部工具的情况下读取并提取 Xar 存档。  
- **支持哪些 .NET 版本？** .NET Framework 4.6+、.NET Core 3.1+、.NET 5/6+。  
- **需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **实现需要多长时间？** 通常在 10 分钟以内。  
- **可以解压到自定义文件夹吗？** 是的——只需在 `ExtractToDirectory` 中指定目标路径。

## 什么是 “how to extract xar”？
解压 Xar 存档意味着读取压缩包并将其内部文件写入磁盘上的目录。当您从 macOS 安装程序、备份工具或第三方工具收到 XAR 包，并需要在 .NET 应用程序中处理其内容时，这非常有用。

## 为什么在此任务中使用 Aspose.Zip？
- **零外部依赖** – 纯 .NET，无本机二进制文件。  
- **基于流的 API** – 支持文件、内存流或网络流。  
- **健壮的错误处理** – 详细的异常帮助您排查损坏的存档。  
- **完整的 .NET 兼容性** – 在 Windows、Linux 和 macOS 运行时均可工作。

## 前提条件

在开始之前，请确保您具备以下条件：

- **Aspose.Zip for .NET** – 集成到您的项目中。您可以从 [此处](https://releases.aspose.com/zip/net/) 下载。  
- **Document Directory** – 您的解决方案中用于放置示例 `.xar` 文件和解压输出的文件夹。

## 导入命名空间

在您的 .NET 项目中，包含访问 Aspose.Zip 功能所需的命名空间：

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## 步骤 1：定义文档目录

```csharp
string dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为包含 `sample.xar` 且希望创建输出文件夹的绝对或相对路径。

## 步骤 2：解压 Xar 存档

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

此代码片段打开 Xar 文件，创建 `XarArchive` 实例，并将 **整个 decompress xar archive** 提取到 `DecompressXar_out`。该操作完全基于流，因而即使是大型包也能高效处理。

## 步骤 3：运行代码

构建并运行您的应用程序。执行后，您将在文档目录下看到一个名为 `DecompressXar_out` 的新文件夹，里面包含原始 `.xar` 存档中打包的所有文件。

## 常见问题与技巧

- **文件未找到** – 确保 `File.OpenRead` 中的路径正确指向 `sample.xar`。使用 `Path.Combine` 可获得更安全的路径处理。  
- **访问被拒绝** – 以足够的文件系统权限运行应用程序，尤其是在写入受保护目录时。  
- **存档损坏** – Aspose.Zip 会抛出 `InvalidDataException`；请确认源 `.xar` 文件完整无损。

## 常见问题解答

**问：Aspose.Zip 是否兼容最新的 .NET 框架版本？**  
答：是的，Aspose.Zip 定期更新，以确保与最新的 .NET 框架版本兼容。具体细节请参阅 [文档](https://reference.aspose.com/zip/net/)。

**问：我可以在购买前试用 Aspose.Zip 吗？**  
答：当然！您可以从 [此处](https://releases.aspose.com/) 下载免费试用版。

**问：如何获取 Aspose.Zip 的支持？**  
答：如有任何疑问或需要帮助，请访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)。

**问：Aspose.Zip 是否提供临时许可证？**  
答：是的，可从 [此处](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**问：在哪里可以购买 Aspose.Zip for .NET？**  
答：您可以在 [此处](https://purchase.aspose.com/buy) 购买 Aspose.Zip for .NET。

**问：我能只提取 Xar 存档中的特定文件吗？**  
答：可以——使用 `archive.Entries` 枚举条目，并对选定的条目调用 `ExtractToFile`。

**问：库是否支持受密码保护的 Xar 文件？**  
答：目前，Xar 存档不支持加密；如果遇到受保护的文件，需要在使用 Aspose.Zip 之前先解密。

---

**最后更新：** 2025-12-17  
**测试环境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}