---
date: 2026-03-08
description: 了解如何使用 Aspose.Zip for .NET 对 zip 压缩包进行密码保护，存储多个文件而不进行压缩，并使用 AES 加密实现
  zip 文件的密码保护。
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET - 对 Zip 存档进行密码保护并在不压缩的情况下存储多个文件
url: /zh/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

 bullet points.

Tables: translate headers and cells.

Make sure to keep markdown formatting.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET - 密码保护 Zip 存档教程

在现代 .NET 开发中，安全地归档文件是常见需求。使用 **Aspose.Zip for .NET**，您可以 **对 zip 存档进行密码保护**，在不进行压缩的情况下存储多个项目，并应用强大的 AES 加密——只需几行 C# 代码。本教程将逐步演示如何创建一个包含多个文件、使用 *store*（无压缩）模式且受密码锁定的 zip。

## 快速答案
- **“密码保护 zip 存档” 是什么意思？** 它会加密 zip 内容，只有使用正确密码才能打开。  
- **使用哪种加密算法？** 通过 `AesEcryptionSettings` 使用 AES‑256。  
- **可以添加多个文件吗？** 可以——为每个源文件重复调用 `CreateEntry`。  
- **生产环境需要许可证吗？** 需要商业许可证；提供免费试用。  
- **在 .NET 6/7 上受支持吗？** 完全支持——Aspose.Zip 可在 .NET Framework、.NET Core 以及 .NET 5/6/7 上运行。

## 什么是密码保护 zip 存档？
*密码保护 zip 存档* 是指使用用户自定义密码对 ZIP 文件的条目进行加密。打开存档时必须提供密码，否则内容不可读取。Aspose.Zip 通过 AES‑256 加密实现此功能，为敏感数据提供强安全性。

## 为什么要使用 Aspose.Zip 的 zip 文件密码保护？
- **无压缩存储** – `StoreCompressionSettings` 保持原始文件大小，适用于已压缩的媒体文件。  
- **强加密** – AES‑256 可抵御暴力破解攻击。  
- **完整的 .NET 集成** – 支持 .NET Framework、.NET Core 以及 .NET 5/6/7，无需本地依赖。  
- **简洁 API** – 创建存档、设置密码、添加条目并保存，仅需几行代码。

## 前置条件

在开始编写代码之前，请确保您已：

- **安装 Aspose.Zip for .NET**。您可以在此处下载 [here](https://releases.aspose.com/zip/net/)。  
- 准备一个包含待归档文件的文件夹。下面示例中，变量 `dataDir` 指向该文件夹。

## 导入命名空间

首先，将所需的命名空间引入作用域：

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 如何对 zip 存档进行密码保护并在无压缩模式下存储多个文件

以下为逐步指南。每一步均包含简短说明以及原始代码块（保持不变）。

### 步骤 1：打开 Zip 文件

我们创建一个 `FileStream` 来保存生成的存档。

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

### 步骤 2：打开源文件

打开要添加到存档的第一个文件。若需添加更多文件，可重复此块代码。

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

### 步骤 3：创建使用 Store 压缩和 AES 加密的存档

在这里我们将存档配置为 **store**（无压缩）文件，并使用 AES‑256 实现 **zip 文件密码保护**。

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

### 步骤 4：创建存档条目并保存 – *create archive entry c#*

现在将文件添加到存档并将加密后的 zip 写入磁盘。

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

> **专业提示：** 若要添加更多文件，只需在 `archive.Save(zipFile);` 之前调用 `archive.CreateEntry("anotherFile.txt", anotherStream);`。

## 常见问题及解决方案

| 问题 | 原因 | 解决办法 |
|------|------|----------|
| **“Invalid password” 异常** | 密码错误或加密方式不匹配。 | 确保 `AesEcryptionSettings` 中的密码字符串与打开 zip 时使用的密码一致，并验证使用了 `EncryptionMethod.AES256`。 |
| **文件大小大于预期** | 意外使用了压缩。 | 确认使用的是 `StoreCompressionSettings`（无压缩），而非 `DeflateCompressionSettings`。 |
| **流未关闭** | `using` 语句缺少闭合括号。 | 确保每个 `using` 块都正确闭合；示例代码展示了正确的嵌套方式。 |

## 常见问答

**问：我可以在 Aspose.Zip for .NET 中使用其他加密方式吗？**  
答：可以，Aspose.Zip 支持多种加密算法，包括 AES‑128 和 ZipCrypto。详细信息请参阅文档 [here](https://reference.aspose.com/zip/net/)。

**问：在哪里可以获得 Aspose.Zip for .NET 的支持？**  
答：访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取社区帮助和官方支持。

**问：Aspose.Zip for .NET 是否提供免费试用？**  
答：是的，您可以在此处获取免费试用 [here](https://releases.aspose.com/)。  

**问：如何获取 Aspose.Zip for .NET 的临时许可证？**  
答：请在此处申请临时许可证 [here](https://purchase.aspose.com/temporary-license/)。  

**问：在哪里可以购买 Aspose.Zip for .NET？**  
答：您可以在此处购买 Aspose.Zip for .NET [here](https://purchase.aspose.com/buy)。  

## 结论

本指南演示了如何使用 Aspose.Zip for .NET **对 zip 存档进行密码保护**、在无压缩模式下存储多个项目，并通过 AES‑256 加密确保安全。按照这些步骤，您即可保护敏感数据、满足合规要求，并保持存档轻量。欢迎尝试添加更多文件、更改密码或切换其他加密方式——Aspose.Zip 让这一切变得简单直观。

---

**最后更新：** 2026-03-08  
**测试环境：** Aspose.Zip for .NET 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}