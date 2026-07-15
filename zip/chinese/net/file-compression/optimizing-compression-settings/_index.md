---
date: 2026-06-09
description: 了解如何使用 Aspose.Zip for .NET 为 zip 添加密码并创建 LZMA zip 存档。本教程涵盖 Bzip2、LZMA（字典大小）、PPMd、Enhanced
  Deflate、Store 压缩，以及 ASP.NET 大文件的文件压缩。
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: 优化压缩设置
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 为 zip 添加密码并创建 LZMA 存档
url: /zh/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 为 zip 添加密码并使用 Aspose.Zip for .NET 创建 LZMA 存档

在现代 .NET 应用程序中，**为 zip 添加密码** 并创建高压缩率的 LZMA zip 存档可以保护敏感数据，同时提供最佳的压缩效果。无论您是在构建 ASP.NET 文件压缩服务、处理多 GB 文件的桌面工具，还是基于云的工作流，本教程都将逐步演示如何使用 Aspose.Zip for .NET 对文件进行安全压缩。

## 快速答案
- **LZMA 压缩的主要优势是什么？** 在大多数文件类型上实现最高的压缩比，同时保持合理的速度。  
- **哪种方法在不进行压缩的情况下存储文件？** Store compression（也称为 “store compression zip”）。  
- **我可以在 ASP.NET 应用程序中使用这些设置吗？** 可以——只需在项目中引用 Aspose.Zip 并调用相同的 API。  
- **生产环境是否需要许可证？** 生产环境需要商业许可证；提供免费试用版。  
- **支持哪些 .NET 版本？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1，以及 .NET 5–10。

## 什么是 Aspose.Zip 中的 “add password to zip”？
**为 zip 添加密码会对 ZIP 存档中的每个条目进行加密，只有知道密码的用户才能解压文件。** Aspose.Zip 同时支持传统的 ZipCrypto 加密和 AES 加密（128、192 或 256 位）。加密设置作为第二个参数传递给 `ArchiveEntrySettings` 构造 `Archive` 时提供，暂无单独的 `SetPassword` 方法。

## 为什么使用 Aspose.Zip for .NET 进行文件压缩？
Aspose.Zip 提供统一且一致的 API，覆盖多种算法，同时实现高性能和低内存占用。它让开发者能够为不同场景选择最佳压缩方式，并在一步操作中完成加密，简化代码并降低维护成本。

- **统一 API** – 为 Bzip2、LZMA、PPMd、Enhanced Deflate 和 Store 提供一致的接口。  
- **性能调优** – 优化的本地实现可处理 **高达 10 GB 的文件**，无需将整个文件加载到内存中。  
- **ASP.NET 友好** – 在 Web 项目、后台服务和 Azure Functions 中无缝工作。  
- **细粒度控制** – 通过单一构造函数即可调整字典大小、压缩级别和加密方式。  
- **支持 10+ 压缩算法** – 覆盖企业数据管道中最常见的使用场景。

