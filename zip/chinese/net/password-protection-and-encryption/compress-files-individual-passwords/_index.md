---
date: 2026-03-02
description: 了解如何使用 Aspose.Zip 在 .NET 中创建受密码保护的 ZIP 存档并使用密码压缩文件。请按照我们的分步指南操作。
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip 在 .NET 中创建受密码保护的 ZIP 档案
url: /zh/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 创建受密码保护的 ZIP 档案

## 介绍

当您需要共享敏感数据时，**受密码保护的 zip 档案** 是一种最简单且最有效的保护信息的方式之一。在 .NET 应用程序中，Aspose.Zip 可以轻松实现 **带密码的文件压缩**，为每个文件分配独立的加密密钥。在本教程中，您将学习如何创建此类档案、其重要性以及在实际项目中的应用场景。

## 快速答案
- **应该使用哪个库？** Aspose.Zip for .NET 提供对每个文件密码和多种加密方式的内置支持。  
- **代码行数多少？** 大约 30 行，包括设置和保存档案的代码。  
- **每个文件可以使用不同的密码吗？** 可以——您可以为每个条目分配唯一密码。  
- **有哪些加密方法可用？** 传统的 ZipCrypto、AES‑128 和 AES‑256。  
- **生产环境需要许可证吗？** 生产使用需要商业许可证；提供免费试用版。

## 什么是受密码保护的 zip 档案？
受密码保护的 zip 档案是一种压缩文件（ZIP），需要密码才能解压其内容。密码可以保护整个档案或单独的条目，现代算法如 AES‑128/256 提供强大的加密能力。

## 为什么要使用 Aspose.Zip 对文件进行密码压缩？
- **细粒度安全** – 为每个文件分配不同密码，适用于多租户场景。  
- **多种加密标准** – 可在传统 ZipCrypto 与强大的 AES 之间选择。  
- **无需外部工具** – 所有操作均在 .NET 代码中以编程方式完成。  
- **性能** – 使用 Deflate 进行快速压缩，同时保持档案体积小。

## 前置条件

在开始之前，请确保您已具备：

- **Aspose.Zip for .NET** – 在项目中安装该库。详细文档请参阅[此处](https://reference.aspose.com/zip/net/)。  
- **下载最新的包**（如果尚未下载），请前往[此链接](https://releases.aspose.com/zip/net/)。  
- 包含待压缩文件的文件夹。

## 导入命名空间

在 C# 文件顶部添加所需的命名空间：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 步骤 1：设置资源目录路径

将代码指向保存源文件的文件夹：

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：使用单独密码压缩文件

现在我们将创建一个 **受密码保护的 zip 档案**，每个文件使用各自的密码和加密方式。示例使用三个示例文件（`alice29.txt`、`asyoulik.txt` 和 `fields.c`），并为它们设置不同的密码。

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

### 工作原理
- **CreateEntry** 将文件添加到档案中。  
- 第四个参数（`ArchiveEntrySettings`）允许您同时指定压缩（`DeflateCompressionSettings`）和加密（`TraditionalEncryptionSettings` 或 `AesEcryptionSettings`）。  
- 为每个条目传入不同的密码字符串，即可得到一个 **受密码保护的 zip 档案**，每个文件只能使用对应的密钥解锁。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| 解压时出现 “Wrong password” 错误 | 密码不匹配或使用了错误的加密方式 | 核对准确的密码字符串，并确保在解压时使用相同的 `EncryptionMethod`。 |
| 档案大小大于预期 | 在小文本文件上使用 AES‑256 会增加开销 | 对于小文件，使用 AES‑128 可能已足够且可生成更小的档案。 |
| `archive.Save` 运行时抛出异常 | 目标文件夹没有写入权限 | 确保应用程序对 `dataDir` 具有写入权限，或使用其他输出路径。 |

## 常见问答 (FAQs)

### 我可以为每个文件使用不同的加密方法吗？
可以，Aspose.Zip for .NET 允许在每个文件上混合使用传统 ZipCrypto、AES‑128 和 AES‑256 加密方式。

### 是否提供试用版本？
提供，您可以在此处获取 Aspose.Zip for .NET 的免费试用版[这里](https://releases.aspose.com/)。  

### 如果遇到问题，如何获取支持？
访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区和 Aspose 官方的帮助。

### 在哪里可以找到 Aspose.Zip for .NET 的详细文档？
文档可在[此处](https://reference.aspose.com/zip/net/)查阅。

### 我可以购买临时许可证用于测试吗？
可以，您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-03-02  
**测试环境：** Aspose.Zip for .NET（最新发布）  
**作者：** Aspose  

---