---
date: 2026-05-05
description: 学习如何使用 Aspose.Zip for .NET 对文件进行密码压缩并加密 ZIP 档案，涵盖 7z 密码保护以及 C# 中的单文件
  zip 密码。
keywords:
- compress files with password
- how to encrypt zip
- aes 256 zip encryption
- encrypt zip entries
- per file zip password
linktitle: 不同密码的条目
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 对文件进行密码压缩并对 ZIP 条目使用不同密码进行加密
url: /zh/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 对文件进行密码压缩并使用不同密码加密 ZIP 条目

## 介绍

如果您需要**使用密码压缩文件**并为每个条目分配独立的密码，您来对地方了。在本教程中，我们将逐步演示如何使用 Aspose.Zip for .NET 库创建一个 7‑zip 存档，使每个文件都受到唯一密码的保护。完成后，您将了解每条目加密的重要性、如何进行设置以及如何在自己的项目中验证结果。

## 快速回答
- **“encrypt zip” 是什么意思？** 它指对 ZIP/7z 存档的内容应用基于密码的保护（AES 或 ZipCrypto）。  
- **每个条目可以有不同的密码吗？** 可以——Aspose.Zip 允许为每个文件分配不同的密码。  
- **支持哪些 .NET 版本？** 所有现代的 .NET Framework、.NET Core 以及 .NET 5/6 版本。  
- **生产环境需要许可证吗？** 生产使用需要商业许可证；提供免费试用版。  
- **示例中使用的压缩格式是什么？** 示例创建了一个使用 AES‑256 加密的 7z 存档。

## 什么是使用 Aspose.Zip 加密 zip？
对 ZIP（或 7z）文件进行加密意味着对其条目进行保护，使其在没有正确密码的情况下无法打开。Aspose.Zip for .NET 支持传统的 ZipCrypto 和更强大的 AES 加密，并且允许您为每个条目指定加密设置，从而实现细粒度的安全控制。

## 为什么要使用密码压缩文件？
- **安全分段：** 如果一个密码被泄露，其他文件仍然受到保护。  
- **合规要求：** 某些行业要求对不同数据类别使用独立凭证。  
- **面向用户的分发：** 单个存档可以发送给多个用户，每个用户只能解锁其被授权查看的文件。

## 为什么使用 AES 256 zip 加密？
AES‑256 是当前业界标准的强对称加密。相较于 ZipCrypto，它能够抵御现代的暴力破解攻击，并且与 7‑Zip 及其他现代解压工具完全兼容。当您需要 **aes 256 zip 加密** 时，Aspose.Zip 能够简化配置过程。

## 前置条件

在开始之前，请确保您已具备以下条件：

- 已安装 **Aspose.Zip for .NET** —— 请参阅官方[文档](https://reference.aspose.com/zip/net/)获取下载和安装说明。  
- 在机器上创建一个文件夹，用于存放源文件（即“文档目录”）。  
- 对 C# 和 Visual Studio（或您偏好的 .NET IDE）有基本了解。

## 导入命名空间

我们首先引入包含所需类的命名空间。

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步骤 1：设置文档目录

定义保存待归档文件的路径。

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：使用不同密码创建条目

以下是本教程的核心。我们打开一个新的 7z 文件，创建三个 `FileInfo` 对象，并为每个对象以各自的 AES 密码添加为条目。

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### 工作原理

- `SevenZipArchive` 是 7‑z 存档的容器。  
- `CreateEntry` 接受条目名称、源文件、覆盖标志以及 `SevenZipEntrySettings` 对象。  
- 在 `SevenZipEntrySettings` 中，我们提供两个设置对象：一个用于压缩（`SevenZipStoreCompressionSettings`），一个用于加密（`SevenZipAESEncryptionSettings`）。  
- 每次调用都提供一个**不同的密码**（`"test1"`、`"test2"`、`"test3"`），实现每条目保护。

## 步骤 3：验证

存档保存后，您可以输出一条简单的确认信息。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

运行程序后，使用 7‑Zip 等工具尝试打开 `archive.7z`。它会为每个条目提示输入密码，从而确认密码确实各不相同。

## 使用每文件 zip 密码加密 zip 条目 – 最佳实践

在使用每文件密码**加密 zip 条目**时，请注意以下建议：

1. **使用强且唯一的密码**——避免使用常见词汇和重复使用。  
2. **安全存储密码**——如果需要分发密码，考虑使用密码管理器或安全保险库。  
3. **使用多种工具测试**——确保 7‑Zip 和 WinRAR 都能读取该存档，因为某些旧工具可能不支持 AES‑256。  
4. **记录密码‑文件映射**——使用简单的 CSV（文件,密码）可帮助管理员追踪每个密码对应的条目。

## Zip 存档密码保护 – 常见陷阱

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **密码错误** | 密码字符串包含多余的空格或不可见字符。 | 修剪密码字符串（`new SevenZipAESEncryptionSettings(password.Trim())`）。 |
| **旧工具无法打开存档** | 某些旧版 ZIP 工具不支持 7z 使用的 AES‑256 加密。 | 使用现代解压工具（7‑Zip 19.00+）。 |
| **文件未添加到存档** | 源文件路径错误或文件不存在。 | 检查 `dataDir` 和文件名，或使用 `Path.Combine(dataDir, "data1.bin")`。 |

## 常见问题

### 问题 1：Aspose.Zip for .NET 是否兼容所有 .NET 版本？

A1: 是的，Aspose.Zip for .NET 旨在无缝集成到所有 .NET 框架版本中。

### 问题 2：我可以在商业项目中使用 Aspose.Zip for .NET 吗？

A2: 当然可以！Aspose.Zip for .NET 提供商业许可证，您可以在[此处](https://purchase.aspose.com/buy)了解购买详情。

### 问题 3：是否提供免费试用？

A3: 是的，您可以通过免费试用来体验 Aspose.Zip for .NET 的功能。请在[此处](https://releases.aspose.com/)开始。

### 问题 4：如何获取 Aspose.Zip for .NET 的支持？

A4: 如有任何疑问或需要帮助，请访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)。

### 问题 5：我可以在没有永久许可证的情况下使用 Aspose.Zip for .NET 吗？

A5: 是的，您可以获取临时许可证以满足短期需求。更多详情请参阅[此处](https://purchase.aspose.com/temporary-license/)。

## 结论

您刚刚学习了使用 Aspose.Zip for .NET **使用密码压缩文件**并对 ZIP 存档进行每条目密码加密的方式。此技术让您能够灵活地单独保护每个文件，满足更严格的安全要求并简化面向用户的分发。欢迎尝试其他压缩设置、更大的文件集，或将此逻辑集成到能够实时生成安全存档的 Web 服务中。

---

**最后更新：** 2026-05-05  
**测试环境：** Aspose.Zip for .NET 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}