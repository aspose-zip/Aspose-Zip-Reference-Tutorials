---
date: 2026-02-20
description: 了解如何压缩 tarbz2 文件、创建 targz 归档，以及使用 Aspose.Zip for .NET 进行 .NET 归档解压和密码保护的
  zip 解压。提升存储效率和安全性。
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 如何使用 Aspose.Zip for .NET 压缩 TarBz2 文件
url: /zh/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Zip for .NET 压缩 TarBz2 文件

## Introduction

在本指南中，您将学习 **如何使用 Aspose.Zip for .NET 压缩 tarbz2 文件**，同时了解如何创建 TarGz 存档以及执行 .net 对受密码保护的 zip 文件的解压缩。高效的文件处理是现代 .NET 开发的基石，掌握这些格式可以帮助您降低存储成本、加快数据传输并保护敏感信息安全。无论您是在构建备份服务、云存储客户端，还是数据处理流水线，本指南所涵盖的技术都能让您的文件管理任务更加顺畅可靠。

## Quick Answers
- **TarBz2 是什么？** 一种压缩归档，结合了 TAR 打包和 BZIP2 压缩，以实现高压缩比。  
- **为什么选择 Aspose.Zip for .NET？** 它提供了一个统一、流式的 API，可创建和提取多种归档格式，无需外部依赖。  
- **我可以创建 TarGz 存档吗？** 可以——Aspose.Zip 支持 TarGz、TarLz、TarXz、TarZ 等格式。  
- **如何提取受密码保护的 zip 存档？** 在提取时使用 `ArchiveEntry` 对象的 `Password` 属性。  
- **生产环境是否需要许可证？** 生产环境需要商业许可证；可免费试用以进行评估。

## How to Compress TarBz2 Files
将文件压缩为 TarBz2 意味着首先将多个文件和目录打包成一个 **TAR** 容器，然后再进行 **BZIP2** 压缩。最终得到的 `.tar.bz2` 文件既便于传输，又具备高度压缩率。

## Why Use Aspose.Zip for .NET to Handle These Formats?
- **统一 API** – 单一库，支持多种格式（TarBz2、TarGz、TarLz、TarXz、TarZ）。  
- **无本地依赖** – 开箱即用，支持 Windows、Linux 和 macOS。  
- **密码支持** – 使用每个条目的密码安全地保护和提取归档。  
- **性能导向** – 基于流的处理最小化内存占用。

## Prerequisites
- .NET 6.0 或更高（或 .NET Core 3.1+ / .NET Framework 4.5+）。  
- 已安装 Aspose.Zip for .NET NuGet 包（`Install-Package Aspose.Zip`）。  
- 具备 C# 和文件 I/O 的基本了解。

## Step‑by‑Step Guide

### Step 1: Choose the archive format you need
决定 **TarBz2**、**TarGz**、**TarLz**、**TarXz** 或 **TarZ** 中哪种最符合您的压缩比和兼容性需求。  
- **TarBz2** – 压缩率最高，处理速度较慢。  
- **TarGz** – 在速度和体积之间取得良好平衡（涵盖次要关键词 *how to create targz*）。  
- **TarZ** – 传统格式，适用于与旧版 Unix 工具的兼容性。

### Step 2: Create a new `Archive` instance
实例化 `Archive` 类并指向输出文件路径。该对象将管理打包和压缩过程。

### Step 3: Add files and folders
使用 `AddAll` 或 `AddFile` 方法添加要压缩的文件。通过添加基文件夹可以保留目录结构。

### Step 4: Set the desired compression type
在保存归档时指定压缩算法（`CompressionType.BZip2`、`CompressionType.GZip` 等）。这一步实际上是 **将文件压缩为 TarBz2** 或其他格式。

### Step 5: Save the archive
调用 `Save` 并使用相应的格式枚举（`ArchiveFormat.TarBz2`、`ArchiveFormat.TarGz` 等）。库将在一次操作中写入 TAR 容器并应用所选压缩。

### Step 6: Extracting archives with passwords
如果需要 **使用不同密码提取归档条目**（次要关键词 *password protected zip extraction*），打开归档，定位每个条目，分配其密码，然后进行提取。

### Step 7: Verify the result
提取后，对比文件大小和校验和，以确保归档创建和解压正确。

## Common Use Cases
- **备份工具** – 将每日备份存储为 `.tar.bz2`，以降低存储成本。  
- **跨平台数据交换** – 基于 Tar 的格式在 Linux、macOS 和 Windows 上均被通用支持。  
- **安全分发** – 为单个条目设置密码，以满足合规性需求的环境。

## Troubleshooting & Tips
- **大型归档** – 使用流式 API（`Archive.CreateEntryFromFile`）避免将整个文件加载到内存中。  
- **密码不匹配** – 确保每个 `ArchiveEntry` 设置的密码与提取时使用的密码一致，否则会抛出 `InvalidPasswordException`。  
- **不支持的压缩级别** – BZIP2 不支持自定义压缩级别；如果需要更细粒度的控制，可考虑 TarLz 或 TarXz。

## Frequently Asked Questions

**问：如何创建 TarGz 存档？**  
答：在调用 `Save` 时将压缩类型设为 `CompressionType.GZip`，格式设为 `ArchiveFormat.TarGz`。

**问：是否可以在不知道密码的情况下提取受密码保护的归档？**  
答：不能。每个条目必须提供正确的密码，否则提取会失败。

**问：Aspose.Zip 是否支持对每个条目使用不同密码进行提取？**  
答：支持。您可以在提取前为每个 `ArchiveEntry` 单独分配密码。

**问：哪种格式提供最佳压缩率？**  
答：TarBz2 通常提供最高的压缩比，其次是 TarLz 和 TarXz。TarGz 在速度与体积之间提供良好平衡。

**问：向 TAR 归档中添加的文件数量是否有限制？**  
答：实际上没有限制，但极大的归档可能通过拆分为多个部分以便更易处理。

## Archive Extraction and Formats Tutorials
### [使用 Aspose.Zip for .NET 将文件压缩为 TarBz2](./compress-to-tar-bz2/)
了解如何使用 Aspose.Zip for .NET 将文件压缩为 TarBz2 格式。按照我们的分步指南实现高效的文件压缩。
### [使用 Aspose.Zip for .NET 压缩为 TarGz](./compress-to-tar-gz/)
探索在 .NET 中使用 Aspose.Zip 进行高效文件压缩。轻松压缩为 TarGz。
### [使用 Aspose.Zip for .NET 压缩为 TarLz](./compress-to-tar-lz/)
在 .NET 中使用 Aspose.Zip 轻松压缩文件。一步步学习创建 TarLz 归档。
### [使用 Aspose.Zip for .NET 压缩为 TarXz](./compress-to-tar-xz/)
学习如何使用 Aspose.Zip for .NET 将文件压缩为 TarXz 格式。按照我们的分步指南实现高效的文件存储和传输。
### [使用 Aspose.Zip for .NET 压缩为 TarZ](./compress-to-tar-z/)
探索使用 Aspose.Zip for .NET 对 TarZ 进行分步压缩。为您的 .NET 项目实现高效的文件处理。
### [在 Aspose.Zip for .NET 中使用不同密码提取归档条目](./extract-archive-different-passwords/)
了解如何在 Aspose.Zip for .NET 中使用不同密码提取归档条目。提升您应用程序的安全性和灵活性。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-02-20  
**测试环境：** Aspose.Zip for .NET 24.11  
**作者：** Aspose