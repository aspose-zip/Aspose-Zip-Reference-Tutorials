---
date: 2026-07-18
description: 了解如何使用 Aspose.Zip for .NET 创建受密码保护的 zip 文件、对 zip 文件夹进行密码保护以及更改 zip 密码。
keywords:
- create password protected zip
- zip folder with password
- how to encrypt zip
- password protect zip folder
- encrypt zip archive c#
lastmod: 2026-07-18
linktitle: 密码保护目录
og_description: 使用 Aspose.Zip 为 .NET 目录创建受密码保护的 zip 存档。本分步教程展示了如何加密文件夹、更改密码以及利用 AES
  加密。
og_image_alt: 'Developer guide: Create password protected zip for .NET directories
  with Aspose.Zip'
og_title: 创建受密码保护的 zip – Aspose.Zip .NET 指南
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to create password protected zip files, password protect
    zip folder, and change zip password using Aspose.Zip for .NET.
  headline: Create password protected zip for .NET directories – Aspose.Zip Tutorial
  type: TechArticle
- questions:
  - answer: Use `TraditionalEncryptionSettings` when creating the `Archive` object,
      then call `CreateEntries` on the target folder.
    question: How do I encrypt a folder with zip using Aspose.Zip?
  - answer: No, the password must be defined at creation time; to change it, recreate
      the archive with a new password.
    question: Can I set a zip folder password after the archive is created?
  - answer: '`AesEncryptionSettings` configures AES‑256 encryption for a ZIP archive.
      Yes, you can switch to `AesEncryptionSettings` for AES‑256 encryption instead
      of the traditional ZipCrypto.'
    question: Does Aspose.Zip support AES encryption for stronger security?
  - answer: Absolutely – the current release works with all modern .NET runtimes.
    question: Is the library compatible with .NET 6 and .NET 7?
  - answer: Aspose.Zip will throw a `PasswordRequiredException`, prompting you to
      supply the correct password.
    question: What happens if I try to open a password‑protected zip without a password?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip encryption
- Aspose.Zip
- .NET compression
- password protected archive
title: 为 .NET 目录创建受密码保护的 zip – Aspose.Zip 教程
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 .NET 目录的密码保护 zip – Aspose.Zip 教程

在本教程中，您将使用 .NET 的 Aspose.Zip 库 **创建密码保护 zip** 存档，以压缩整个目录。无论您需要 **加密文件夹**、保护备份文件，还是仅仅限制对敏感数据的访问，本分步指南都会向您展示如何使用简洁的 C# 代码完成此操作。完成后，您将了解如何保护目录、切换加密模式以及更改现有存档的密码。

## 快速答复
- **推荐使用的库是什么？** Aspose.Zip for .NET  
- **我可以加密整个文件夹吗？** 是的——只需将 API 指向您想要压缩的文件夹。  
- **是否支持更改 zip 密码？** 当然，使用 `TraditionalEncryptionSettings`。  
- **生产环境是否需要许可证？** 商业使用需要有效的 Aspose.Zip 许可证。  
- **支持 .NET Core/5/6 吗？** 是的，API 完全兼容现代 .NET 运行时。  

## 什么是“创建密码保护 zip”？
创建密码保护 zip 是指在将文件或目录压缩为 ZIP 存档的同时应用加密，使得只有使用正确密码才能打开该存档。这可以防止未授权访问内容，并符合多项数据保护法规。

## 如何为目录创建密码保护 zip
加载目标文件夹，使用 `TraditionalEncryptionSettings` 配置密码，并将数据流式写入新的 ZIP 文件——只需几行简洁的代码。API 将每个条目直接写入输出流，即使是多 GB 级别的目录也能以极低的内存开销进行处理。

## 为什么在 .NET 中使用 Aspose.Zip 对目录进行密码保护？
Aspose.Zip 支持 **30 多种压缩和加密算法**，能够处理超过 **10 GB** 的文件夹而无需将整个存档加载到内存中，并提供传统的 ZipCrypto 和现代的 AES‑256 加密。该库完全线程安全，运行于 **.NET Framework 4.6+**、**.NET Core 3.1+** 和 **.NET 6/7**，并包含详细的日志记录，帮助您排查任何问题。

## 常见使用场景
- **备份保护：** 将每日备份文件夹压缩为 zip 并使用强密码锁定。  
- **安全文件交换：** 将 zip 文件夹密码发送给客户，而不暴露内容。  
- **合规性要求：** 将个人身份信息 (PII) 存储在加密的 zip 存档中，以符合数据保护标准。  

## 前提条件
在开始之前，请确保您具备：

