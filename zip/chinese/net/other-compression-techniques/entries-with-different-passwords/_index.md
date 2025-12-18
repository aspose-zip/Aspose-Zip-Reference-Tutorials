---
date: 2025-12-18
description: 了解如何使用 Aspose.Zip for .NET 对 zip 文件进行不同密码的加密。本指南展示了如何使用密码压缩文件以及在 C# 中创建
  7z 压缩包。
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 Aspose.Zip for .NET 中使用不同密码加密 ZIP 文件
url: /zh/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 对 ZIP 文件进行不同密码加密

## 介绍

如果您需要 **如何加密 zip** 存档并为每个条目分配独立的密码，您来对地方了。在本教程中，我们将逐步演示如何使用 Aspose.Zip for .NET 创建一个 7‑zip 存档，使每个文件都使用唯一密码进行保护。完成后，您将了解为何每条目加密很重要、如何进行设置以及如何在自己的项目中验证结果。

## 快速答案
- **“encrypt zip” 是什么意思？** 它指对 ZIP/7z 存档的内容应用基于密码的保护（AES 或 ZipCrypto）。  
- **每个条目可以使用不同的密码吗？** 可以——Aspose.Zip 允许为每个文件分配不同的密码。  
- **支持哪些 .NET 版本？** 支持所有现代的 .NET Framework、.NET Core 以及 .NET 5/6 版本。  
- **生产环境需要许可证吗？** 生产使用需要商业许可证；提供免费试用版。  
- **示例使用的压缩格式是什么？** 示例创建了一个使用 AES‑256 加密的 7z 存档。

## 什么是使用 Aspose.Zip 加密 zip？

对 ZIP（或 7z）文件进行加密意味着对其条目进行保护，只有使用正确的密码才能打开。Aspose.Zip for .NET 支持经典的 ZipCrypto 和更强的 AES 加密，并且允许您为每个条目单独设置加密参数，从而实现细粒度的安全控制。

## 为什么为每个条目使用不同的密码？

- **安全分区：** 即使一个密码泄露，其他文件仍保持受保护。  
- **合规要求：** 某些行业要求对不同数据类别使用独立凭证。  
- **用户特定访问：** 您可以向多个用户分发同一个存档，每人只能解锁其被授权查看的文件。

## 前提条件

在开始之前，请确保您已具备：

- 已安装 **Aspose.Zip for .NET** ——请参阅官方 [documentation](https://reference.aspose.com/zip/net/) 获取下载和安装说明。  
- 在机器上创建一个用于存放源文件的文件夹（即 “Document Directory”）。  
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

定义保存待压缩文件的路径。

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：创建具有不同密码的条目

下面是本教程的核心。我们打开一个新的 7z 文件，创建三个 `FileInfo` 对象，并为每个对象添加带有独立 AES 密码的条目。

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
- `CreateEntry` 接受条目名称、源文件、是否覆盖的标志以及 `SevenZipEntrySettings` 对象。  
- 在 `SevenZipEntrySettings` 中我们提供两个设置对象：一个用于压缩（`SevenZipStoreCompressionSettings`），一个用于加密（`SevenZipAESEncryptionSettings`）。  
- 每次调用都提供 **不同的密码**（`"test1"`、`"test2"`、`"test3"`），实现了每条目独立保护。

## 步骤 3：验证

存档保存后，您可以输出一条简单的确认信息。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

运行程序后，使用 7‑Zip 等工具打开 `archive.7z`。系统会为每个条目分别提示输入密码，从而确认密码确实各不相同。

## 常见问题及解决方案

| Issue | Reason | Fix |
|-------|--------|-----|
| **Incorrect password error** | 密码字符串中包含多余的空格或不可见字符。 | 使用 `Trim` 去除密码两端空格（`new SevenZipAESEncryptionSettings(password.Trim())`）。 |
| **Archive not opening in older tools** | 某些旧版 ZIP 工具不支持 7z 使用的 AES‑256 加密。 | 使用现代解压工具（如 7‑Zip 19.00+）。 |
| **File not added to archive** | 源文件路径错误或文件不存在。 | 检查 `dataDir` 与文件名，或使用 `Path.Combine(dataDir, "data1.bin")`。 |

## 常见问答

### Q1: Aspose.Zip for .NET 是否兼容所有 .NET 版本？

A1: 是的，Aspose.Zip for .NET 旨在无缝集成到所有 .NET 框架版本中。

### Q2: 我可以在商业项目中使用 Aspose.Zip for .NET 吗？

A2: 当然可以！Aspose.Zip for .NET 提供商业许可证，更多购买信息请参阅 [here](https://purchase.aspose.com/buy)。

### Q3: 是否提供免费试用？

A3: 是的，您可以通过免费试用来体验 Aspose.Zip for .NET 的功能。立即开始 [here](https://releases.aspose.com/)。

### Q4: 如何获取 Aspose.Zip for .NET 的技术支持？

A4: 如有任何疑问或需要帮助，请访问 [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37)。

### Q5: 我可以在没有永久许可证的情况下使用 Aspose.Zip for .NET 吗？

A5: 可以，您可以获取临时许可证以满足短期需求。详情请查看 [here](https://purchase.aspose.com/temporary-license/)。

## 结论

您已经学习了 **如何加密 zip** 存档并为每个条目设置独立密码的技巧。此方法使您能够对每个文件单独保护，满足更严格的安全要求并简化针对特定用户的分发。欢迎尝试其他压缩设置、更大的文件集，或将此逻辑集成到生成安全存档的 Web 服务中。

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Zip for .NET 24.12（撰写时的最新版本）  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}