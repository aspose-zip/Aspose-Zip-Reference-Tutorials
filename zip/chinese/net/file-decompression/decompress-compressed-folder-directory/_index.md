---
date: 2026-06-04
description: 了解如何使用 Aspose.Zip for .NET 将 zip 解压到文件夹，包括受密码保护的存档和加密 zip 的提取。
keywords:
- extract zip to folder
- how to unzip zip
- extract zip with password
- unzip files in c#
- read zip archive c#
linktitle: 解压 zip 到文件夹
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  headline: How to extract zip to folder with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  name: How to extract zip to folder with Aspose.Zip for .NET
  steps:
  - name: Open the ZIP file (or encrypted archive)
    text: The `FileStream` class provides a read‑only stream to the physical ZIP file
      on disk. Using a stream lets Aspose.Zip work with files located on network shares
      or embedded resources without first copying them to a temporary location.
  - name: Create an `Archive` instance (provide password when needed)
    text: The `Archive` class is the core object that represents a ZIP archive in
      memory. `ArchiveLoadOptions` defines settings used when loading an archive,
      such as the decryption password. Passing an `ArchiveLoadOptions` object with
      the `DecryptionPassword` property enables decryption of AES‑encrypted entri
  - name: Extract the contents to a destination folder
    text: '`ExtractToDirectory` iterates over every entry in the archive and writes
      it to the target path, preserving the original folder hierarchy. The method
      creates missing directories automatically and can also filter entries if you
      only need a subset. > **Pro tip:** If you only need to extract a subset of'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET supports ZIP, GZIP, and several other common
      formats.
    question: Does Aspose.Zip support other compression formats like GZIP?
  - answer: Absolutely. A valid license is required for production, but you can use
      the free trial for evaluation.
    question: Can I use Aspose.Zip in both commercial and non‑commercial projects?
  - answer: You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: How do I get a temporary license for testing?
  - answer: Visit the Aspose.Zip trial page [here](https://releases.aspose.com/) to
      download the latest version.
    question: Where can I download a free trial of Aspose.Zip?
  - answer: 'The Aspose.Zip community forum is a great place to get assistance: [support
      forum](https://forum.aspose.com/c/zip/37).'
    question: Where can I ask for help if I run into issues?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 将 zip 解压到文件夹的方法
url: /zh/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 将 zip 解压到文件夹

## 介绍

如果您需要在 .NET 应用程序中快速且可靠地 **extract zip to folder**，Aspose.Zip for .NET 为您提供了一个简洁、跨平台的 API，能够同等处理普通和加密的归档文件。在本教程中，我们将逐步演示您需要的全部内容——从库的设置到解压受密码保护的 ZIP 文件——让您专注于业务逻辑，而无需处理底层归档操作。

## 快速解答
- **Aspose.Zip 的主要用途是什么？** 在 .NET 应用程序中创建、读取并 **extract zip to folder**。  
- **如何使用密码解压 zip？** 通过 `ArchiveLoadOptions.DecryptionPassword` 传递密码。  
- **我可以在没有密码的情况下解压加密归档吗？** 不可以——Aspose.Zip 需要正确的密码才能打开加密归档。  
- **支持哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 和 .NET 5–10。  
- **生产环境是否需要许可证？** 是的，商业使用需要有效的 Aspose.Zip 许可证。

## 什么是 **extract zip to folder**？

解压 ZIP 文件意味着读取压缩数据并将原始文件写入磁盘上的目标目录。Aspose.Zip 抽象了底层细节，使您只需调用一个方法即可完成整个操作，同时支持 **30+ archive formats**，并能处理高达 **2 GB** 的文件，而无需将整个归档加载到内存中。

## 为什么在 **how to unzip zip** 任务中使用 Aspose.Zip？

Aspose.Zip 提供了简洁的 API，使您只需几行代码即可解压文件，支持密码保护和 AES 加密的归档，并可在 Windows、Linux 和 macOS 上运行。它在普通服务器上能够在 **500‑page ZIP archives in under 2 seconds**，消除对本机 zip 工具的需求，降低部署复杂度。

## 前置条件

- Aspose.Zip for .NET 库：从 [Aspose.Zip for .NET documentation](https://reference.aspose.com/zip/net/) 下载并安装库。  
- 一个 .NET 开发环境（Visual Studio、VS Code 或您喜欢的任何 IDE）。  
- （可选）一个密码保护的 ZIP 文件，如果您想尝试 **extract zip with password**。

## 导入命名空间

在您的 .NET 项目中，导入必要的命名空间以利用 Aspose.Zip 的功能：

```csharp
using Aspose.Zip;
using System.IO;
```

现在让我们逐步分解解压过程。

## 如何 **extract zip to folder** – 步骤指南

加载您的 ZIP 归档，可选地提供解密密码，然后调用 `ExtractToDirectory` —— 这就是完整的解压工作流，分为三个简洁步骤。API 会在目标文件夹不存在时自动创建，并将条目流式写入磁盘，以保持低内存使用，即使是多 GB 的归档也能处理。

### 步骤 1：打开 ZIP 文件（或加密归档）

`FileStream` 类提供对磁盘上物理 ZIP 文件的只读流。使用流可以让 Aspose.Zip 直接处理位于网络共享或嵌入资源中的文件，而无需先将其复制到临时位置。

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

### 步骤 2：创建 `Archive` 实例（需要时提供密码）

`Archive` 类是内存中表示 ZIP 归档的核心对象。`ArchiveLoadOptions` 定义了加载归档时使用的设置，例如解密密码。传入带有 `DecryptionPassword` 属性的 `ArchiveLoadOptions` 对象即可启用对 AES 加密条目的解密。

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

### 步骤 3：将内容提取到目标文件夹

`ExtractToDirectory` 会遍历归档中的每个条目并写入目标路径，保留原始文件夹层次结构。该方法会自动创建缺失的目录，并且如果只需要部分文件，还可以过滤条目。

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

> **技巧提示：** 如果只需要提取部分文件，请使用接受过滤委托的重载，而不是提取全部。

## 常见问题与故障排除

- **密码错误** – Aspose.Zip 抛出身份验证异常。请再次检查密码字符串，或从配置源安全获取。  
- **目标路径未找到** – 确保目标目录路径有效；`ExtractToDirectory` 会创建缺失的文件夹，但父路径必须可访问。  
- **大归档** – 对于非常大的 ZIP 文件，考虑使用流式 API 逐条提取，以保持低内存使用。  

## 常见问答

**问：Aspose.Zip 是否支持其他压缩格式，如 GZIP？**  
答：是的，Aspose.Zip for .NET 支持 ZIP、GZIP 以及其他多种常见格式。

**问：我可以在商业和非商业项目中使用 Aspose.Zip 吗？**  
答：当然可以。生产环境需要有效许可证，但您可以使用免费试用版进行评估。

**问：如何获取用于测试的临时许可证？**  
答：您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取用于测试的临时许可证。

**问：在哪里可以下载 Aspose.Zip 的免费试用版？**  
答：请访问 Aspose.Zip 试用页面 [here](https://releases.aspose.com/) 下载最新版本。

**问：如果遇到问题，我可以在哪里寻求帮助？**  
答：Aspose.Zip 社区论坛是获取帮助的好地方：[support forum](https://forum.aspose.com/c/zip/37)。

---

**最后更新：** 2026-06-04  
**测试环境：** Aspose.Zip for .NET（最新版本）  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Zip for .NET 提取带密码的 Zip](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [如何使用 Aspose.Zip for .NET 将 WIM 提取到文件夹](/zip/net/file-decompression/decompress-wim-folder/)
- [如何使用 Aspose.Zip for .NET 解压文件](/zip/net/file-decompression/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}