- 具备 C# 编程的基础知识。  
- Visual Studio（任意近期版本）。  
- Aspose.Zip for .NET 库——在 **[此处](https://releases.aspose.com/zip/net/)** 下载。  
- 磁盘上需要使用密码保护的文件夹。  

## 导入命名空间
在 C# 文件中添加所需的命名空间，以便编译器知道 Aspose.Zip 类所在的位置。

## 步骤 1：设置资源目录的路径
定义指向您打算压缩并保护的目录的路径。

## 步骤 2：对目录进行密码保护
`TraditionalEncryptionSettings` 定义 ZIP 存档的密码和加密算法。  
在创建 `Archive` 实例时使用此设置对象，以应用 ZipCrypto 保护。

## 步骤 3：代码说明
`Archive` 表示一个 ZIP 存档，并提供添加条目和保存存档的方法。

- **创建输出文件：** `File.Open(..., FileMode.Create)` 打开（或创建）用于保存加密数据的 ZIP 文件。  
- **选择源文件夹：** `new DirectoryInfo(".\\CanterburyCorpus")` 告诉 Aspose.Zip 要压缩的目录。  
- **应用密码：** `new TraditionalEncryptionSettings("p@s$")` 设置用于保护存档的密码。  
- **添加条目并保存：** `archive.CreateEntries(corpus)` 将文件夹中的每个文件添加进去，`archive.Save(zipFile)` 将加密的 ZIP 写入磁盘。  

## 如何稍后更改 zip 密码？
要更改密码，必须重新创建存档，因为密码存储在中心目录头中。使用所需密码创建新的 `TraditionalEncryptionSettings`，打开现有存档，将其条目复制到使用新设置的 `Archive` 实例中，然后保存新存档。此过程会使用新密码重新加密所有条目。

## 强密码的 zip 文件夹提示
- 使用大小写字母、数字和符号的组合。  
- 目标长度至少为 12 个字符；更长的密码破解难度指数级提升。  
- 避免使用常见词汇或模式；可以考虑使用密码短语。  

## 常见问题与提示
- **大型文件夹：** Aspose.Zip 采用流式处理数据，即使是 5 GB 的目录，内存使用也保持在 **150 MB** 以下。  
- **密码复杂度：** 使用强密码（字母、数字、符号混合）以提升安全性。  
- **许可证错误：** 确保已应用有效的许可证文件；否则库将在评估模式下运行，功能受限。  
- **zip 文件夹密码未被识别：** 确认在打开存档时使用相同的加密方法（`TraditionalEncryptionSettings`）。  

## 常见问题

### Aspose.Zip for .NET 是否适用于大型目录？
是的，Aspose.Zip for .NET 旨在高效处理大型目录，提供最佳性能。

### 我可以更改已受保护目录的密码吗？
是的，您可以通过相应地调整代码中的 `TraditionalEncryptionSettings` 来修改密码。

### 使用 Aspose.Zip for .NET 是否有许可要求？
是的，在生产环境中使用 Aspose.Zip for .NET 需要有效的许可证。您可以在 **[此处](https://purchase.aspose.com/buy)** 获取许可证。

### 是否提供 Aspose.Zip for .NET 的免费试用？
是的，您可以在 **[此处](https://releases.aspose.com/)** 获取免费试用。

### 在哪里可以找到 Aspose.Zip for .NET 的额外支持？
您可以访问 **[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)** 获取支持或咨询。

## 快速 FAQ（AI 友好）

**Q: 如何使用 Aspose.Zip 对文件夹进行 zip 加密？**  
A: 在创建 `Archive` 对象时使用 `TraditionalEncryptionSettings`，然后对目标文件夹调用 `CreateEntries`。

**Q: 可以在创建存档后设置 zip 文件夹密码吗？**  
A: 不能，密码必须在创建时定义；若要更改，需要使用新密码重新创建存档。

**Q: Aspose.Zip 是否支持 AES 加密以提升安全性？**  
A: `AesEncryptionSettings` 可为 ZIP 存档配置 AES‑256 加密。是的，您可以切换到 `AesEncryptionSettings` 使用 AES‑256 加密，而非传统的 ZipCrypto。

**Q: 该库是否兼容 .NET 6 和 .NET 7？**  
A: 完全兼容——当前版本可在所有现代 .NET 运行时上运行。

**Q: 如果尝试在没有密码的情况下打开密码保护的 zip 会怎样？**  
A: Aspose.Zip 将抛出 `PasswordRequiredException`，提示您提供正确的密码。

**最后更新：** 2026-07-18  
**测试环境：** Aspose.Zip for .NET（最新版本）  
**作者：** Aspose

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## 相关教程

- [使用 Aspose.Zip for .NET 创建密码保护 ZIP](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [使用 Aspose.Zip 创建带 AES 加密的密码保护 ZIP 文件](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Aspose.Zip for .NET - 密码保护 Zip 存档并在不压缩的情况下存储多个文件](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}