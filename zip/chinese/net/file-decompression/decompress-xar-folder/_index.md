---
date: 2026-02-28
description: 了解如何使用 Aspose.Zip for .NET 提取 xar 存档并将 xar 文件解压到文件夹。请按照本分步指南操作。
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 将 Xar 存档提取到文件夹
url: /zh/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspise.Zip for .NET 将 Xar 存档解压到文件夹的方式

## 简介

如果你是一名需要 **快速可靠地解压 xar 存档** 的 .NET 开发者，Aspose.Zip for .NET 提供了简洁、高性能的 API，能够在不依赖外部工具的情况下完成整个过程。在本教程中，我们将逐步演示如何将 Xar 存档解压到文件夹，说明此方法为何能为你节省时间，并提供可直接运行的代码示例。完成后，你将了解何时使用此方案、如何将其集成到项目中，以及如何规避常见陷阱。

## 快速解答

- **此库的功能是什么？** 它无需外部工具即可读取和提取 Xar 压缩包。
- **支持哪些 .NET 版本？** .NET Framework 4.6+、.NET Core 3.1+、.NET 5/6+。
- **需要许可证吗？** 免费试用版适用于开发环境；生产环境需要商业许可证。
- **部署需要多长时间？** 通常不到 10 分钟。
- **我可以提取到自定义文件夹吗？** 可以——只需在 `ExtractToDirectory` 中指定目标路径即可。

## 如何提取 Xar？

提取 Xar 压缩包是指读取压缩包并将其内部文件写入磁盘上的指定目录。当您从 macOS 安装程序、备份实用程序或第三方工具收到 XAR 包，并且需要在 .NET 应用程序中处理其内容时，此功能非常有用。

## 为什么选择 Aspose.Zip 来完成这项任务？

- **零外部依赖** – 纯 .NET 开发，无需原生二进制文件。
- **基于流的 API** – 可处理文件、内存流或网络流。
- **强大的错误处理能力** – 详细的异常信息可帮助您排查损坏的归档文件。
- **完全兼容 .NET** – 可在 Windows、Linux 和 macOS 运行时环境下运行。

## 前提条件

在开始之前，请确保您已具备以下条件：

- **Aspose.Zip for .NET** – 已集成到您的项目中。您可以从[此处](https://releases.aspose.com/zip/net/)下载。
- **文档目录** – 解决方案中的一个文件夹，用于存放示例 `.xar` 文件和提取的输出结果。

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

将 `"Your Document Directory"` 替换为包含 `sample.xar` 的绝对路径或相对路径，以及您希望创建输出文件夹的位置。稍后使用 `Path.Combine` 有助于避免跨操作系统出现路径分隔符问题。

## 步骤 2：解压缩 Xar 归档文件

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

此代码片段打开 Xar 文件，创建一个 `XarArchive` 实例，并将**整个解压缩后的 Xar 归档文件**提取到 `DecompressXar_out` 文件夹中。此操作完全基于流，因此即使处理大型软件包也能高效运行。

## 步骤 3：运行代码

构建并运行您的应用程序。执行后，您将在文档目录中找到一个名为 `DecompressXar_out` 的新文件夹，其中包含原始 `.xar` 归档文件中打包的所有文件。

## 常见问题及提示

- **文件未找到** – 请确保 `File.OpenRead` 中的路径正确指向 `sample.xar`。使用 `Path.Combine` 可以更安全地处理路径。
- **访问被拒绝** – 使用足够的文件系统权限运行应用程序，尤其是在写入受保护目录时。
- **归档文件已损坏** – Aspose.Zip 会抛出 `InvalidDataException` 异常；请验证源 `.xar` 文件是否完整。

## 常见问题解答

**问：Aspose.Zip 是否兼容最新的 .NET Framework 版本？** 

答：是的，Aspose.Zip 会定期更新以确保与最新的 .NET Framework 版本兼容。有关详细信息，请参阅[文档](https://reference.aspose.com/zip/net/)。

**问：我可以在购买前试用 Aspose.Zip 吗？** 

答：当然可以！您可以从[此处](https://releases.aspose.com/)下载免费试用版。

**问：如何获得 Aspose.Zip 的支持？** 

答：如有任何疑问或需要帮助，请访问[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)。

**问：Aspose.Zip 是否提供临时许可证？**

答：是的，您可以从[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**问：在哪里可以购买适用于 .NET 的 Aspose.Zip？**

答：您可以从[此处](https://purchase.aspose.com/buy)购买适用于 .NET 的 Aspose.Zip。

**问：我可以从 Xar 归档文件中仅提取特定文件吗？**

答：可以——使用 `archive.Entries` 枚举项目，并对选定的条目调用 `ExtractToFile`。

**问：该库是否支持受密码保护的 Xar 文件？**

答：目前，Xar 归档文件不支持加密；如果您遇到受保护的文件，则需要先对其进行解密，然后再使用 Aspose.Zip。

---

**上次更新时间：** 2026-02-28
**测试版本：** Aspose.Zip 24.11 for .NET
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}