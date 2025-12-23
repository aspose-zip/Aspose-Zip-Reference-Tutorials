---
date: 2025-12-23
description: 了解如何使用 Aspose.Zip for .NET 对 zip 文件进行密码保护以及如何加密 zip 存档。使用安全密码在不压缩的情况下存储多个文件。
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 对 ZIP 进行密码保护
url: /zh/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 对 ZIP 文件进行密码保护

在现代 .NET 开发中，保护归档文件的安全性与压缩它们同等重要。本教程展示了 **如何使用 Aspose.Zip for .NET 对 zip 文件进行密码保护**，同时演示 **如何在 .NET 中创建不压缩的 zip 归档** 以及 **如何使用 AES 加密 zip 归档**。阅读完本指南后，您将获得一套可直接嵌入任意 C# 项目的完整步骤方案。

## 快速答案
- **主要库是什么？** Aspose.Zip for .NET  
- **可以不压缩存储文件吗？** 可以 – 使用 `StoreCompressionSettings`。  
- **如何添加密码？** 提供一个包含密码的 `AesEcryptionSettings` 实例。  
- **支持 AES‑256 吗？** 完全支持 – 设置 `EncryptionMethod.AES256`。  
- **兼容哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。

## 什么是 “如何对 zip 进行密码保护”？
密码保护为 ZIP 归档添加了一层加密，只有知道密码的用户才能解压其中的内容。Aspose.Zip 通过在创建归档时定义加密设置，使这一过程变得简洁直观。

## 为什么选择 Aspose.Zip for .NET？
- **无外部依赖** – 纯 .NET 库。  
- **完全可控**，可自定义压缩、加密和归档结构。  
- **支持现代加密** 方法，如 AES‑256。  
- **高效处理大文件**，提供流式 API。

## 前置条件

在开始之前，请确保您具备以下条件：

- **Aspose.Zip for .NET 库** – 在 **[此处](https://releases.aspose.com/zip/net/)** 下载。  
- **文档目录** – 包含待归档文件的文件夹。示例中变量 `dataDir` 指向该位置。

## 导入命名空间

首先，导入使用 Aspose.Zip 所需的命名空间：

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 如何在 .NET 中创建不压缩的 Zip 归档

### 步骤 1：打开 Zip 文件

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

这里我们创建一个新的归档文件，用于保存条目。`FileMode.Create` 标志确保每次运行都会生成全新的文件。

### 步骤 2：打开源文件

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

我们打开第一个源文件（`alice29.txt`）。如需存储更多文件，可重复此代码块。

### 步骤 3：创建 “不压缩的 zip 归档”

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

- `StoreCompressionSettings()` 告诉 Aspose.Zip **不对文件进行压缩**，从而得到 **不压缩的 zip 归档**。  
- `AesEcryptionSettings("p@s$", EncryptionMethod.AES256)` 正是 **如何加密 zip 归档** 的实现——密码为 `"p@s$"`，加密方式为 AES‑256。

### 步骤 4：添加归档条目并保存

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

文件被添加到归档中并保存到磁盘，完成 **如何对 zip 进行密码保护** 的整个过程。

## 常见陷阱与技巧

- **密码复杂度** – 使用强密码；简单字符串容易被暴力破解。  
- **流释放** – `using` 语句会自动关闭流，防止文件被锁定。  
- **多文件** – 若要添加更多文件，只需再打开相应的 `FileStream` 并对每个文件调用 `CreateEntry`。  
- **兼容性** – 大多数现代压缩工具（WinRAR、7‑Zip 等）均支持 AES‑256 加密的 ZIP。

## 常见问答

**Q: 除了 AES‑256，我还能使用其他加密方式吗？**  
A: 可以，Aspose.Zip 支持 ZipCrypto 以及其他 AES 级别。只需相应地修改 `EncryptionMethod` 枚举。

**Q: 能否对已有的归档进行加密？**  
A: 需要使用期望的加密设置重新创建归档；Aspose.Zip 不支持对现有归档现场加密。

**Q: 不压缩存储文件会导致归档体积增大吗？**  
A: 会略有增大，因为原始文件字节被直接写入。这在需要快速解压或保持原始文件完整性的场景下很有用。

**Q: 如何读取受密码保护的文件？**  
A: 使用包含相同 `AesEcryptionSettings`（密码）的 `Archive` 实例打开归档即可。

**Q: 对文件大小或条目数量有上限吗？**  
A: Aspose.Zip 能处理大文件和成千上万的条目，唯一限制来自系统内存和存储空间。

## 其他资源

- **Aspose.Zip 文档** – 详细的 API 参考请访问 **[此处](https://reference.aspose.com/zip/net/)**。  
- **社区支持** – 在 **[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)** 提问。  
- **免费试用** – 在 **[此处](https://releases.aspose.com/)** 获取试用版。  
- **临时许可证** – 通过 **[此处](https://purchase.aspose.com/temporary-license/)** 申请临时许可证。  
- **购买选项** – 前往 **[此处](https://purchase.aspose.com/buy)** 购买完整许可证。

---

**最后更新：** 2025-12-23  
**测试环境：** Aspose.Zip 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}