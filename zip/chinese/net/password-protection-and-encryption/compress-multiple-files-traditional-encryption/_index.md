---
title: 在 Aspose.Zip .NET 中加密压缩多个文件
linktitle: 使用传统加密压缩多个文件
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 了解如何使用 Aspose.Zip for .NET 中的传统加密安全地压缩多个文件。增强 .NET 应用程序中的数据保护。
type: docs
weight: 17
url: /zh/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
---

## 介绍

欢迎阅读本分步教程，了解如何使用 Aspose.Zip for .NET 通过传统加密方式压缩多个文件。 Aspose.Zip 是一个功能强大的库，使开发人员能够在其 .NET 应用程序中无缝地使用 zip 存档。在本指南中，我们将引导您完成使用传统加密压缩多个文件的过程，确保数据的安全。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Zip for .NET：确保您的开发环境中安装了 Aspose.Zip for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/zip/net/).

- 您的文档目录：替换`"Your Document Directory"`在代码片段中包含文档目录的实际路径。

## 导入命名空间

在您的 .NET 应用程序中，首先导入必要的命名空间。这将允许您访问 Aspose.Zip 提供的功能。这是一个例子：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 第 1 步：设置 Zip 文件

使用以下命令创建一个新的 zip 文件`Archive`班级。在此步骤中，您还将定义传统加密设置，提供密码以增强安全性。

```csharp
//ExStart：使用传统加密压缩多个文件
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    //使用传统加密设置创建存档
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        //继续下一步...
    }
}
//扩展：使用传统加密压缩多个文件
```

## 第 2 步：将文件添加到存档

现在，将要压缩的文件添加到存档中。在此示例中，我们添加三个文件：“alice29.txt”、“asyoulik.txt”和“fields.c”。

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

## 第 3 步：保存 Zip 文件

保存包含添加条目的 zip 文件。这一步完成了压缩过程。

```csharp
archive.Save(zipFile);
```

恭喜！您已使用 Aspose.Zip for .NET 通过传统加密成功压缩了多个文件。

## 结论

在本教程中，我们探讨了如何利用 Aspose.Zip for .NET 通过传统加密来压缩多个文件。此过程可确保数据的安全性，同时有效管理 .NET 应用程序中的 zip 存档。

---

## 常见问题解答

### 1. 我可以在 Windows 和 Linux 环境中使用 Aspose.Zip for .NET 吗？

是的，Aspose.Zip for .NET 与 Windows 和 Linux 环境兼容，为开发人员提供了灵活性。

### 2. Aspose.Zip for .NET 是否有免费试用版？

是的，您可以免费试用 Aspose.Zip for .NET[这里](https://releases.aspose.com/).

### 3. 如何获得 Aspose.Zip for .NET 支持？

如需任何支持或疑问，您可以访问[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37).

### 4. Aspose.Zip for .NET 是否有临时许可证？

是的，可以从以下位置获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 5. 在哪里可以找到 Aspose.Zip for .NET 的详细文档？

参考文档[这里](https://reference.aspose.com/zip/net/)以获得深入的信息。
