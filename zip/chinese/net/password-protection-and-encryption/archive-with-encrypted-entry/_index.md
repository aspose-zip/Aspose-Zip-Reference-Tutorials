---
date: 2026-03-05
description: 学习如何在 .NET 中使用 Aspose.Zip 创建带 AES 加密的 7z 文件，以实现安全归档。
linktitle: Archive with Encrypted Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何在 .NET 中使用 Aspose.Zip 创建安全归档的 7z 文件
url: /zh/net/password-protection-and-encryption/archive-with-encrypted-entry/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip 在 .NET 中创建带安全归档的 7z 文件

## 介绍

如果您需要创建既紧凑又受保护的 **how to create 7z** 存档，您来对地方了。在现代 .NET 应用程序中，安全归档对于保护知识产权、遵守数据隐私法规以及降低存储成本至关重要。Aspose.Zip for .NET 为您提供简洁的 API，能够生成 **Seven Zip** 存档、应用 **AES 加密**，甚至 **password protect 7z** 文件——全部在 C# 环境中完成。

在本教程中，我们将完整演示创建 7z 存档、加密 zip 条目并将结果保存到磁盘的全过程。完成后，您将了解如何 **how to encrypt zip** 文件、使用 **seven zip compression**，以及将安全归档集成到任何 .NET 项目中。

## 快速答案
- **支持 7z 创建的库是什么？** Aspose.Zip for .NET  
- **我可以加密单个条目吗？** 是的，使用 `SevenZipAESEncryptionSettings`  
- **是否支持密码保护？** 当然——AES 密钥充当密码  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+  
- **生产环境需要许可证吗？** 生产使用需要商业许可证  

## 什么是 7z 存档以及为何使用 AES 加密？

**7z** 文件是一种由 7‑Zip 实用程序创建的高压缩率存档格式。它支持 LZMA/LZMA2 等高级算法以及强大的 **AES‑256** 加密，使其非常适合 **secure archiving .net** 场景，在这些场景中，文件大小和机密性同等重要。

## 为什么选择 Aspose.Zip for .NET？

- **原生 .NET API** – 无需外部可执行文件或本机互操作。  
- **完全控制** 压缩级别、加密设置和条目流。  
- **跨平台** 支持 Windows、Linux 和 macOS。  
- **全面的文档** 与活跃的社区支持。  

## 前提条件

在开始之前，请确保您具备：

- 一个 .NET 开发环境（Visual Studio、VS Code 或 Rider）。  
- 已安装 Aspose.Zip for .NET – 请参阅文档 **[此处](https://reference.aspose.com/zip/net/)**。  
- 从 **[下载链接](https://releases.aspose.com/zip/net/)** 下载库。  
- 具备 C# 和文件 I/O 的基本了解。  

## 导入命名空间

在您的 C# 项目中，首先导入所需的命名空间：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## 步骤 1：设置资源目录路径

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory";
```

## 步骤 2：使用 AES 加密创建 Seven Zip 文件

```csharp
//ExStart: ArchiveWithEncryptedEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", 
            new MemoryStream(new byte[] { 0x00, 0xFF }), 
            new SevenZipEntrySettings(new SevenZipLZMACompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.Save(sevenZipFile);
    }
}
//ExEnd: ArchiveWithEncryptedEntry
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

**说明：**  
在此步骤中，我们打开（或创建）名为 **archive.7z** 的文件，添加一个名为 **entry1.bin** 的条目，并使用密码 `"test1"` 应用 **AES 加密**。`SevenZipLZMACompressionSettings` 对象控制压缩算法，而 `SevenZipAESEncryptionSettings` 负责加密。您可以重复调用 `CreateEntry` 来添加更多文件，如有需要，每个文件都可以拥有各自的加密配置。

### 如何单独加密 zip 条目
如果您需要使用不同密码对 **encrypt zip entry** 对象进行加密，只需为每次调用 `CreateEntry` 实例化一个新的 `SevenZipAESEncryptionSettings` 即可。

### 如何对 7z 文件进行密码保护
在 `SevenZipAESEncryptionSettings` 中提供的密码即充当整个存档的 **password protection**。打开存档时，必须提供相同的密码。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| 打开存档时出现 “Invalid password” 错误 | 密码不匹配或缺少 `SevenZipAESEncryptionSettings` | 确认密码字符串完全匹配（区分大小写）。 |
| 存档大小大于预期 | 使用默认压缩级别 | 调整 `SevenZipLZMACompressionSettings`（例如，将 `CompressionLevel = CompressionLevel.High`）。 |
| 在非 Windows 操作系统上运行时异常 | 缺少本机依赖项 | 确保使用的 Aspose.Zip 版本为最新，并已捆绑所需的本机库。 |

## 结论

您已经学习了使用 Aspose.Zip for .NET 通过 AES 加密 **how to create 7z** 存档的方式。此技术使您能够构建 **secure archiving .net** 解决方案，在保护敏感数据的同时保持文件体积最小。欢迎探索其他设置——例如自定义压缩级别或多线程归档——以针对特定场景微调性能。

## 常见问答

### 我可以在非商业项目中使用 Aspose.Zip for .NET 吗？
可以，Aspose.Zip for .NET 可用于商业和非商业项目。

### 如何获取 Aspose.Zip for .NET 的临时许可证？
获取临时许可证 **[此处](https://purchase.aspose.com/temporary-license/)**。

### 是否有 Aspose.Zip for .NET 的社区支持？
是的，请访问 **[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)** 获取社区支持。

### 除了 LZMA 之外还有其他支持的压缩算法吗？
Aspose.Zip for .NET 支持多种算法，包括 LZMA、LZMA2、BZIP2 和 PPMd。请查阅文档获取完整细节。

### 我可以进一步自定义加密设置吗？
当然！请查阅文档了解高级加密选项，例如自定义密钥长度和迭代次数。

## 常见问题

**问：如何向同一个 7z 存档添加多个加密条目？**  
答：重复调用 `archive.CreateEntry`，如果需要不同密码，则为每个条目提供不同的 `SevenZipAESEncryptionSettings`。

**问：Aspose.Zip 是否支持在不将大文件全部加载到内存的情况下进行流式处理？**  
答：是的，您可以将 `FileStream` 或其他流传递给 `CreateEntry`，从而高效处理大文件。

**问：我可以使用 Aspose.Zip 解密已有的 7z 存档吗？**  
答：使用接受流的 `SevenZipArchive` 构造函数，并通过 `SevenZipAESEncryptionSettings` 提供正确的密码。

**问：是否可以为每个条目单独设置压缩级别？**  
答：可以，在调用 `CreateEntry` 前为每个条目配置 `SevenZipLZMACompressionSettings`。

**问：哪些 .NET 运行时已正式测试与 Aspose.Zip 兼容？**  
答：.NET Framework 4.5+、.NET Core 3.1+、.NET 5、.NET 6 以及更高版本。

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}