---
date: 2026-01-28
description: 学习如何使用 Aspose.Zip for .NET 提取带密码的压缩包、将文件压缩为 TarBz2、创建 TarGz 压缩文件。提升存储效率和安全性。
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用密码提取归档并压缩为 TarBz2（.NET）
url: /zh/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}

# 使用密码提取归档并压缩为 TarBz (.NET)

在本指南中，您将了解 **如何使用密码提取归档**，并掌握使用 Aspose.Zip for .NET **压缩文件为 TarBz2** 的方法。无论您是在构建备份服务、云存储客户端，还是数据处理流水线，这些技术都能帮助您减小存储占用、加快传输速度，并保护敏感数据。

## 快速回答
- **什么是 TarBz2？** 一种将 TAR 打包与 BZIP2 压缩相结合的压缩归档，具有高压缩比。  
- **为什么选择 Aspose.Zip for .NET？** 它提供统一、流畅的 API，支持多种归档格式且无需本地依赖。  
- **我可以创建 TarGz 归档吗？** 可以——Aspose.Zip 支持 TarGz、TarLz、TarXz、TarZ 等多种格式。  
- **如何提取受密码保护的归档？** 在提取前为每个 `ArchiveEntry` 设置 `Password` 属性。  
- **生产环境需要许可证吗？** 生产使用需商业许可证，提供免费试用供评估。

## 使用 Aspose.Zip for .NET 提取带密码的归档
提取 **受密码保护的 zip 归档** 非常简单。打开归档，定位所需条目，分配密码，然后调用 `Extract`。此方法同样适用于 TarBz2、TarGz 以及其他受支持的格式。

## “压缩文件为 TarBz2” 实际意味着什么？
将文件压缩为 TarBz2 首先是把多个文件和目录打包成一个 **TAR** 容器，然后使用 **BZIP2** 进行压缩。最终得到的 `.tar.bz2` 文件既易于传输，又具备高度压缩率。

## 为什么使用 Aspose.Zip for .NET 处理这些格式？
- **统一 API** – 一个库，支持多种格式（TarBz2、TarGz、TarLz、TarXz、TarZ）。  
- **无本地依赖** – 在 Windows、Linux、macOS 上开箱即用。  
- **密码支持** – 支持对每个条目单独设置密码，安全提取。  
- **性能导向** – 基于流的处理方式最大限度降低内存占用。

## 前置条件
- .NET 6.0 或更高版本（或 .NET Core 3.1+ / .NET Framework 4.5+）。  
- 已安装 Aspose.Zip for .NET NuGet 包（`Install-Package Aspose.Zip`）。  
- 具备 C# 基础以及文件 I/O 知识。

## 步骤指南

### 步骤 1：选择所需的归档格式
根据压缩比和兼容性需求决定使用 **TarBz2**、**TarGz**、**TarLz**、**TarXz** 或 **TarZ**。  
- **TarBz2** – 最高压缩率，处理速度较慢。  
- **TarGz** – 在速度与体积之间取得良好平衡（涵盖次要关键词 *compress files to targz*）。  
- **TarZ** – 旧版 Unix 工具使用的遗留格式。

### 步骤 2：创建 `Archive` 实例
实例化 `Archive` 类并指向输出文件路径。该对象负责打包和压缩过程。

### 步骤 3：添加文件和文件夹
使用 `AddAll` 或 `AddFile` 方法将需要压缩的文件加入。通过添加基文件夹来保持目录结构。

### 步骤 4：设置所需的压缩类型
在保存归档时指定压缩算法（`CompressionType.BZip2`、`CompressionType.GZip` 等）。这一步即实现 **compress files to tarbz2** 或其他格式。

### 步骤 5：保存归档
调用 `Save` 并传入相应的格式枚举（`ArchiveFormat.TarBz2`、`ArchiveFormat.TarGz` 等）。库会一次性写入 TAR 容器并应用选定的压缩。

### 步骤 6：使用密码提取归档
如果需要 **提取带不同密码的归档条目**（次要关键词 *how to extract password protected archive*），打开归档，定位每个条目，分配其密码，然后进行提取。

### 步骤 7：验证结果
提取后对比文件大小和校验和，确保归档创建和解压均正确。

## 常见使用场景
- **备份工具** – 将每日备份存为 `.tar.bz2`，降低存储成本。  
- **跨平台数据交换** – 基于 Tar 的格式在 Linux、macOS 和 Windows 上均通用。  
- **安全分发** – 为单个条目设置密码，满足合规性要求。

## 故障排除与技巧
- **大归档** – 使用流式 API（`Archive.CreateEntryFromFile`）避免一次性加载整个文件。  
- **密码不匹配** – 确保每个 `ArchiveEntry` 设置的密码与提取时使用的密码一致，否则会抛出 `InvalidPasswordException`。  
- **不支持的压缩级别** – BZIP2 不支持自定义压缩级别；若需更细粒度控制，可考虑 TarLz 或 TarXz。  
- **性能技巧** – 在创建 **create tarbz2 archive** 时，对底层流启用缓冲，可提升写入速度。

## 常见问答

**Q: 如何创建 TarGz 归档？**  
A: 在调用 `Save` 时将压缩类型设为 `CompressionType.GZip`，格式设为 `ArchiveFormat.TarGz`。

**Q: 能在不知道密码的情况下提取受密码保护的归档吗？**  
A: 不能。每个条目必须提供正确的密码，否则提取会失败。

**Q: Aspose.Zip 是否支持对不同条目使用不同密码进行提取？**  
A: 支持。可以在提取前为每个 `ArchiveEntry` 单独分配密码。

**Q: 哪种格式提供最佳压缩率？**  
A: 通常 TarBz2 提供最高压缩比，其次是 TarLz 和 TarXz。TarGz 在速度与体积之间取得平衡。

**Q: 向 TAR 归档中添加的文件数量有限制吗？**  
A: 实际上没有硬性限制，但极大的归档可能需要拆分为多个部分以便更易处理。

## 归档提取与格式教程
### [File Compressing to TarBz2 with Aspose.Zip for .NET](./compress-to-tar-bz2/)
了解如何在 .NET 中使用 Aspose.Zip 将文件压缩为 TarBz2 格式。按照我们的分步指南实现高效压缩。
### [Compressing to TarGz with Aspose.Zip for .NET](./compress-to-tar-gz/)
探索在 .NET 中使用 Aspose.Zip 高效压缩文件为 TarGz。
### [Compressing to TarLz with Aspose.Zip for .NET](./compress-to-tar-lz/)
轻松在 .NET 中使用 Aspose.Zip 压缩文件为 TarLz，逐步学习创建过程。
### [Compressing to TarXz with Aspose.Zip for .NET](./compress-to-tar-xz/)
学习在 .NET 中使用 Aspose.Zip 将文件压缩为 TarXz 格式，获取高效存储与传输的分步指南。
### [Compressing to TarZ with Aspose.Zip for .NET](./compress-to-tar-z/)
探索使用 Aspose.Zip for .NET 将文件压缩为 TarZ 的步骤，提升 .NET 项目中文件处理效率。
### [Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET](./extract-archive-different-passwords/)
了解如何在 Aspose.Zip for .NET 中对不同条目使用不同密码进行提取，提升应用安全性与灵活性。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-28  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose  

---