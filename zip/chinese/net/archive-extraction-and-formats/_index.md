---
date: 2026-06-19
description: 了解如何使用 Aspose.Zip for .NET 压缩 tar 文件、创建 targz 存档以及提取受密码保护的 zip 文件——提升存储效率和安全性。
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: 归档提取与格式
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 使用 Aspose.Zip for .NET 压缩 Tar 文件的方法
url: /zh/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 压缩 Tar 文件

## 介绍

在本指南中，您将了解**压缩 tar**文件，使用 Aspose.Zip for .NET，学习创建 TarGz 存档，并了解如何提取受密码保护的 zip 存档。高效的存档处理是现代 .NET 开发者的核心技能——无论您是在构建备份服务、云存储客户端，还是数据处理流水线，掌握这些格式都能降低存储成本、加快传输速度，并保护敏感数据安全。

## 快速答案
- **TarBz2 是什么？** 一种压缩归档，将 TAR 打包与 BZIP2 压缩相结合，以实现高压缩比。  
- **为什么选择 Aspose.Zip for .NET？** 它提供了一个统一、流畅的 API，用于创建和提取多种归档格式，无需外部依赖。  
- **我可以创建 TarGz 存档吗？** 是的——Aspose.Zip 支持 TarGz、TarLz、TarXz、TarZ 等。  
- **如何提取受密码保护的 zip 存档？** 在提取时使用 `ArchiveEntry` 对象的 `Password` 属性。  
- **生产使用需要许可证吗？** 生产环境需要商业许可证；可使用免费试用版进行评估。

## 什么是 Tar 压缩？

Tar（磁带归档）是一种容器格式，可将多个文件和目录打包成单个流而不进行压缩。当您使用 BZIP2、GZip、LZMA 或 XZ 等压缩算法时，结果就是 **基于 tar 的归档**，如 `.tar.bz2`、`.tar.gz`、`.tar.lz` 等。这些格式在 Linux、macOS 和 Windows 上得到广泛支持，因而非常适合跨平台数据交换。

## 为什么在 .NET 中使用 Aspose.Zip 处理这些格式？

Aspose.Zip 提供了 **统一、无依赖的 API**，支持 50 多种归档和压缩格式，包括 TarBz2、TarGz、TarLz、TarXz 和 TarZ。它可在 Windows、Linux 和 macOS 上运行，其基于流的架构即使在处理数百兆字节的归档时，内存使用也保持在 10 MB 以下。内置的密码保护允许对每个条目进行加密，无需额外库。

## 前提条件
- .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 或 .NET 5–10。  
- 已安装 Aspose.Zip for .NET NuGet 包（`Install-Package Aspose.Zip`）。  
- 对 C# 文件 I/O 和 .NET 项目系统有基本了解。

## 分步指南

### 如何压缩 Tar 文件 – 直接答案
`Archive` 表示一个归档文件，并提供添加条目和保存的方式。创建一个 `Archive` 实例，添加要打包的文件，设置 `CompressionType.BZip2`，并使用 `ArchiveFormat.TarBz2` 调用 `Save`。库在单次流式传输中写入 TAR 容器并进行压缩，因此您永远不会将整个归档加载到内存中。

### 步骤 1：选择所需的归档格式
确定哪种基于 tar 的格式最符合您的压缩‑速度权衡：
- **TarBz2** – 最高压缩比（约比 TarGz 小 30 %），但速度较慢。  
- **TarGz** – 在速度和体积之间取得良好平衡；适用于大多数云存储场景。  
- **TarLz / TarXz** – 极高压缩率且速度适中，适用于归档存储。  
- **TarZ** – 传统格式，兼容旧版 Unix 工具。

### 步骤 2：创建新的 `Archive` 实例
`Archive` 是表示内存中单个归档文件的顶层对象。`Archive` 类管理打包和压缩工作流，提供添加条目和写入最终文件的方法。

### 步骤 3：添加文件和文件夹
您可以使用 `AddAll` 添加整个目录树，或使用 `AddFile` 添加单个文件。只需传入基目录路径，即可保留原始文件夹层次结构。

### 步骤 4：设置所需的压缩类型
`CompressionType` 列举了受支持的算法。`CompressionType` 定义了在保存期间将应用于 TAR 流的算法（BZip2、GZip、LZMA、XZ 等）。

