---
date: 2026-10-25
description: 了解如何使用 Aspose.Zip for .NET 在压缩 tar 文件时提取 zip 密码并设置压缩算法，从而提升存储效率和安全性。
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: 归档提取与格式
og_description: 了解如何使用 Aspose.Zip for .NET 在压缩 tar 文件时提取 zip 密码并设置压缩算法，从而提升存储效率和安全性。
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: 使用 Aspose.Zip 提取 zip 密码并压缩 tar 文件
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: 使用 Aspose.Zip 提取 zip 密码并压缩 tar 文件
url: /zh/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 提取 zip 密码并使用 Aspose.Zip 压缩 tar 文件

## 简介

在本指南中，您将了解 **extract zip password** 技术，学习在创建基于 tar 的归档时如何设置压缩算法，并了解如何使用 Aspose.Zip for .NET 构建 TarGz、TarBz2 等格式。无论您是构建备份服务、云存储客户端，还是数据处理管道，掌握这些操作都能降低存储成本、加快传输速度，并保护敏感文件。

## 快速答案
- **TarBz2 是什么？** 一种压缩归档，将 TAR 打包与 BZIP2 压缩相结合，以实现高压缩比。  
- **为什么选择 Aspose.Zip for .NET？** 它支持 50 多种归档和压缩格式，可在 Windows、Linux 和 macOS 上运行，并在处理数百兆字节的归档时将内存使用保持在 10 MB 以下。  
- **我可以创建 TarGz 归档吗？** 可以 — Aspose.Zip 提供 TarGz、TarLz、TarXz、TarZ 等多种格式。  
- **如何提取受密码保护的 zip 归档？** 在调用 `Extract` 之前，为每个 `ArchiveEntry` 设置 `Password` 属性。  
- **生产环境使用是否需要许可证？** 生产环境需要商业许可证；可使用免费试用版进行评估。

## tar 压缩是什么？

Tar 压缩将 TAR 容器与诸如 BZIP2、GZIP、LZMA 或 XZ 等压缩算法相结合。其结果是一个单一文件（例如 `.tar.gz`、`.tar.bz2`），可在 Linux、macOS 和 Windows 上解压。它保留原始目录层次结构，支持随机访问提取，并且被命令行工具和编程库广泛支持，使其成为跨平台分发和归档存储的理想选择。

## 为什么在 .NET 中使用 Aspose.Zip 处理这些格式？

Aspose.Zip 提供统一、无依赖的 API，支持 **50+** 种归档和压缩格式，包括所有主要的基于 tar 的类型。其流式架构能够处理大于 10 GB 的归档，同时将 RAM 使用保持在 10 MB 以下，适用于高吞吐量的服务器工作负载。  

**直接回答：** 您使用 Aspose.Zip 是因为它让您能够使用单一流畅的 API 创建、压缩和提取基于 tar 的归档以及受密码保护的 zip 文件，无需外部工具，并在内存高效的流模式下处理多吉字节的归档。

## 先决条件
- .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1 或 .NET 5–10。  
- Aspose.Zip for .NET NuGet 包 (`Install-Package Aspose.Zip`)。  
- 熟悉 C# 文件 I/O 和 .NET 项目系统的基础知识。

## 分步指南

### 如何压缩 tar 文件 – 直接回答
创建一个 `Archive` 实例，添加要打包的文件，设置 `CompressionType.BZip2`（或其他算法），然后使用 `ArchiveFormat.TarBz2` 调用 `Save`。库会在一次流式传输中写入 TAR 容器并进行压缩，因而无需将整个归档加载到内存中。

### 步骤 1：选择所需的归档格式
决定哪种基于 tar 的格式最符合您的压缩‑速度权衡：

- **TarBz2** – 最高压缩比（约比 TarGz 小 30 %），但速度较慢。  
- **TarGz** – 在速度和体积之间取得良好平衡；适用于大多数云存储场景。  
- **TarLz / TarXz** – 在适中速度下实现极高压缩，适合归档存储。  
- **TarZ** – 为兼容旧 Unix 工具的传统格式。

### 步骤 2：创建新的 `Archive` 实例
`Archive` 表示单个归档文件，并提供添加条目和保存归档的方法。  

`Archive` 类管理打包和压缩工作流，公开用于添加条目和写入最终文件的方法。

### 步骤 3：添加文件和文件夹
您可以使用 `AddAll` 添加整个目录树，或使用 `AddFile` 添加单个文件。  

`AddAll` 将整个目录树添加到归档中，保留其结构。  
`AddFile` 将单个文件添加到归档中。只需传入基目录路径即可保留原始文件夹层次结构。

