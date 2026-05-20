---
description: 了解如何使用 Aspose.Zip for .NET 将 RAR 解压到文件夹并解密加密的 RAR 文件。按照分步指南读取加密的 RAR
  文件并指定 RAR 密码。
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 将 RAR 解压到文件夹
url: /zh/net/rar-archive/decrypt-rar-archive/
weight: 12
---

Be careful to preserve markdown formatting, code block placeholders remain unchanged.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 将 RAR 解压到文件夹

## 介绍

如果您需要 **extract RAR to folder** 并处理受密码保护的压缩包，Aspose.Zip for .NET 能让这项工作变得轻而易举。在本教程中，我们将逐步演示如何读取加密的 RAR 文件、指定 RAR 密码，并将压缩包的内容解压到目标目录。无论您是在构建桌面工具还是服务器端服务，都能快速、可靠地集成解密逻辑。

## 快速答案
- **“extract RAR to folder” 是什么意思？** 它指的是打开 RAR 压缩包并将每个条目写入磁盘上的指定目录。  
- **哪个库负责解密？** Aspose.Zip for .NET 提供对加密 RAR 压缩包的内置支持。  
- **测试是否需要许可证？** 可提供临时许可证用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+ 和 .NET 5/6+。  
- **实现需要多长时间？** 对于基本的解压场景，通常在 10 分钟以内。

## 什么是 “extract RAR to folder”？
将 RAR 压缩包解压到文件夹意味着解压存储在压缩包中的每个文件，并将它们放置在您选择的目录中。当压缩包被加密时，您还必须提供正确的密码才能进行解压。

## 为什么使用 Aspose.Zip 来解压加密的 RAR？
Aspose.Zip 抽象了 RAR 格式的复杂性，能够在无需外部依赖的情况下处理标准和加密的压缩包。它提供简洁的面向对象 API、出色的性能和优秀的错误处理——是希望获得 **how to decrypt RAR** 文件可靠解决方案的 .NET 开发者的理想选择。

## 先决条件

在开始教程之前，请确保已满足以下前提条件：

1. **Aspose.Zip for .NET 库**：确保在 .NET 项目中已安装 Aspose.Zip 库。您可以从 [Aspose.Zip 文档](https://reference.aspose.com/zip/net/) 下载。  
2. **文档目录**：设置一个存放加密 RAR 压缩包的目录。将示例代码中的 “Your Document Directory” 替换为该目录的实际路径。

## 导入命名空间

让我们先导入使用 Aspose.Zip 库所需的命名空间。将以下代码添加到 .NET 文件的顶部：

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## 步骤 1 – 打开加密的 RAR 压缩包

首先，为加密的 RAR 文件打开只读流。这一步为解密和解压做好准备。

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## 步骤 2 – 指定 RAR 密码（how to decrypt RAR）

现在创建一个 `RarArchive` 实例，并告诉 Aspose.Zip 保护该压缩包的密码。将 `"p@s$"` 替换为您创建加密 RAR 时使用的实际密码。

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## 步骤 3 – 将内容提取到文件夹（extract encrypted RAR）

最后，将每个条目提取到您选择的文件夹中。这一步完成了 **extract RAR to folder** 操作。

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

对需要解密的每个 RAR 压缩包重复上述步骤，即可在项目中无缝集成 Aspose.Zip for .NET。

## 常见陷阱与技巧

- **密码错误** – 若密码不正确，Aspose.Zip 会抛出 `WrongPasswordException`。请仔细检查传递给 `DecryptionPassword` 的字符串。  
- **大型压缩包** – 对于非常大的 RAR 文件，建议先解压到临时文件夹，再将文件移动到最终位置，以避免磁盘空间不足。  
- **路径安全** – 始终验证 `dataDir` 和输出路径，防止目录遍历漏洞。

## 结论

恭喜！您已成功 **extracted a RAR to folder**，并学习了如何使用 Aspose.Zip for .NET **read encrypted RAR file**。该强大库简化了解锁受密码保护压缩包的复杂过程，是 .NET 应用开发者的宝贵工具。

## 常见问题 (FAQs)

### Aspose.Zip for .NET 是否兼容所有 RAR 压缩包版本？
Aspose.Zip for .NET 支持各种 RAR 压缩包版本，确保兼容广泛的文件。

### 我可以在商业项目中使用 Aspose.Zip for .NET 吗？
是的，Aspose.Zip for .NET 可用于商业项目。访问 [purchase page](https://purchase.aspose.com/buy) 获取许可详情。

### 是否提供用于测试的临时许可证？
是的，您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取用于测试的临时许可证。

### 在哪里可以找到更多支持或社区讨论？
访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取支持和社区讨论。

### 如何获取 Aspose.Zip for .NET 的文档？
请参阅 [文档](https://reference.aspose.com/zip/net/) 获取 Aspose.Zip for .NET 的完整使用信息。

**附加问答**

**Q:** 如何仅从加密的 RAR 中提取特定文件？  
**A:** 使用 `RarArchiveEntry` 定位所需条目，并在已设置解密密码的压缩包上调用 `ExtractToFile`。

**Q:** 如果需要动态更改输出文件夹名称怎么办？  
**A:** 在调用 `ExtractToDirectory` 之前，使用 `Path.Combine` 和运行时变量构建输出路径。

**Q:** Aspose.Zip 是否支持多卷 RAR 压缩包？  
**A:** 是的，只要所有卷都可访问，库即可打开并解压多卷 RAR 集。

---

**最后更新：** 2026-03-13  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}