### 步骤 5：保存归档
`ArchiveFormat` 是一个枚举集合（例如 `TarBz2`、`TarGz`），用于告诉写入器使用哪种容器和压缩方式。调用 `Save` 使用选定的格式将归档写入磁盘。

### 步骤 6：使用密码提取归档
`ArchiveEntry` 表示归档内的单个文件或目录条目。要提取受密码保护的 zip，打开归档，定位每个 `ArchiveEntry`，为其分配 `Password` 属性，然后调用 `Extract`。这种每条目密码模型允许您在单个 zip 中保护各个文件。

### 步骤 7：验证结果
提取后，比较文件大小和 SHA‑256 校验和，以确认归档往返过程保持了数据完整性。

## 常见使用场景
- **备份工具** – 将每日备份存储为 `.tar.bz2`，可将存储成本降低最高达 30 %。  
- **跨平台数据交换** – 基于 Tar 的格式被 Linux、macOS 和 Windows 工具原生支持。  
- **安全分发** – 为敏感条目分配密码，满足合规要求，无需额外加密工具。

## 故障排除与技巧
- **大型归档** – 优先使用流式 API（`Archive.CreateEntryFromFile`）以保持低内存使用。  
- **密码不匹配** – 每个 `ArchiveEntry` 设置的密码必须完全匹配，否则会抛出 `InvalidPasswordException`。  
- **压缩级别** – BZIP2 不提供自定义级别；如果需要更细粒度的控制，请切换到 LZMA（`CompressionType.LZMA`）或 XZ（`CompressionType.XZ`）。

## 常见问题

**问：如何创建 TarGz 存档？**  
答：在调用 `Save` 时将 `CompressionType.GZip` 设置为压缩类型，并使用 `ArchiveFormat.TarGz`。这将在一步完成生成 `.tar.gz` 文件。

**问：我可以在不知道密码的情况下提取受密码保护的归档吗？**  
答：不能。每个条目必须提供正确的密码，否则提取会因 `InvalidPasswordException` 而失败。

**问：Aspose.Zip 是否支持对每个条目使用不同密码提取归档？**  
答：是的。在调用 `Extract` 之前，单独为每个 `ArchiveEntry` 分配密码。

**问：哪种格式提供最佳压缩？**  
答：通常 TarBz2 能得到最小体积，其次是 TarLz 和 TarXz。TarGz 提供更快且仍然有效的替代方案。

**问：向 TAR 归档中添加的文件数量是否有限制？**  
答：实际上没有限制，但极大的归档（>10 GB）可能受益于拆分为多个部分，以便更易处理。

## 归档提取与格式教程
### [使用 Aspose.Zip for .NET 将文件压缩为 TarBz2](./compress-to-tar-bz2/)
了解如何在 .NET 中使用 Aspose.Zip 将文件压缩为 TarBz2 格式。遵循我们的分步指南，实现高效的文件压缩。  
### [使用 Aspose.Zip for .NET 压缩为 TarGz](./compress-to-tar-gz/)
探索在 .NET 中使用 Aspose.Zip 进行高效文件压缩。轻松压缩为 TarGz。  
### [使用 Aspose.Zip for .NET 压缩为 TarLz](./compress-to-tar-lz/)
在 .NET 中使用 Aspose.Zip 轻松压缩文件。学习逐步创建 TarLz 归档。  
### [使用 Aspose.Zip for .NET 压缩为 TarXz](./compress-to-tar-xz/)
了解如何在 .NET 中使用 Aspose.Zip 将文件压缩为 TarXz 格式。遵循我们的指南，实现高效存储与传输。  
### [使用 Aspose.Zip for .NET 压缩为 TarZ](./compress-to-tar-z/)
探索使用 Aspose.Zip for .NET 步骤式压缩为 TarZ。为您的 .NET 项目提供高效文件处理。  
### [在 Aspose.Zip for .NET 中使用不同密码提取归档条目](./extract-archive-different-passwords/)
了解如何在 Aspose.Zip for .NET 中使用不同密码提取归档条目。提升应用程序的安全性和灵活性。

---

**最后更新：** 2026-06-19  
**测试版本：** Aspose.Zip for .NET 24.11  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Zip for .NET 创建 tar 归档并添加文件](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [如何使用 Aspose.Zip for .NET 压缩 tar 并创建 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [使用 Aspose.Zip 将文件添加到 tar 并创建 tarxz 归档](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}