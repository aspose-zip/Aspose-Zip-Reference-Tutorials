---
date: 2026-05-15
description: 了解如何使用 Aspose.Zip for .NET 通过几个简单步骤创建受密码保护的 zip 文件并对文件进行密码压缩。
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: 使用单独密码压缩文件
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 在 .NET 中使用 Aspose.Zip 创建受密码保护的 ZIP
url: /zh/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Zip 创建受密码保护的 ZIP

## 介绍

在本教程中，您将学习如何使用 Aspose.Zip 在 .NET 应用程序中**创建受密码保护的 zip**文件。当需要传输机密数据或存储敏感文档而不让未授权人员访问时，安全压缩至关重要。

**Aspose.Zip** 是一个 .NET 库，可编程地创建、读取和加密 ZIP 存档。它支持 AES‑256 加密，并允许您为存档中的每个条目分配唯一密码。

## 快速答疑
- **Aspose.Zip 的作用是什么？** 它创建并操作 ZIP 存档，包括每文件的密码保护。  
- **我可以分配多少个密码？** 每个文件一个不同的密码；条目数量无限。  
- **使用哪种加密算法？** AES‑256，提供 256 位安全性。  
- **测试是否需要许可证？** 提供免费试用；生产环境需要许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 前提条件

在深入教程之前，请确保您具备以下前提条件：

- Aspose.Zip for .NET：确保在您的 .NET 项目中已安装 Aspose.Zip 库。您可以在[此处](https://reference.aspose.com/zip/net/)找到所需文档。
- 下载：如果尚未下载，请从[此链接](https://releases.aspose.com/zip/net/)获取 Aspose.Zip for .NET 库。
- 文档目录：准备一个包含您要压缩的文件的目录。

## 导入命名空间

在您的 .NET 项目中，请确保导入必要的命名空间：

`ZipFile` 是 Aspose.Zip 用于创建 ZIP 存档并为每个条目分配单独密码的主要类。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 如何在 .NET 中创建受密码保护的 zip 文件？

加载目标文件夹，实例化 `ZipFile` 对象，为每个文件添加各自的密码，最后调用 `Save` 写入存档。整个过程仅需几行代码，并确保每个条目使用您指定的密码进行加密。

### 步骤 1：设置资源目录路径

定义包含您文件的资源目录的路径。

```csharp
string dataDir = "Your Document Directory";
```

### 步骤 2：使用单独密码压缩文件

现在，让我们使用单独密码压缩文件。我们将使用三个示例文件（`alice29.txt`、`asyoulik.txt` 和 `fields.c`），为每个文件设置不同的密码。

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

## 为什么要对 ZIP 存档使用密码保护？

Aspose.Zip 支持 **30+ 种压缩算法**，并可使用 AES‑256 加密存档，提供高达 **256 位安全性**。它能够在不将整个文件加载到内存的情况下处理数百兆字节的存档，适用于高性能服务器端场景。此外，密码保护有助于满足 GDPR、HIPAA 等监管合规要求，确保敏感数据在静止和传输过程中均保持加密。

## 结论

恭喜！您已成功学习如何使用 Aspose.Zip for .NET **创建受密码保护的 zip** 文件以及 **使用密码压缩文件**。此功能为您的压缩文件增加了一层额外的安全性，确保机密性并符合数据保护政策的合规要求。

## 常见问题

**Q: 我可以为每个文件使用不同的加密方式吗？**  
A: 是的，Aspose.Zip 允许您在将文件添加到存档时为每个条目选择加密算法（例如 AES‑256）。

**Q: 是否提供试用版？**  
A: 是的，您可以在[此处](https://releases.aspose.com/)获取 Aspose.Zip for .NET 的免费试用。

**Q: 如果遇到问题，我该如何获取支持？**  
A: 请访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区和 Aspose 支持的帮助。

**Q: 在哪里可以找到 Aspose.Zip for .NET 的详细文档？**  
A: 文档可在[此处](https://reference.aspose.com/zip/net/)获取。

**Q: 我可以购买临时许可证用于测试吗？**  
A: 是的，您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

---

**最后更新：** 2026-05-15  
**测试使用：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Zip for .NET 创建受密码保护的 ZIP](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [使用 Aspose.Zip 通过 AES 加密保护 ZIP 文件](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [在 Aspose.Zip .NET 中加密压缩多个文件](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}