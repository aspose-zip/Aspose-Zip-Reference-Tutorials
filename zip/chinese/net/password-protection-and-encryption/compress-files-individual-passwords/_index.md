---
date: 2025-12-20
description: 了解如何使用 Aspose.Zip 在 .NET 中创建受密码保护的 zip 压缩文件。本分步指南展示了如何使用密码压缩文件、设置 zip
  条目的密码以及使用 AES 加密。
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 在 .NET 中创建受密码保护的 ZIP 文件
url: /zh/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 创建受密码保护的 ZIP 文件

## Introduction

如果您需要在 .NET 应用程序中创建受密码保护的 zip 存档，Aspose.Zip 让这变得简单。通过为每个条目分配唯一密码，您可以在保持 ZIP 压缩便利性的同时保护敏感文档安全。在本教程中，您将学习如何使用单独密码压缩文件、选择不同的加密方法以及设置 zip 条目密码——全部使用清晰、可用于生产的代码。

## Quick Answers
- **我应该使用哪个库？** Aspose.Zip for .NET.
- **我可以为每个文件分配不同的密码吗？** 是的，每个条目都可以有自己的密码。
- **支持哪些加密算法？** 传统的 ZipCrypto、AES‑128 和 AES‑256。
- **开发需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。
- **这与 .NET 6+ 兼容吗？** 完全兼容——API 面向 .NET Standard 2.0 及更高版本。

## What is “create password protected zip”?

创建受密码保护的 zip 意味着对 ZIP 存档中的一个或多个条目添加加密，使得没有正确密码无法打开内容。这非常适合传输机密文件、存储备份或遵守数据保护政策。

## Why use Aspose.Zip for password‑protected archives?

- **细粒度控制** – 为每个文件设置不同的密码。
- **多种加密选项** – 从传统 ZipCrypto 到强大的 AES‑128/256。
- **无外部依赖** – 纯 .NET 库，易于集成。
- **完整文档** – 包含 **aspose zip tutorial**，适用于更深入的场景。

## Prerequisites

在开始教程之前，请确保您具备以下前提条件：

- Aspose.Zip for .NET：确保在您的 .NET 项目中安装了 Aspose.Zip 库。您可以在[此处](https://reference.aspose.com/zip/net/)找到所需文档。
- 下载：如果尚未下载，请从[此链接](https://releases.aspose.com/zip/net/)获取 Aspose.Zip for .NET 库。
- 文档目录：准备一个包含您要压缩的文件的目录。

## Import Namespaces

在您的 .NET 项目中，请确保导入必要的命名空间：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Step 1: Set the Resource Directory Path

定义资源目录的路径，该目录存放您的源文件。

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Compress Files with Individual Passwords

现在，让我们使用单独的密码压缩文件。我们将使用三个示例文件（`alice29.txt`、`asyoulik.txt` 和 `fields.c`），为每个文件设置不同的密码。这演示了如何 **使用密码压缩文件**，以及如何使用不同的加密方案 **设置 zip 条目密码**，包括 **使用 aes 的 zip 存档**。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### How this works
- **TraditionalEncryptionSettings** 使用较旧的 ZipCrypto 算法（兼容大多数 ZIP 工具）。
- **AesEcryptionSettings** 允许您选择 AES‑128 或 AES‑256，以获得更强的安全性。
- 每个 `CreateEntry` 调用都会接收一个 `ArchiveEntrySettings` 对象，在其中我们指定压缩方法和加密设置，从而有效地 **对 zip 存档条目进行密码保护**。

## Common Issues and Solutions

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| 打开 ZIP 时出现“Invalid password” | 代码中使用的密码与解压时输入的密码不匹配 | 检查传递给 `TraditionalEncryptionSettings` 或 `AesEcryptionSettings` 的密码字符串是否完全一致。 |
| 旧的解压工具无法打开 AES 加密的条目 | 并非所有 ZIP 工具都支持 AES 加密 | 使用传统的 ZipCrypto 方法以获得最大兼容性，或建议用户使用现代工具（例如 7‑Zip）。 |
| 大文件导致 `OutOfMemoryException` | 在压缩前将巨大的文件加载到内存 | 直接使用 `FileStream` 流式读取文件，而不是将整个文件加载到 `FileInfo` 对象中。 |

## Frequently Asked Questions (FAQs)

### Can I use different encryption methods for each file?
是的，Aspose.Zip for .NET 允许在压缩期间为每个文件使用不同的加密方法。

### Is there a trial version available?
是的，您可以在[此处](https://releases.aspose.com/)获取 Aspose.Zip for .NET 的免费试用版。

### How can I get support if I encounter issues?
访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区和 Aspose 支持的帮助。

### Where can I find detailed documentation for Aspose.Zip for .NET?
文档可在[此处](https://reference.aspose.com/zip/net/)查看。

### Can I purchase a temporary license for testing purposes?
是的，您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

## Additional Quick FAQ

**问：该库是否支持 .NET Core 和 .NET 5/6？**  
答：是的，Aspose.Zip 以 .NET Standard 为目标，可兼容 .NET Framework、.NET Core 和 .NET 5/6。

**问：我可以为每个 ZIP 条目添加注释吗？**  
答：虽然 Aspose.Zip 主要关注压缩和加密，但您可以在存档内的单独清单文件中存放元数据。

**问：是否可以使用单一密码加密整个存档？**  
答：您可以像示例中那样为每个条目单独设置密码，或对所有条目使用相同密码，以实现更简易的 “使用 aes 的 zip 存档”。

## Conclusion

您现在已经掌握了如何使用 Aspose.Zip 在 .NET 中 **创建受密码保护的 zip** 文件。通过为每个条目分配单独密码并选择合适的加密方法，您可以在不牺牲 ZIP 压缩便利性的前提下确保数据安全。探索 Aspose.Zip 的其他功能，如流式处理大文件、添加自定义元数据以及与云存储集成，以实现更强大的场景。

---

**最后更新：** 2025-12-20  
**测试环境：** Aspose.Zip for .NET 23.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}