## 前置条件
- **Aspose.Zip for .NET 库** – 从 [Aspose 文档](https://reference.aspose.com/zip/net/) 下载并安装。  
- **示例文本文件** – 准备一个示例文件（例如 `sample.txt`），用于压缩。  
- **.NET 开发环境** – Visual Studio 2022 或任何兼容的 IDE。

## 导入命名空间

`Archive`、`ArchiveEntrySettings` 和加密类位于 `Aspose.Zip` 命名空间。请在文件顶部导入它们：

- `Archive` 表示 ZIP 存档容器。  
- `ArchiveEntrySettings` 保存每个条目的压缩和加密选项。  
- 加密类（如 `AesEncryptionSettings`）定义数据的加密方式。

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

现在让我们逐一查看每种压缩设置，并在适当的位置 **为 zip 添加密码**。

## 使用 Bzip2 压缩设置

### 步骤 1：使用传统加密初始化 Bzip2 压缩

`Bzip2CompressionSettings` 配置 Bzip2 算法（块大小等）。  
`TraditionalEncryptionSettings` 对条目应用传统的 ZipCrypto 加密。

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*密码保护通过直接传递给 `ArchiveEntrySettings` 的 `TraditionalEncryptionSettings` 实现。*

## 如何使用 Aspose.Zip for .NET 为 zip 添加密码

加载源文件，使用条目设置创建 `Archive`，并将文件添加到存档中。由于在创建 `ArchiveEntrySettings` 实例时已提供加密信息，密码会自动应用。

**直接回答（40‑70 字）：**  
创建包含所需压缩设置以及 `TraditionalEncryptionSettings` 或 `AesEncryptionSettings` 的 `ArchiveEntrySettings` 对象。将该对象传递给 `Archive` 构造函数并使用 `AddEntry` 添加文件。存档在写入时已嵌入密码，无需在创建后额外操作。

`ArchiveEntrySettings` 是配置持有者，告诉 Aspose.Zip 每个条目应如何压缩和加密。  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## 如何使用 Aspose.Zip 创建 LZMA zip 存档

### 步骤 1：使用 AES256 加密初始化 LZMA 压缩

`LzmaCompressionSettings` 控制 LZMA 特有的参数，如字典大小和 fast bytes。  
`AesEncryptionSettings` 为存档条目提供 AES‑256 加密。

**直接回答（40‑70 字）：**  
实例化 `LzmaCompressionSettings` 并设置 `DictionarySize`，创建包含密码且 `EncryptionMethod.AES256` 的 `AesEncryptionSettings` 对象，然后将两者组合成 `ArchiveEntrySettings`。将该设置传给 `Archive` 构造函数并添加文件；生成的 zip 将以 LZMA 压缩并使用 AES‑256 加密，一步完成。

`LzmaCompressionSettings` 是控制 LZMA 特定参数（如字典大小和 fast bytes）的类。  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **提示：** LZMA 提供可配置的 **LZMA 字典大小**，会影响压缩比和内存使用。若需针对超大文件进行微调，可通过 `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` 设置。

## 使用 PPMd 压缩设置

### 步骤 1：使用 AES256 加密初始化 PPMd 压缩

`PpmdCompressionSettings` 定义 PPMd 算法的阶数和内存使用。  
`AesEncryptionSettings` 为存档条目提供 AES‑256 加密。

**直接回答（40‑70 字）：**  
创建 `PpmdCompressionSettings` 实例，结合包含密码的 `AesEncryptionSettings`，并将两者传入 `ArchiveEntrySettings`。在构造 `Archive` 时使用该设置；生成的 zip 将以 PPMd 压缩并自动进行密码保护，无需额外调用。

`PpmdCompressionSettings` 定义 PPMd 算法的阶数和内存使用。  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## 使用 Enhanced Deflate 压缩设置

### 步骤 1：使用 AES256 加密初始化 Enhanced Deflate 压缩

`EnhancedDeflateCompressionSettings` 允许指定在速度与体积之间平衡的压缩级别。  
`AesEncryptionSettings` 为存档条目提供 AES‑256 加密。

**直接回答（40‑70 字）：**  
实例化 `EnhancedDeflateCompressionSettings` 并设置所需级别（0‑9），与 `AesEncryptionSettings` 配对后包装进 `ArchiveEntrySettings`。将该设置传给 `Archive` 构造函数并添加文件；存档将使用 Enhanced Deflate 压缩并在一次操作中完成 AES‑256 密码保护。

`EnhancedDeflateCompressionSettings` 让您指定在速度与体积之间平衡的压缩级别。  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## 使用 Store 压缩设置（store compression zip）

### 步骤 1：使用传统加密初始化 Store 压缩

`StoreCompressionSettings` 告诉 Aspose.Zip 完全跳过压缩，保持源文件的原始字节。  
`TraditionalEncryptionSettings` 应用传统的 ZipCrypto 加密。

**直接回答（40‑70 字）：**  
创建 `StoreCompressionSettings` 实例（不进行压缩），将其与包含密码的 `TraditionalEncryptionSettings` 组合，并包装进 `ArchiveEntrySettings`。将该设置传给 `Archive` 构造函数；生成的 zip 将保持文件未压缩但已受密码保护。

`StoreCompressionSettings` 告诉 Aspose.Zip 完全跳过压缩，保持源文件的原始字节。  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **专业提示：** 将 `dataDir` 变量调整为指向实际工作目录，并在需要向同一存档添加多个文件时复用同一个 `Archive` 实例。

## 常见问题与解决方案
- **“找不到文件”错误** – 确认 `dataDir` 以路径分隔符（`\` 或 `/`）结尾，并且 `sample.txt` 确实存在。  
- **大文件的内存消耗** – 使用 `ArchiveEntrySettings` 启用流式模式，直接将数据写入输出流。  
- **压缩级别不兼容** – 某些算法（如 LZMA）暴露额外属性，例如 `DictionarySize`。如需更细粒度控制，请查阅 API 文档。  
- **密码未生效** – 确保在构造 `ArchiveEntrySettings` 时将加密设置对象作为第二参数传入，而不是在创建存档后再设置。

## 常见问答

**问：我可以将 Aspose.Zip for .NET 与其他压缩库一起使用吗？**  
答：Aspose.Zip 设计用于使用其内置算法。可以集成第三方库，但需要在 Aspose API 之外进行自定义处理。

**问：如何为使用 Aspose.Zip 创建的 zip 添加密码保护？**  
答：在构造 `Archive` 时，将 `TraditionalEncryptionSettings` 或 `AesEncryptionSettings` 作为第二参数传递给 `ArchiveEntrySettings`。完整示例请参阅[文档](https://docs.aspose.com/zip/net/password-protecting-archives/)。

**问：是否有可供测试的试用版？**  
答：有，您可以在[此处](https://releases.aspose.com/)获取试用版。

**问：在哪里可以获取社区帮助或提问？**  
答：请访问[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)获取支持和社区讨论。

**问：我可以获取临时许可证用于评估吗？**  
答：可以，临时许可证请前往[此处](https://purchase.aspose.com/temporary-license/)获取。

**问：这对 ASP.NET 文件压缩有什么帮助？**  
答：在 ASP.NET 控制器或中间件中调用相同的 API，即可在将文件发送给客户端之前实时压缩，降低带宽消耗并提升感知性能。

**问：压缩大文件的最佳方式是什么？**  
答：将流式模式与 LZMA 压缩以及合适的 `DictionarySize` 结合使用，可在处理海量数据时平衡内存占用和压缩比。

---

**最后更新：** 2026-06-09  
**测试环境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [Aspose.Zip for .NET - 为 Zip 存档添加密码并在不压缩的情况下存储多个文件](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [为 .NET 目录创建受密码保护的 zip – Aspose.Zip 教程](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [c# 多文件压缩 – 使用 Aspose.Zip for .NET 轻松实现](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}