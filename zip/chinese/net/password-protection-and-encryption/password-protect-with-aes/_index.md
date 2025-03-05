---
title: 保护您的文件 - 使用 Aspose.Zip 进行 AES 加密
linktitle: 使用 AES 进行密码保护
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 了解如何使用 Aspose.Zip for .NET 和 AES 加密来增强文件安全性。请遵循我们的分步指南以获得最佳保护。
type: docs
weight: 11
url: /zh/net/password-protection-and-encryption/password-protect-with-aes/
---

## 介绍

在当今的数字时代，保护您的敏感文件至关重要，Aspose.Zip for .NET 提供了一个强大的解决方案，使用高级加密标准 (AES) 为您的档案提供密码保护。在本教程中，我们将探讨如何使用三种密钥长度（128 位、192 位和 256 位）实施 AES 加密，以确保压缩文件的最高级别的安全性。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Zip for .NET：确保您已将 Aspose.Zip 库集成到您的 .NET 项目中。你可以下载它[这里](https://releases.aspose.com/zip/net/).

- 文档目录：有一个源文件所在的目录。

## 导入命名空间

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 第 1 步：使用 AES-128 进行密码保护

```csharp
//ExStart：使用 AES128 进行密码保护
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//结束：PasswordProtectWithAES128
```

在此步骤中，我们创建一个 zip 文件并使用 AES-128 加密对其进行保护。密码“p@s$”可确保您的存档的安全。

## 步骤 2：使用 AES-192 进行密码保护

```csharp
//ExStart：使用 AES192 进行密码保护
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//结束：PasswordProtectWithAES192
```

此步骤演示如何实施 AES-192 加密以增强安全性。为了一致性，使用相同的密码“p@s$”。

## 步骤 3：使用 AES-256 进行密码保护

```csharp
//ExStart：使用 AES256 进行密码保护
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//结束：PasswordProtectWithAES256
```

在最后一步中，我们实施最高级别的加密 AES-256，为您的压缩文件提供额外的安全层。

## 结论

在本教程中，我们介绍了在 Aspose.Zip for .NET 中使用 AES 加密来密码保护存档的基本步骤。无论您选择 128 位、192 位还是 256 位加密，您的文件都将受到保护，不会受到未经授权的访问。

## 经常问的问题

### 我可以将 Aspose.Zip for .NET 与其他编程语言一起使用吗？
Aspose.Zip 主要为 .NET 应用程序设计，确保无缝集成和最佳性能。

### AES 加密方法对于敏感数据安全吗？
是的，AES 加密被广泛认为是保护敏感信息的安全可靠的方法。

### 我可以更改已加密存档的密码吗？
不可以，加密存档的密码一旦设置就无法更改。您需要使用不同的密码创建新的加密存档。

### 使用 Aspose.Zip 加密的文件类型是否有任何限制？
Aspose.Zip 支持各种文件类型的加密，确保保护不同类型数据的灵活性。

### 如果我忘记加密存档的密码会怎样？
不幸的是，没有办法恢复加密存档的密码。将密码保存在安全的位置至关重要。
