---
title: 使用 Aspose.Zip 在 .NET 中进行安全文件压缩
linktitle: 使用单独的密码压缩文件
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 了解如何增强 .NET 应用程序中的文件安全性！请按照我们的分步指南使用 Aspose.Zip for .NET 压缩具有单独密码的文件。
type: docs
weight: 16
url: /zh/net/password-protection-and-encryption/compress-files-individual-passwords/
---

## 介绍

在 .NET 开发领域，有效管理和压缩文件是一项至关重要的任务。 Aspose.Zip for .NET 提供了强大的文件压缩解决方案，提供各种功能来增强您的应用程序。一个显着的功能是能够使用单独的密码压缩文件，从而提供额外的安全层。在本教程中，我们将指导您完成使用 Aspose.Zip for .NET 压缩具有单独密码的文件的过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Zip for .NET：确保您的 .NET 项目中安装了 Aspose.Zip 库。您可以找到必要的文档[这里](https://reference.aspose.com/zip/net/).

- 下载：如果您还没有下载 Aspose.Zip for .NET 库，请从[这个链接](https://releases.aspose.com/zip/net/).

- 文档目录：准备一个包含要压缩的文件的目录。

## 导入命名空间

在您的 .NET 项目中，确保导入必要的命名空间：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 第1步：设置资源目录路径

定义文件所在资源目录的路径。

```csharp
string dataDir = "Your Document Directory";
```

## 第 2 步：使用单独的密码压缩文件

现在，让我们使用单独的密码来压缩文件。我们将使用三个示例文件（`alice29.txt`, `asyoulik.txt` ， 和`fields.c`）每个都有不同的密码。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        //使用单独的密码压缩每个文件
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        //保存压缩文件
        archive.Save(zipFile);
    }
}
```

## 结论

恭喜！您已成功学习如何使用 Aspose.Zip for .NET 来压缩具有单独密码的文件。此功能为您的压缩文件添加了额外的安全层，确保机密性。

## 常见问题 (FAQ)

### 我可以对每个文件使用不同的加密方法吗？
是的，Aspose.Zip for .NET 允许您在压缩过程中对每个文件使用不同的加密方法。

### 有试用版吗？
是的，您可以访问 Aspose.Zip for .NET 的免费试用版[这里](https://releases.aspose.com/).

### 如果遇到问题，我如何获得支持？
参观[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)寻求社区的帮助和 Aspose 支持。

### 在哪里可以找到 Aspose.Zip for .NET 的详细文档？
文档可用[这里](https://reference.aspose.com/zip/net/).

### 我可以购买临时许可证用于测试目的吗？
是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
