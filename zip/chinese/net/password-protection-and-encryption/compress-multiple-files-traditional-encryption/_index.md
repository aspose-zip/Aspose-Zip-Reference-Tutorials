---
date: 2025-12-20
description: 学习如何使用 Aspose.Zip for .NET 通过传统加密对 ZIP 存档进行密码保护。本指南展示了如何加密 ZIP 文件并高效地向
  ZIP 添加文件。
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip .NET 对 Zip 档案进行密码保护
url: /zh/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip .NET 对 Zip 存档进行密码保护

## 介绍

欢迎阅读本分步教程，了解 **如何使用 Aspose.Zip for .NET 对 zip 存档文件进行密码保护**（传统加密）。Aspose.Zip 是一款强大的库，可让开发者轻松创建、读取和操作 zip 存档。在本指南中，我们将演示如何压缩多个文件、将它们添加到 zip 中，并使用密码保护存档，同时保持代码简洁易维护。

## 快速答案
- **“password protect zip archive” 是什么意思？** 即对 zip 文件进行加密，只有提供正确密码后才能打开其内容。  
- **在 .NET 中使用哪个库实现？** Aspose.Zip for .NET 内置对传统加密的支持。  
- **生产环境需要许可证吗？** 是的，生产使用需购买商业许可证；提供免费试用版。  
- **可以在 Linux 上运行吗？** 完全可以——Aspose.Zip 跨平台，支持 Windows、Linux 和 macOS。  
- **可以添加多少文件？** 任意数量；示例中展示了三个文件，实际可扩展。

## 什么是 “password protect zip archive”？

密码保护的 zip 存档使用加密（此处为传统 PKZIP 加密）来对存档内部的文件数据进行混淆。用户在解压时必须提供正确的密码才能解密内容。

## 为什么使用 Aspose.Zip 完成此任务？

- **简洁的 API** – 一行代码即可启用加密。  
- **无外部依赖** – 纯 .NET 实现，无需本机 DLL。  
- **跨平台** – 支持 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **性能优化** – 高效处理大文件。

## 前置条件

在开始之前，请确保具备以下条件：

- **Aspose.Zip for .NET** – 可从官方站点 [here](https://releases.aspose.com/zip/net/) 下载。  
- **包含文件的文件夹** – 将示例代码中的 `"Your Document Directory"` 替换为实际存放待压缩文件的路径。

## 导入命名空间

首先导入所需的命名空间，以便使用 Aspose.Zip 类：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 使用传统加密对 zip 进行加密

### 步骤 1：设置 Zip 文件（Password Protect Zip Archive）

创建 zip 文件并配置传统加密设置。密码 `"p@s$"` 仅为示例——实际项目请使用强密码替换。

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### 向 zip 存档添加文件

现在，将每个需要包含的文件加入。`CreateEntry` 方法接受 zip 内的文件名以及指向实际文件数据的流（`source1`、`source2`、`source3`）。

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### 保存 Zip 文件（使用密码压缩文件）

最后，将存档持久化到磁盘。此步骤会将加密后的 zip 文件写入前面指定的位置。

```csharp
archive.Save(zipFile);
```

> **专业提示：** 始终使用 `using` 语句关闭流，以及时释放文件句柄，尤其在处理大文件时。

## 常见问题及解决方案

| 问题 | 原因 | 解决办法 |
|------|------|----------|
| **Incorrect password error** | 密码不匹配或在 `TraditionalEncryptionSettings` 中出现拼写错误 | 核对密码字符串，确保解压时使用相同密码。 |
| **File not added** | 源流 (`sourceX`) 为 null 或已被释放 | 在传递给 `CreateEntry` 前使用 `File.OpenRead` 打开源流。 |
| **Performance slowdown on large files** | 使用默认压缩级别处理大量大文件 | 考虑在 `ArchiveEntrySettings` 中设置 `CompressionLevel` 以提升处理速度。 |

## 常见问答

**Q: 可以在 Windows 和 Linux 环境下使用吗？**  
A: 可以，Aspose.Zip for .NET 完全跨平台，支持 Windows、Linux 和 macOS。

**Q: 有免费试用吗？**  
A: 当然，您可以在此处 [here](https://releases.aspose.com/) 体验 Aspose.Zip for .NET 的免费试用。

**Q: 如果遇到问题，在哪里获取支持？**  
A: 请访问官方的 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区帮助和官方支持。

**Q: 临时许可证可以用于评估吗？**  
A: 可以，您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 完整的 API 文档在哪里？**  
A: 详细的参考资料请访问 [here](https://reference.aspose.com/zip/net/)。

---

**最后更新：** 2025-12-20  
**测试环境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}