---
date: 2025-12-21
description: 了解如何在 .NET 中创建受密码保护的 zip 文件、加密文件夹以及使用 Aspose.Zip 更改 zip 密码。
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 为 .NET 目录创建受密码保护的 zip – Aspose.Zip 教程
url: /zh/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 为 .NET 目录创建受密码保护的 zip – Aspose.Zip 教程

在本指南中，您将使用 Aspose.Zip 库为整个目录 **创建受密码保护的 zip** 压缩包。无论是 **加密文件夹**、保护备份文件，还是仅仅限制对敏感数据的访问，本分步教程都将展示如何使用简洁的 C# 代码实现。

## 快速答案
- **推荐使用哪个库？** Aspose.Zip for .NET  
- **可以加密整个文件夹吗？** 可以 – 只需将 API 指向要压缩的文件夹。  
- **是否支持更改 zip 密码？** 当然，使用 `TraditionalEncryptionSettings` 即可。  
- **生产环境需要许可证吗？** 商业使用必须拥有有效的 Aspose.Zip 许可证。  
- **兼容 .NET Core/5/6 吗？** 兼容，API 完全支持现代 .NET 运行时。  

## 什么是 “create password protected zip”？
创建受密码保护的 zip 是指在将文件或目录压缩为 ZIP 存档的同时，应用加密，使得只有使用正确密码才能打开该存档，从而防止未授权访问。

## 为什么在 .NET 中使用 Aspose.Zip 对目录进行密码保护？
Aspose.Zip 提供直观且高性能的 API，支持 **c# zip password protection**、传统 ZipCrypto 加密以及 AES 加密。它能够高效处理大型目录，并可无缝集成到任何 .NET 项目中。

## 前置条件
在开始之前，请确保您具备以下条件：

- 基础的 C# 编程知识。  
- Visual Studio（任意近期版本）。  
- Aspose.Zip for .NET 库 – 在 **[此处](https://releases.aspose.com/zip/net/)** 下载。  
- 一个您希望使用密码保护的磁盘文件夹。

## 导入命名空间
在 C# 文件中添加所需的命名空间，以便编译器能够找到 Aspose.Zip 类。

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## 步骤 1：设置资源目录的路径
定义指向您要压缩并保护的目录的路径。

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：对目录进行密码保护
使用 `TraditionalEncryptionSettings` 指定密码并创建加密存档。这是 **c# zip password protection** 的核心。

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## 步骤 3：代码说明
- **创建输出文件：** `File.Open(..., FileMode.Create)` 打开（或创建）用于保存加密数据的 ZIP 文件。  
- **选择源文件夹：** `new DirectoryInfo(".\\CanterburyCorpus")` 告诉 Aspose.Zip 要压缩哪个目录。  
- **应用密码：** `new TraditionalEncryptionSettings("p@s$")` 设置用于保护存档的密码。  
- **添加条目并保存：** `archive.CreateEntries(corpus)` 将文件夹中的每个文件加入压缩包，`archive.Save(zipFile)` 将加密后的 ZIP 写入磁盘。

## 如何以后更改 zip 密码？
如果需要 **change zip password**，只需使用包含新密码的 `TraditionalEncryptionSettings` 实例重新创建存档，然后再次保存即可。

## 常见问题与技巧
- **大型文件夹：** Aspose.Zip 采用流式处理，内存占用低，即使是超大目录也能顺畅处理。  
- **密码复杂度：** 使用强密码（字母、数字、符号混合）提升安全性。  
- **许可证错误：** 确保已应用有效的许可证文件，否则库将以评估模式运行并受限。

## 常见问答

### Aspose.Zip for .NET 适用于大型目录吗？
是的，Aspose.Zip for .NET 旨在高效处理大型目录，提供最佳性能。

### 能否更改已受保护目录的密码？
可以，只需在代码中相应地调整 `TraditionalEncryptionSettings` 即可。

### 使用 Aspose.Zip for .NET 是否有许可证要求？
是的，生产环境中使用 Aspose.Zip for .NET 必须拥有有效许可证。您可以在 **[此处](https://purchase.aspose.com/buy)** 获取许可证。

### 是否提供 Aspose.Zip for .NET 的免费试用？
提供，您可以在 **[此处](https://releases.aspose.com/)** 访问免费试用。

### 在哪里可以获取 Aspose.Zip for .NET 的其他支持？
您可以访问 **[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)** 寻求支持或提问。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.Zip for .NET（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}