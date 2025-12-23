---
date: 2025-12-23
description: 学习如何使用 Aspose.Zip for .NET 提取受密码保护的 RAR 文件以及解密的 RAR 文件。按照分步指南高效读取加密的
  RAR 文件。
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 提取受密码保护的 RAR
url: /zh/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 提取受密码保护的 rar

## 介绍

如果您曾经需要在 .NET 应用程序中**提取受密码保护的 rar**压缩包，您就会知道这有多棘手。幸运的是，Aspose.Zip for .NET 消除了猜测，让您只需几行代码即可读取加密的 rar 文件。在本教程中，我们将完整演示整个过程——从项目设置到内容提取——帮助您将解密功能无缝集成到解决方案中。

## 快速答复
- **处理 RAR 解密的库是什么？** Aspose.Zip for .NET  
- **生产环境是否需要许可证？** 是的，需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **可以在循环中提取多个压缩包吗？** 当然——对每个文件重复相同步骤即可。  
- **密码是否区分大小写？** 是的，按普通字符串处理。

## 什么是“提取受密码保护的 rar”？

提取受密码保护的 RAR 压缩包意味着打开压缩包，提供正确的解密密码，然后将其中的文件写入目标文件夹。Aspose.Zip 抽象了底层细节，让您专注于业务逻辑。

## 为什么使用 Aspose.Zip for .NET？

- **完整的 RAR 支持** – 支持 RAR4 和 RAR5 格式，包括加密压缩包。  
- **简洁的 API** – 只需少量方法调用即可打开、解密和提取。  
- **跨平台** – 在 Windows、Linux 和 macOS 的 .NET 运行时上均可运行。  
- **无外部依赖** – 无需携带第三方 RAR 工具。

## 前提条件

1. **Aspose.Zip for .NET 库** – 通过 NuGet 安装该库，或从 [Aspose.Zip 文档](https://reference.aspose.com/zip/net/) 下载。  
2. **文档目录** – 准备一个包含待处理加密 RAR 压缩包的文件夹。将代码中的占位路径替换为实际目录。

## 导入命名空间

在 C# 文件顶部添加所需的 `using` 语句：

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## 步骤 1：打开加密的 RAR 压缩包

为要解密的 RAR 文件打开只读流。将 `"encrypted.rar"` 更改为您的文件名。

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## 步骤 2：指定解密密码

提供保护压缩包的密码。在本例中密码为 `"p@s$"`。请将其替换为您实际设置的密码。

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## 步骤 3：将内容提取到目录

将解密后的文件提取到您选择的文件夹。将 `"DecompressRar_out"` 更改为您想要的输出路径。

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

## 使用 Aspose.Zip 提取受密码保护的 rar 文件的方法

通过上述三个步骤，您可以以编程方式**提取受密码保护的 rar**压缩包。此方法适用于任意数量的文件——只需遍历文件列表并重复这些步骤即可。

## 常见使用场景

- **自动化数据摄取** – 从加密的 RAR 包中提取数据并自动处理。  
- **企业备份恢复** – 解密并恢复存储在受密码保护的 RAR 文件中的归档备份。  
- **安全文件交换** – 允许用户上传加密的 RAR 压缩包，然后在服务器端进行验证后提取。

## 结论

您已经学习了如何使用 Aspose.Zip for .NET **提取加密的 rar 文件**以及**读取加密的 rar 文件**内容。该库负责繁重的工作，让您专注于将提取的数据集成到应用程序的工作流中。

## 常见问题 (FAQs)

### Aspose.Zip for .NET 是否兼容所有 RAR 压缩包版本？

Aspose.Zip for .NET 支持多种 RAR 压缩包版本，确保兼容大量文件。

### 我可以在商业项目中使用 Aspose.Zip for .NET 吗？

可以，Aspose.Zip for .NET 可用于商业用途。请访问[购买页面](https://purchase.aspose.com/buy)了解许可证详情。

### 是否提供用于测试的临时许可证？

可以，您可以从[此处](https://purchase.aspose.com/temporary-license/)获取用于测试的临时许可证。

### 我在哪里可以找到额外的支持或社区讨论？

请访问[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)获取支持和社区讨论。

### 如何获取 Aspose.Zip for .NET 的文档？

[文档](https://reference.aspose.com/zip/net/)提供了使用 Aspose.Zip for .NET 的全面信息。

**Additional Q&A**

**问：如果密码错误会怎样？**  
答：Aspose.Zip 会抛出 `InvalidPasswordException`。捕获该异常以优雅地处理错误。

**问：我可以只提取压缩包中的特定文件吗？**  
答：可以，遍历 `archive.Entries` 并对所需的条目调用 `entry.ExtractToFile()`。

**问：是否可以提取大于 2 GB 的压缩包？**  
答：完全可以——Aspose.Zip 使用流处理，文件大小仅受系统可用资源限制。

---

**最后更新：** 2025-12-23  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}