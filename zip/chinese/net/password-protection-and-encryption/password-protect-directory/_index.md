---
title: 使用 Aspose.Zip 教程密码保护 .NET 中的目录
linktitle: 密码保护目录
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 了解如何使用 Aspose.Zip 对 .NET 中的目录进行密码保护。通过此分步教程轻松保护您的文件。
weight: 10
url: /zh/net/password-protection-and-encryption/password-protect-directory/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip 教程密码保护 .NET 中的目录


## 介绍

在 .NET 开发领域，管理和保护目录是文件处理的一个重要方面。 Aspose.Zip for .NET 为密码保护目录提供了强大的解决方案，确保敏感数据的机密性和完整性。在本教程中，我们将指导您使用 Aspose.Zip for .NET 逐步完成密码保护目录的过程。

## 先决条件

在深入学习本教程之前，请确保您满足以下先决条件：

- 对 C# 编程语言有基本了解。
- Visual Studio 安装在您的计算机上。
-  Aspose.Zip for .NET 库。你可以下载它[这里](https://releases.aspose.com/zip/net/).
- 包含要受密码保护的文件的目录。

## 导入命名空间

首先，您需要将必要的命名空间导入到您的 C# 项目中。这些命名空间对于利用 Aspose.Zip for .NET 提供的功能至关重要。

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 第1步：设置资源目录的路径

首先，定义包含要使用密码保护的文件的目录的路径。

```csharp
string dataDir = "Your Document Directory";
```

## 第 2 步：用密码保护目录

现在，让我们深入研究执行目录密码保护的代码。我们使用`TraditionalEncryptionSettings`类设置密码并将其应用于指定目录。

```csharp
//ExStart：密码保护目录
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //结束：密码保护目录
    }
}
```

## 第 3 步：代码解释

让我们分解代码来理解每个步骤：

- 设置输出文件：`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)`为加密输出创建一个新的 ZIP 文件。

- 定义目录：`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")`指定要受密码保护的目录。

- 创建和保存条目：`archive.CreateEntries(corpus)`为指定目录中的文件创建条目，并且`archive.Save(zipFile)`保存受密码保护的存档。

## 结论

在本教程中，我们演示了使用 Aspose.Zip for .NET 使用密码保护目录的过程。通过执行这些步骤，您可以以用户友好且高效的方式确保敏感文件的安全。

---

## 经常问的问题

### Aspose.Zip for .NET 适合大型目录吗？
是的，Aspose.Zip for .NET 旨在高效处理大型目录，提供最佳性能。

### 我可以更改已受保护目录的密码吗？
是的，您可以通过调整密码来修改密码`TraditionalEncryptionSettings`相应地在代码中。

### 使用 Aspose.Zip for .NET 有任何许可要求吗？
是的，在生产环境中使用 Aspose.Zip for .NET 需要有效的许可证。您可以获得许可证[这里](https://purchase.aspose.com/buy).

### Aspose.Zip for .NET 是否有免费试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/).

### 在哪里可以找到 Aspose.Zip for .NET 的其他支持？
您可以访问[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)如有任何支持或疑问。


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
