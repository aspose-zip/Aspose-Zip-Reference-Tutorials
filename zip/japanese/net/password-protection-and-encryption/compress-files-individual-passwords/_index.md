---
date: 2026-03-02
description: Aspose.Zip を使用して .NET でパスワード保護された zip アーカイブの作成方法と、パスワードでファイルを圧縮する方法を学びましょう。ステップバイステップのガイドに従ってください。
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET と Aspose.Zip を使用してパスワード保護された ZIP アーカイブを作成する
url: /ja/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip を使用した .NET でのパスワード保護 ZIP アーカイブの作成

## Introduction

機密データを共有する必要があるとき、**パスワード保護された zip アーカイブ**は、情報を安全に保つ最もシンプルで効果的な方法のひとつです。.NET アプリケーションでは、Aspose.Zip を使うことで **パスワード付きでファイルを圧縮**でき、各ファイルに個別の暗号化キーを付与できます。このチュートリアルでは、実際にそのようなアーカイブを作成する方法、重要性、そして実際のプロジェクトでの活用例を学びます。

## Quick Answers
- **What library should I use?** Aspose.Zip for .NET provides built‑in support for per‑file passwords and multiple encryption methods.  
- **How many lines of code?** About 30 lines, including setup and saving the archive.  
- **Can each file have a different password?** Yes – you can assign a unique password to every entry.  
- **Which encryption methods are available?** Traditional ZipCrypto, AES‑128, and AES‑256.  
- **Do I need a license for production?** A commercial license is required for production use; a free trial is available.

## What is a password protected zip archive?
パスワード保護された zip アーカイブとは、内容を展開する際にパスワードが必要な圧縮ファイル（ZIP）のことです。パスワードはアーカイブ全体または個々のエントリに設定でき、AES‑128/256 などの最新アルゴリズムにより強力な暗号化が提供されます。

## Why compress files with passwords using Aspose.Zip?
- **Granular security** – assign a distinct password per file, ideal for multi‑tenant scenarios.  
- **Multiple encryption standards** – choose between legacy ZipCrypto and strong AES.  
- **No external tools** – everything is handled programmatically within your .NET codebase.  
- **Performance** – fast compression with Deflate while keeping the archive size small.

## Prerequisites

開始する前に、以下が揃っていることを確認してください。

- **Aspose.Zip for .NET** – install the library in your project. Detailed docs are available [here](https://reference.aspose.com/zip/net/).  
- **Download the latest package** if you haven’t already, from [this link](https://releases.aspose.com/zip/net/).  
- 圧縮したいファイルが入っているフォルダー。

## Import Namespaces

Add the required namespaces at the top of your C# file:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Step 1: Set the Resource Directory Path

Point the code to the folder that holds the source files:

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Compress Files with Individual Passwords

Now we’ll create a **password protected zip archive** where each file uses its own password and encryption method. The example uses three sample files (`alice29.txt`, `asyoulik.txt`, and `fields.c`) with different passwords.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### How it works
- **CreateEntry** adds a file to the archive.  
- The fourth argument (`ArchiveEntrySettings`) lets you specify both compression (`DeflateCompressionSettings`) and encryption (`TraditionalEncryptionSettings` or `AesEcryptionSettings`).  
- By passing a different password string for each entry, you end up with a **password protected zip archive** where every file is unlocked only with its own key.

## Common Issues & Troubleshooting

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| “Wrong password” エラーで抽出に失敗する | パスワードが一致しない、または暗号化方式が異なる | 正確なパスワード文字列を確認し、抽出時に同じ `EncryptionMethod` を使用しているか確認してください。 |
| アーカイブサイズが予想より大きい | 小さなテキストファイルに AES‑256 を使用するとオーバーヘッドが増える | 小規模ファイルには AES‑128 で十分な場合が多く、サイズも小さくなります。 |
| `archive.Save` 実行時に例外が発生する | 出力先フォルダーへの書き込み権限がない | アプリケーションが `dataDir` に書き込み権限を持っているか確認するか、別の出力パスを使用してください。 |

## Frequently Asked Questions (FAQs)

### Can I use different encryption methods for each file?
Yes, Aspose.Zip for .NET allows you to mix encryption methods—traditional ZipCrypto, AES‑128, and AES‑256—on a per‑file basis.

### Is there a trial version available?
Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).

### How can I get support if I encounter issues?
Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance from the community and Aspose support.

### Where can I find detailed documentation for Aspose.Zip for .NET?
The documentation is available [here](https://reference.aspose.com/zip/net/).

### Can I purchase a temporary license for testing purposes?
Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

---