---
title: 使用 Aspose.Zip for .NET 解密 RAR 存档
linktitle: 解密 RAR 存档
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 使用 Aspose.Zip for .NET 轻松解锁加密的 RAR 存档。按照我们的分步指南进行无缝集成和高效解密。
weight: 12
url: /zh/net/rar-archive/decrypt-rar-archive/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 解密 RAR 存档


## 介绍

解锁受密码保护的 RAR 存档的内容可能是一项艰巨的任务，但使用 Aspose.Zip for .NET，该过程变得简单而高效。在本教程中，我们将引导您完成使用 Aspose.Zip 库解密 RAR 存档的步骤。无论您是经验丰富的开发人员还是编码爱好者，本指南都将帮助您将解密功能无缝集成到您的 .NET 应用程序中。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

1.  Aspose.Zip for .NET 库：确保您的 .NET 项目中安装了 Aspose.Zip 库。您可以从[Aspose.Zip 文档](https://reference.aspose.com/zip/net/).

2. 文档目录：设置加密 RAR 存档所在的目录。将示例代码中的“您的文档目录”替换为该目录的实际路径。

## 导入命名空间

让我们首先导入必要的命名空间以有效地使用 Aspose.Zip 库。将以下行添加到 .NET 文件的顶部：

```csharp
//ExStart：导入命名空间
using Aspose.Zip;
using System.IO;
//ExEnd：导入命名空间
```

## 第 1 步：打开加密的 RAR 存档

首先打开加密的 RAR 存档。在示例代码中，将“encrypted.rar”替换为加密 RAR 文件的名称。

```csharp
//开始：DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //结束：DecryptRarArchive_Step1
    //在这里继续下一步...
}
```

## 步骤2：指定解密密码

指定 RAR 存档的解密密码。在示例中，使用密码“p@s$”。将其替换为您为加密 RAR 文件设置的实际密码。

```csharp
//开始：DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //结束：DecryptRarArchive_Step2
    //在这里继续下一步...
}
```

## 第 3 步：将内容提取到目录

现在，将 RAR 存档的内容提取到指定目录。将“DecompressRar_out”替换为您想要存储解密文件的路径。

```csharp
//开始：DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//结束：DecryptRarArchive_Step3
```

对您需要解密的每个 RAR 存档重复这些步骤，确保将 Aspose.Zip for .NET 无缝集成到您的项目中。

## 结论

恭喜！您已使用 Aspose.Zip for .NET 成功解密了 RAR 存档。这个功能强大的库简化了解锁受密码保护的存档的复杂过程，使其成为使用 .NET 应用程序的开发人员的宝贵工具。

## 常见问题 (FAQ)

### Aspose.Zip for .NET 是否与所有 RAR 存档版本兼容？
Aspose.Zip for .NET 支持各种 RAR 存档版本，确保与各种文件的兼容性。

### 我可以在商业项目中使用 Aspose.Zip for .NET 吗？
是的，Aspose.Zip for .NET 可用于商业用途。参观[购买页面](https://purchase.aspose.com/buy)了解许可详细信息。

### 临时许可证是否可用于测试目的？
是的，您可以从以下位置获取临时测试许可证[这里](https://purchase.aspose.com/temporary-license/).

### 我在哪里可以找到其他支持或社区讨论？
参观[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)用于支持和社区讨论。

### 如何访问 Aspose.Zip for .NET 的文档？
这[文档](https://reference.aspose.com/zip/net/)提供有关使用 Aspose.Zip for .NET 的全面信息。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
