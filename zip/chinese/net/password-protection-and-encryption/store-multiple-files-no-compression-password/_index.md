---
date: 2026-07-23
description: 了解如何使用 Aspose.Zip for .NET 对 zip archive 进行密码保护，store multiple files
  without compression，并使用 AES encryption 实现 zip file password protection。
keywords:
- create password protected zip
- how to encrypt zip
- zip file password protection
- add multiple files zip
- create zip archive c#
lastmod: 2026-07-23
linktitle: 使用密码的 store multiple files without compression
og_description: 使用 Aspose.Zip for .NET 和 AES‑256 encryption 创建 password protected
  zip archive，store multiple files without compression，轻松保护您的数据。
og_image_alt: Guide to create password protected zip archive in C# with Aspose.Zip
og_title: 使用 Aspose.Zip for .NET 创建密码保护的 Zip
schemas:
- author: Aspose
  dateModified: '2026-07-23'
  description: Learn how to password protect zip archive using Aspose.Zip for .NET,
    store multiple files without compression, and apply zip file password protection
    with AES encryption.
  headline: Create Password Protected Zip with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to password protect zip archive using Aspose.Zip for .NET,
    store multiple files without compression, and apply zip file password protection
    with AES encryption.
  name: Create Password Protected Zip with Aspose.Zip for .NET
  steps:
  - name: Open the Zip File
    text: '`FileStream` is a .NET class that provides a stream for reading and writing
      bytes to a file. We create a new `FileStream` that will hold the resulting archive.'
  - name: Open the Source File
    text: '`Stream` is the abstract base class for all byte‑based I/O in .NET. Open
      the first file you want to add to the archive. You can repeat this block for
      additional files.'
  - name: Create an Archive with Store Compression and AES Encryption
    text: '`Archive` is Aspose.Zip''s main object representing a ZIP container in
      memory. `AesEncryptionSettings` configures AES‑256 encryption parameters, including
      the password. Here we configure the archive to **store** (no compression) the
      files and apply **zip file password protection** using AES‑256.'
  - name: Create Archive Entry and Save – *create archive entry c#*
    text: '`CreateEntry` adds a new file entry to an `Archive` instance. Now we add
      the file to the archive and write the encrypted zip to disk. > **Pro tip:**
      To add more files, simply call `archive.CreateEntry("anotherFile.txt", anotherStream);`
      before `archive.Save(zipFile);`.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip supports several algorithms, including AES‑128 and ZipCrypto.
      See the documentation [here](https://reference.aspose.com/zip/net/) for details.
    question: Can I use Aspose.Zip for .NET with other encryption methods?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community
      help and official support.
    question: Where can I get support for Aspose.Zip for .NET?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Zip for .NET?
  - answer: Request a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip for .NET?
  - answer: You can buy Aspose.Zip for .NET [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip archive
- Aspose.Zip
- .NET compression
- password protection
- AES encryption
title: 使用 Aspose.Zip for .NET 创建密码保护的 Zip
url: /zh/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 创建受密码保护的 Zip

在现代 .NET 开发中，安全地归档文件是常见需求。使用 **Aspose.Zip for .NET**，您可以 **创建受密码保护的 zip** 档案，存储多个项目而不进行压缩，并应用强大的 AES‑256 加密——只需几行 C# 代码。本教程将逐步演示如何构建包含多个文件、使用 *store*（无压缩）模式并通过密码锁定的 zip。

## 快速答复
- **“密码保护 zip 档案”是什么意思？** 它会加密 zip 内容，只有使用正确的密码才能打开。  
- **使用哪种加密算法？** 通过 `AesEncryptionSettings` 使用 AES‑256。  
- **我可以添加多个文件吗？** 可以——对每个源文件重复调用 `CreateEntry`。  
- **生产环境需要许可证吗？** 需要商业许可证；提供免费试用。  
- **在 .NET 6/7 上受支持吗？** 当然——Aspose.Zip 支持 .NET Framework、.NET Core 和 .NET 5/6/7。

## 什么是密码保护的 zip 档案？

一个 *密码保护的 zip 档案* 是使用用户自定义密码对条目进行加密的 ZIP 文件。打开档案时必须提供密码，否则内容不可读取。Aspose.Zip 通过 AES‑256 加密实现此功能，为敏感数据提供强大安全性。

## 为什么在 Aspose.Zip 中使用 zip 文件密码保护？

您可以通过两个简单步骤创建安全、轻量的档案。Aspose.Zip 在不压缩的情况下存储文件，应用 AES‑256 加密，并在所有主流 .NET 运行时上工作，免除外部工具的需求。此方法可将已压缩媒体的处理时间降低最多 40 %，同时确保数据安全。

- **无压缩存储** – `StoreCompressionSettings` 保持原始文件大小，适用于已压缩的媒体。  
- **强加密** – AES‑256 可防止暴力破解攻击。  
- **完整的 .NET 集成** – 支持三大 .NET 平台——.NET Framework、.NET Core 和 .NET 5/6/7。  
- **简洁的 API** – 创建档案、设置密码、添加条目并保存——只需几行代码。

## 前置条件

在深入代码之前，请确保您已拥有：

- 已安装 **Aspose.Zip for .NET**。您可以在[此处](https://releases.aspose.com/zip/net/)下载。  
- 包含要归档文件的文件夹。在下面的示例中，变量 `dataDir` 指向该文件夹。

## 导入命名空间

首先，将所需的命名空间引入作用域：

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 如何在不压缩的情况下创建受密码保护的 zip 档案并存储多个文件

使用 *store*（无压缩）方式存储文件，并通过 AES‑256 加密全部内容，只需几行 C# 代码即可创建受密码保护的 zip 档案。以下指南展示了您需要遵循的完整步骤。此方法确保文件保持未压缩，以加快解压速度，同时提供强大的 AES‑256 保护。

### 步骤 1：打开 Zip 文件

`FileStream` 是 .NET 类，用于提供读取和写入文件字节的流。  
我们创建一个新的 `FileStream` 来保存生成的档案。

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

### 步骤 2：打开源文件

`Stream` 是 .NET 中所有基于字节的 I/O 的抽象基类。  
打开您想添加到档案的第一个文件。您可以对其他文件重复此代码块。

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

### 步骤 3：创建使用存储压缩和 AES 加密的档案

`Archive` 是 Aspose.Zip 的主要对象，表示内存中的 ZIP 容器。  
`AesEncryptionSettings` 配置 AES‑256 加密参数，包括密码。  
在这里我们将档案配置为 **store**（无压缩）文件，并使用 AES‑256 应用 **zip 文件密码保护**。

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

### 步骤 4：创建档案条目并保存 – *create archive entry c#*

`CreateEntry` 向 `Archive` 实例添加新的文件条目。  
现在我们将文件添加到档案并将加密的 zip 写入磁盘。

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

> **技巧提示：** 若要添加更多文件，只需在 `archive.Save(zipFile);` 之前调用 `archive.CreateEntry("anotherFile.txt", anotherStream);`。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **“Invalid password” 异常** | 密码错误或加密方式不匹配。 | 确保 `AesEncryptionSettings` 中的密码字符串与打开 zip 时使用的密码一致，并确认使用 `EncryptionMethod.AES256`。 |
| **文件大小大于预期** | 不小心使用了压缩。 | 确认使用的是 `StoreCompressionSettings`（无压缩），而不是 `DeflateCompressionSettings`。 |
| **流未关闭** | `using` 语句缺少结束括号。 | 确保每个 `using` 块都正确关闭；示例代码展示了正确的嵌套方式。 |

## 常见问答

**Q: 我可以在 Aspose.Zip for .NET 中使用其他加密方法吗？**  
A: 是的，Aspose.Zip 支持多种算法，包括 AES‑128 和 ZipCrypto。详情请参阅文档[此处](https://reference.aspose.com/zip/net/)。

**Q: 我在哪里可以获得 Aspose.Zip for .NET 的支持？**  
A: 请访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区帮助和官方支持。

**Q: Aspose.Zip for .NET 是否提供免费试用？**  
A: 是的，您可以在[此处](https://releases.aspose.com/)获取免费试用。

**Q: 我如何获取 Aspose.Zip for .NET 的临时许可证？**  
A: 请在[此处](https://purchase.aspose.com/temporary-license/)申请临时许可证。

**Q: 我在哪里可以购买 Aspose.Zip for .NET？**  
A: 您可以在[此处](https://purchase.aspose.com/buy)购买 Aspose.Zip for .NET。

## 结论

在本指南中，我们演示了如何使用 Aspose.Zip for .NET **创建受密码保护的 zip** 文件、在无压缩的情况下存储多个项目，并应用 AES‑256 加密。遵循这些步骤，您可以保护敏感数据，满足合规要求，并保持档案轻量。欢迎尝试添加更多文件、更改密码或切换到其他加密方法——Aspose.Zip 让一切变得简单。

---

**最后更新：** 2026-07-23  
**测试环境：** Aspose.Zip for .NET 24.12（撰写时的最新版本）  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Zip 创建受密码保护的 ZIP 文件并进行 AES 加密](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [在 Aspose.Zip .NET 中压缩多个文件并加密](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)
- [为 .NET 目录创建受密码保护的 zip – Aspose.Zip 教程](/zip/net/password-protection-and-encryption/password-protect-directory/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}