### 步骤 4：设置所需的压缩类型
`CompressionType` 枚举指定应用于 TAR 流的压缩算法。  

`CompressionType` 列举了在保存期间将使用的支持算法（BZip2、GZip、LZMA、XZ 等）。

### 步骤 5：保存归档
`ArchiveFormat` 枚举选择输出文件的容器和压缩组合。  

调用 `Save` 使用所选格式将归档写入磁盘。

### 步骤 6：使用密码提取归档
`ArchiveEntry` 表示归档内的单个文件或目录条目。  

要提取受密码保护的 zip，打开归档，定位每个 `ArchiveEntry`，为其分配 `Password` 属性，然后调用 `Extract`。`Password` 属性为 zip 条目设置解密密码。这种每条目密码模型允许您在单个 zip 中保护单独的文件。

### 步骤 7：验证结果
提取后，比较文件大小和 SHA‑256 校验和，以确认归档往返过程保持了数据完整性。

## 常见用例
- **Backup utilities** – 将每日备份存储为 `.tar.bz2`，可将存储成本降低至 30 % 以内。  
- **Cross‑platform data exchange** – 基于 tar 的格式被 Linux、macOS 和 Windows 工具原生支持。  
- **Secure distribution** – 为敏感条目分配密码，满足合规要求，无需额外加密工具。

## 故障排除与技巧
- **Large archives** – 使用流式 API（`Archive.CreateEntryFromFile`）以保持低内存使用。  
- **Password mismatches** – 每个 `ArchiveEntry` 设置的密码必须完全匹配，否则会抛出 `InvalidPasswordException`。  
- **Compression level** – BZIP2 不提供自定义级别；如果需要更细粒度的控制，可切换到 LZMA（`CompressionType.LZMA`）或 XZ（`CompressionType.XZ`）。

## 常见问题

**Q: 如何创建 TarGz 归档？**  
A: 在调用 `Save` 时设置 `CompressionType.GZip` 并使用 `ArchiveFormat.TarGz`。这将在一步完成生成 `.tar.gz` 文件。

**Q: 我可以在不知道密码的情况下提取受密码保护的归档吗？**  
A: 不能。每个条目必须提供正确的密码，否则提取会因 `InvalidPasswordException` 而失败。

**Q: Aspose.Zip 是否支持对每个条目使用不同密码进行提取？**  
A: 支持。在调用 `Extract` 之前，单独为每个 `ArchiveEntry` 分配密码。

**Q: 哪种格式提供最佳压缩率？**  
A: 通常 TarBz2 能得到最小体积，其次是 TarLz 和 TarXz。TarGz 提供更快且仍然有效的替代方案。

**Q: 向 TAR 归档添加的文件数量是否有限制？**  
A: 实际上没有限制，但极大的归档（>10 GB）可能通过拆分为多个部分来更易处理。

## 归档提取和格式教程
### [使用 Aspose.Zip for .NET 将文件压缩为 TarBz2](./compress-to-tar-bz2/)
了解如何在 .NET 中使用 Aspose.Zip 将文件压缩为 TarBz2 格式。遵循我们的分步指南，实现高效的文件压缩。  
### [使用 Aspose.Zip for .NET 压缩为 TarGz](./compress-to-tar-gz/)
在 .NET 中使用 Aspose.Zip 探索高效的文件压缩。轻松压缩为 TarGz。  
### [使用 Aspose.Zip for .NET 压缩为 TarLz](./compress-to-tar-lz/)
在 .NET 中使用 Aspose.Zip 轻松压缩文件。学习逐步创建 TarLz 归档。  
### [使用 Aspose.Zip for .NET 压缩为 TarXz](./compress-to-tar-xz/)
了解如何在 .NET 中使用 Aspose.Zip 将文件压缩为 TarXz 格式。遵循我们的指南，实现高效存储和传输。  
### [使用 Aspose.Zip for .NET 压缩为 TarZ](./compress-to-tar-z/)
探索使用 Aspose.Zip for .NET 步骤式压缩为 TarZ。为您的 .NET 项目提供高效的文件处理。  
### [在 Aspose.Zip for .NET 中使用不同密码提取归档条目](./extract-archive-different-passwords/)
了解如何在 Aspose.Zip for .NET 中使用不同密码提取归档条目。提升您应用程序的安全性和灵活性。

## 相关教程

- [使用 Aspose.Zip for .NET 创建 tar 归档并向 tar 添加文件](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [使用 Aspose.Zip for .NET 压缩 tar 并创建 TarBz2](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [使用 Aspose.Zip 向 tar 添加文件并创建 tarxz 归档](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**最后更新：** 2026-10-25  
**测试版本：** Aspose.Zip for .NET 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}