---
date: 2026-02-15
description: 了解如何使用 Aspose.Zip for .NET 将 ZIP 解压到文件夹，包括密码保护的压缩包和加密 ZIP 的解压。
linktitle: extract zip to folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 将 ZIP 解压到文件夹
url: /zh/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 将 zip 解压到文件夹

## 介绍

如果您需要在 .NET 应用程序中快速且可靠地 **extract zip to folder**，Aspose.Zip for .NET 为您提供了一个简洁、跨平台的 API，能够处理普通和加密的归档文件。在本教程中，我们将逐步演示您需要的全部内容——从库的设置到解压受密码保护的 ZIP 文件——让您专注于业务逻辑，而无需处理底层归档操作。

## 快速答案
- **Aspose.Zip 的主要用途是什么？** 在 .NET 应用程序中创建、读取并 **extract zip to folder**。  
- **如何使用密码解压 zip？** 通过 `ArchiveLoadOptions.DecryptionPassword` 传递密码。  
- **我可以在没有密码的情况下解压加密归档吗？** 不可以——Aspose.Zip 需要正确的密码才能打开加密归档。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **生产环境是否需要许可证？** 是的，商业使用需要有效的 Aspose.Zip 许可证。

## 什么是 **extract zip to folder**？

解压 ZIP 文件是指读取压缩数据并将原始文件写入磁盘上的目标目录。Aspose.Zip 抽象了底层细节，使您只需调用一个方法即可完成整个操作。

## 为什么在 **how to unzip zip** 任务中使用 Aspose.Zip？

- **简洁的 API** – 只需最少的代码即可打开、解密和解压归档。  
- **支持加密归档** – 适用于安全的数据交换。  
- **跨平台** – 在 Windows、Linux 和 macOS 上使用 .NET Core/.NET 5+ 均可运行。  
- **无外部依赖** – 无需安装本机 zip 工具。  

## 先决条件

在开始之前，请确保您已拥有：

- Aspose.Zip for .NET 库：从 [Aspose.Zip for .NET documentation](https://reference.aspose.com/zip/net/) 下载并安装该库。  
- .NET 开发环境（Visual Studio、VS Code 或您喜欢的任何 IDE）。  
- （可选）如果您想尝试 **extract zip with password**，请准备一个受密码保护的 ZIP 文件。

## 导入命名空间

在您的 .NET 项目中，导入必要的命名空间以使用 Aspose.Zip 的功能：

```csharp
using Aspose.Zip;
using System.IO;
```

现在让我们一步一步拆解提取过程。

## 如何 **extract zip to folder** – 步骤指南

### 步骤 1：打开 ZIP 文件（或加密归档）

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

我们使用 `FileStream` 打开 ZIP 文件。请将路径调整为指向您自己的归档文件。如果归档未加密，同样的代码也适用于普通的 **decompress zip folder** 场景。

### 步骤 2：创建 `Archive` 实例（需要时提供密码）

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

`Archive` 构造函数接收流和一个 `ArchiveLoadOptions` 对象。提供 `DecryptionPassword` 即是实现 **extract zip with password** 并处理 **unzip encrypted archive** 情形的方式。

### 步骤 3：将内容提取到目标文件夹

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

调用 `ExtractToDirectory` 会将归档中的每个条目写入指定目录，完成 **extract zip to folder** 操作。如果目标文件夹不存在，方法会自动创建它。

> **技巧提示：** 如果您只需要提取部分文件，请使用接受过滤委托的重载，而不是提取全部。

## 常见问题与故障排除

- **密码错误** – Aspose.Zip 会抛出身份验证异常。请再次检查密码字符串或从配置源安全获取。  
- **目标路径未找到** – 确保目标目录路径有效；`ExtractToDirectory` 会创建缺失的文件夹，但父路径必须可访问。  
- **大型归档** – 对于非常大的 ZIP 文件，考虑使用流式 API 逐条提取，以降低内存使用。  

## 常见问答

**问：Aspose.Zip 是否支持除 ZIP 之外的压缩格式，如 GZIP？**  
答：是的，Aspose.Zip for .NET 支持 ZIP、GZIP 以及其他常见格式。

**问：我可以在商业和非商业项目中使用 Aspose.Zip 吗？**  
答：当然可以。生产环境需要有效许可证，但您可以使用免费试用版进行评估。

**问：如何获取用于测试的临时许可证？**  
答：您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证用于测试。

**问：在哪里可以下载 Aspose.Zip 的免费试用版？**  
答：请访问 Aspose.Zip 试用页面 [here](https://releases.aspose.com/) 下载最新版本。

**问：如果遇到问题，我可以在哪里寻求帮助？**  
答：Aspose.Zip 社区论坛是获取帮助的好地方：[support forum](https://forum.aspose.com/c/zip/37)。

---

**最后更新：** 2026-02-15  
**测试环境：** Aspose.Zip for .NET（最新发布）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}