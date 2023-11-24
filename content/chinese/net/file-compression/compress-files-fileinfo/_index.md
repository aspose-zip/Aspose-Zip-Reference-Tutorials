---
title: 使用 Aspose.Zip for .NET 中的 FileInfo 压缩文件
linktitle: 使用 FileInfo 压缩文件
second_title: 用于文件压缩和归档的 Aspose.Zip .NET API
description: 学习使用 Aspose.Zip for .NET 的 fileinfo 来压缩文件。请按照我们的分步指南进行高效的文件管理。
type: docs
weight: 11
url: /zh/net/file-compression/compress-files-fileinfo/
---
## 介绍

欢迎来到我们关于使用 Aspose.Zip for .NET 压缩文件的综合指南！如果您希望优化文件存储或传输，Aspose.Zip 是您的首选解决方案。在本教程中，我们将引导您完成使用 FileInfo 类压缩文件的过程，并提供详细的分步指南。让我们深入了解吧！

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

1.  Aspose.Zip for .NET：确保您已安装 Aspose.Zip 库。您可以从[网站](https://releases.aspose.com/zip/net/).

2. 文档目录：在系统上设置一个目录来存储要压缩的文件。

## 导入命名空间

在您的 .NET 项目中，包含必要的命名空间：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## 第 1 步：设置您的文档目录

首先，定义存储文档的目录。您可以使用以下代码：

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：使用 FileInfo 压缩文件

现在，让我们进入该流程的核心。我们将使用`FileInfo`类与 Aspose.Zip 一起压缩文件。按着这些次序：

### 步骤 2.1：打开 Zip 文件

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 步骤2.2：创建FileInfo对象

创造`FileInfo`您要压缩的文件的对象：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### 步骤2.3：创建存档并添加条目

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 步骤 2.4：保存 Zip 文件

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

恭喜！您已使用 Aspose.Zip for .NET 中的 FileInfo 类成功压缩文件。

## 结论

在本教程中，我们探索了如何使用 Aspose.Zip for .NET 高效地压缩文件。通过执行以下步骤，您可以增强文件管理功能并优化空间使用。尝试不同的文件类型和大小，体验 Aspose.Zip 的全部潜力。

## 常见问题解答

### Q1：Aspose.Zip 是否兼容所有文件类型？

A1：Aspose.Zip 支持多种文件类型，确保压缩的多功能性。

### Q2：我可以将Aspose.Zip用于商业项目吗？

 A2：当然！访问我们的[购买页面](https://purchase.aspose.com/buy)探索许可选项。

### Q3：如何获得 Aspose.Zip 的支持？

 A3：加入我们的社区[Aspose.Zip 论坛](https://forum.aspose.com/c/zip/37)寻求帮助和讨论。

### Q4：有免费试用吗？

 A4: 是的，你可以抓住你的[在这里免费试用](https://releases.aspose.com/).

### Q5：如何获得 Aspose.Zip 的临时许可证？

 A5：参观[这个链接](https://purchase.aspose.com/temporary-license/)有关获得临时许可证的信息。