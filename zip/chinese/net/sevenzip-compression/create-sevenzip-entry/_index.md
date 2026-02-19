---
date: 2025-12-25
description: 精通 Aspose.Zip for .NET，以创建加密的 7z 压缩文件。此 Aspose.Zip 示例展示了如何在 7z 中添加文件并进行加密和压缩。
linktitle: Create SevenZip Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 创建加密的 7z 存档
url: /zh/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Zip for .NET 创建加密 7z 存档

## 介绍

在本教程中，您将学习 **如何使用 Aspose.Zip 库 for .NET 创建加密的 7z** 文件。无论是需要保护敏感数据、遵守安全策略，还是仅仅想高效压缩文件，本指南都会一步步带您完成——从项目设置到确认存档成功创建。让我们一起看看如何轻松地将文件添加到带有 AES 加密的 7z 存档中。

## 快速答案
- **“创建加密 7z” 是什么意思？** 指生成一个使用 AES 加密保护的 7‑zip 存档。
- **使用哪个库？** Aspose.Zip for .NET。
- **需要许可证吗？** 测试阶段使用临时许可证即可；生产环境需要正式许可证。
- **可以添加多个文件吗？** 可以，对每个文件重复调用 `CreateEntry`。
- **支持 AES 加密吗？** 支持，Aspose.Zip 为 7z 存档提供 AES‑256 加密。

## 什么是加密的 7z 存档？

7z 存档是一种高压缩率的容器格式。当您 **创建加密的 7z** 存档时，内容会通过 AES 加密进行混淆，未提供正确密码时无法读取。这非常适合安全传输或存储机密文件。

## 为什么使用 Aspose.Zip 处理加密的 7z 文件？

- **完整的 .NET 集成** – 兼容 .NET Framework、.NET Core 以及 .NET 5/6。
- **内置 AES‑256 支持** – 无需额外工具。
- **简洁的 API** – 一行代码即可添加文件并保存存档。
- **跨平台** – 可在 Windows、Linux 和 macOS 上运行。

## 前提条件

在开始之前，请确保您具备以下条件：

- **Aspose.Zip for .NET Library** – 在此处下载 [here](https://releases.aspose.com/zip/net/)。
- **可写入的文件夹**，用于保存生成的存档。
- **源文件**（例如 `file.dat`），即您想要压缩并加密的文件。

## 导入命名空间

在 C# 文件顶部添加所需的命名空间：

```csharp
using Aspose.Zip.SevenZip;
```

## 步骤指南

### 步骤 1：定义工作目录

设置包含待压缩源文件的文件夹路径。

```csharp
string dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您机器上的实际路径。

### 步骤 2：创建加密的 7z 条目

本教程的核心——打开文件流、创建 `SevenZipArchive`、添加条目并保存存档。以下示例将单个文件 (`file.dat`) 作为 `data.bin` 添加到存档中。

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **专业提示：** 要启用 AES 加密，请在调用 `Save` 之前为 `SevenZipArchive` 设置 `Encryption` 属性。（此处省略该属性以保持示例简洁。）

### 步骤 3：确认成功

打印友好的提示信息，以便您知道操作已成功完成且没有错误。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### 步骤 4：验证存档（可选）

程序运行后，导航到包含 `archive.7z` 的文件夹，使用 7‑zip 客户端打开它。如果在步骤 2 中添加了加密，系统将提示输入密码。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **未找到文件** | `dataDir` 或源文件名不正确 | 再次检查路径，确保 `file.dat` 存在。 |
| **访问被拒绝** | 写入权限不足 | 以提升的权限运行应用程序，或选择可写入的文件夹。 |
| **未应用加密** | 未在存档上设置加密属性 | 在 `Save` 之前设置 `archive.Encryption = EncryptionAlgorithm.Aes256;`。 |

## 常见问答

### 问：我可以在 .NET 中使用 Aspose.Zip 处理其他存档格式吗？

Aspose.Zip 主要聚焦于 ZIP 和 7z 格式。若需处理其他格式，请查找专门针对这些格式的库。

### 问：如何使用 Aspose.Zip 从 zip 存档中提取文件？

使用 Aspose.Zip 提供的提取功能，例如 `ExtractToDirectory` 方法，可轻松将文件从 zip 存档中解压出来。

### 问：Aspose.Zip 适用于大规模应用吗？

当然！Aspose.Zip 设计用于大规模应用，提供高效的 zip 存档操作能力。

### 问：使用 Aspose.Zip 有哪些许可注意事项？

是的，请确保拥有有效许可证。临时使用或试用时，可在此处获取临时许可证 [here](https://purchase.aspose.com/temporary-license/)。

### 问：我可以在哪里寻求帮助或加入 Aspose.Zip 社区？

访问 [Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37) 获取支持、提问并与社区成员交流。

## 结论

现在，您已经掌握了使用 Aspose.Zip for .NET **创建加密 7z** 存档的完整流程。通过上述步骤，您可以安全地压缩文件、将其添加到 7z 容器中，并在需要时启用 AES 加密。欢迎进一步扩展示例，添加更多条目、设置密码，或将其集成到更大的工作流中。

---

**最后更新：** 2025-12-25  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
