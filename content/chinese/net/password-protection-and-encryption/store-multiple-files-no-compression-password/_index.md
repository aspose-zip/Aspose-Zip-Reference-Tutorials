---
title: Aspose.Zip for .NET - 安全文件存储教程
linktitle: 使用密码存储多个文件而不进行压缩
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 探索如何使用 Aspose.Zip for .NET 安全地存储多个文件而不进行压缩。密码保护的简单步骤。释放文件管理的力量！
type: docs
weight: 13
url: /zh/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

在 .NET 开发领域，管理和操作文件是一项常见任务。 Aspose.Zip for .NET 是一个功能强大的库，为开发人员提供无缝压缩、解压缩和操作 zip 存档的功能。在本教程中，我们将深入研究一个特定的场景：存储多个文件而不压缩并使用密码保护它们。在本指南结束时，您将具备使用 Aspose.Zip for .NET 实现此功能的知识。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Zip for .NET 库：确保您已安装 Aspose.Zip for .NET 库。你可以下载它[这里](https://releases.aspose.com/zip/net/).

- 文档目录：准备一个源文件所在的目录。在提供的示例中，变量`dataDir`代表您的文档目录。

## 导入命名空间

首先，让我们为我们的代码导入必要的命名空间：

```csharp
//资源目录的路径。
string dataDir = "Your Document Directory"

//导入 Aspose.Zip 命名空间
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 第 1 步：打开 Zip 文件

```csharp
//ExStart：存储多个文件而不带密码压缩
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

此步骤涉及使用以下命令创建新的 zip 文件`FileStream`。该文件将被命名为“StoreMutlipleFilesWithoutCompressionWithPassword_out.zip”。

## 第2步：打开源文件

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

在这里，我们打开第一个源文件“alice29.txt”，该文件将存储在 zip 存档中。

## 第 3 步：创建档案

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

在这一步中，我们创建一个实例`Archive`类，指定压缩和加密设置。我们使用`StoreCompressionSettings`存储不压缩的文件`AesEcryptionSettings`使用密码（“p@s$”）应用 AES 加密。

## 第 4 步：创建存档条目并保存

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

最后一步涉及在存档中创建“alice29.txt”条目并保存存档，从而完成不压缩且具有密码保护的存储文件的过程。

通过总结要点并鼓励读者探索 Aspose.Zip for .NET 的更多可能性来结束您的教程。

## 结论

在本教程中，我们探讨了如何使用 Aspose.Zip for .NET 存储多个文件而不进行压缩并使用密码保护它们。当您继续 .NET 开发之旅时，可以利用 Aspose.Zip 的功能来简化文件管理任务并增强应用程序的安全性。

---

### 常见问题解答

### 我可以将 Aspose.Zip for .NET 与其他加密方法一起使用吗？
是的，Aspose.Zip 支持各种加密方法。检查文档[这里](https://reference.aspose.com/zip/net/)了解详情。

### 在哪里可以获得 Aspose.Zip for .NET 支持？
参观[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)以获得社区支持和讨论。

### Aspose.Zip for .NET 是否有免费试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/).

### 如何获得 Aspose.Zip for .NET 的临时许可证？
申请临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 在哪里可以购买 Aspose.Zip for .NET？
您可以购买 Aspose.Zip for .NET[这里](https://purchase.aspose.com/buy).
