---
date: 2026-07-18
description: Aspose.Zip for .NET を使用してフォルダーを Zip に追加し、ファイルを Zip に追加する方法を学びます。このステップバイステップガイドでは、ASP.NET
  プロジェクトで FileInfo を使用してファイルを圧縮する方法を示します。
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: FileInfo を使用したファイル圧縮
og_description: Aspose.Zip for .NET を使用してフォルダーを Zip に追加します。Zip アーカイブの作成、ファイルの Zip
  への追加、フォルダーの効率的な圧縮方法を ASP.NET で学びます。
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: フォルダーを Zip に追加 – Aspose.Zip for .NET でファイルを圧縮
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Aspose.Zip for .NET を使用してフォルダーを Zip に追加 – FileInfo でファイルを圧縮
url: /ja/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# フォルダーを Zip に追加する方法（Aspose.Zip for .NET）

## はじめに

プログラムで **add folder to zip** を行う必要がある場合、Aspose.Zip for .NET はクリーンで高性能な API を提供し、任意の .NET（ASP.NET を含む）アプリケーションで動作します。このチュートリアルでは `FileInfo` クラスを使用したファイル圧縮の手順を解説し、**add files to zip** の方法を示し、このアプローチが最新の .NET プロジェクトに最適な理由を説明します。また、**add folder to zip** の具体的な手順も紹介し、ディレクトリ全体を一括で圧縮できるようにします。さあ始めましょう！

## クイック回答
- **zip アーカイブを作成する最も簡単な方法は何ですか？** Aspose.Zip の `Archive` クラスと `FileInfo` オブジェクトを組み合わせて使用します。  
- **複数のファイルを一度に追加できますか？** はい、各ファイルに対して `FileInfo` を作成し、`CreateEntry` を呼び出すだけです。  
- **ASP.NET 用に特別なライセンスが必要ですか？** 本番環境では商用の Aspose.Zip ライセンスが必要です。評価目的であれば無料トライアルで動作します。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、そして .NET 5–10 をサポートしています。  
- **API はスレッドセーフですか？** はい、各スレッドが独自の `Archive` インスタンスを使用すれば安全です。

## Zip アーカイブとは何か、なぜ作成するのか

Zip アーカイブは、1 つまたは複数のファイルを単一の圧縮コンテナにまとめます。これによりストレージ容量が削減され、ネットワーク転送が高速化され、配布が簡素化されます。ログの配信、レポートのエクスポート、クライアント向け資産のパッケージ化など、**how to create zip archive** ファイルをプログラムで作成できることは、すべての .NET 開発者にとって貴重なスキルです。

## Aspose.Zip を使用してファイルを Zip に追加する理由

Aspose.Zip は外部依存関係を排除した純粋な .NET ソリューションを提供し、圧縮、エンコーディング、セキュリティに対する細かな制御を開発者に提供します。大容量ファイル、パスワード保護をサポートし、サポート対象のすべての .NET バージョンで一貫して動作するため、レガシーアプリケーションでも最新アプリケーションでも信頼できる選択肢です。  

- **外部依存なし** – 純粋な .NET 実装。  
- **圧縮レベルとエンコーディングの完全な制御**（ASCII、UTF‑8 など）。  
- **4 GB を超えるファイルとパスワード保護をサポート**。  
- **50 以上の .NET バージョンで一貫した API** – .NET Framework 2.0 から .NET 10 まで。  

## 前提条件

コードに入る前に、以下が揃っていることを確認してください。

1. **Aspose.Zip for .NET** がインストールされていること。最新パッケージは [Aspose.Zip download page](https://releases.aspose.com/zip/net/) からダウンロードしてください。  
2. 圧縮したいファイルが入っているフォルダーがマシン上にあること（例: `alice29.txt` と `fields.c`）。

## 名前空間のインポート

Zip アーカイブを扱う任意の C# ファイルで、以下の `using` 文を追加します：

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

これらの名前空間により、`Archive` クラスや保存オプション、標準 I/O ユーティリティにアクセスできます。

## 手順ガイド

### 手順 1: ドキュメントディレクトリの設定

まず、ソースファイルが格納されているフォルダーを定義します。プレースホルダーをシステム上の絶対パスまたは相対パスに置き換えてください：

```csharp
string dataDir = "Your Document Directory";
```

> **プロのコツ:** `Path.Combine` を使用して、クロスプラットフォーム対応のパスを構築してください。

### 手順 2: 書き込み用に Zip ファイルを開く

`FileStream` を作成し、出力先の zip ファイルを指すようにします。ストリームは **Create** モードで開かれ、同名の既存ファイルがあれば上書きされます：

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 手順 3: 各ソースファイル用に `FileInfo` オブジェクトを準備する

`FileInfo` は Aspose.Zip にディスク上の実際のファイルへの直接アクセスを提供します。圧縮したい各ファイルにつき 1 つのインスタンスを作成します：

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **なぜ `FileInfo` を使用するのか？** ファイル全体をメモリに読み込むことを回避できるため、特に大容量ファイルに有効です。

### 手順 4: アーカイブを作成しエントリを追加する

`Archive` クラスは、メモリ内で zip コンテナを表す Aspose.Zip のコアオブジェクトです。`Archive` オブジェクトをインスタンス化し、各 `FileInfo` に対して `CreateEntry` を呼び出します。第1引数は zip 内でのファイル名、第2引数はソースとなる `FileInfo` です：

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

`CreateEntry` メソッドは新しいファイルエントリをアーカイブに追加し、エントリ名とソース `FileInfo` を紐付けることで、アーカイブ保存時にデータがディスクから直接ストリームされます。

### 手順 5: 任意のエンコーディングで Zip アーカイブを保存する

最後に、先ほど開いた `FileStream` にアーカイブを保存します。ここではエントリ名に ASCII エンコーディングを使用していますが、ファイル名に非 ASCII 文字が含まれる場合は UTF‑8 に切り替えることも可能です：

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` ブロックが終了すると、ストリームは自動的に閉じられ、zip ファイルの使用準備が整います。

## Aspose.Zip を使用してフォルダーを Zip に追加する方法

対象ディレクトリを読み込み、すべてのファイルを列挙し、フォルダー名を含む相対パスで各ファイルを追加します。この方法により、各ファイルを手動で列挙せずに **add folder to zip** が可能です。エントリ名にフォルダー階層を保持することで、生成されたアーカイブは元のディレクトリ構造をそのまま保った状態で展開でき、さまざまなデプロイシナリオで重要となります。

1. 圧縮したいフォルダーを指すために `DirectoryInfo` を使用します。  
2. `GetFiles("*", SearchOption.AllDirectories)` を呼び出して、すべてのファイルを再帰的に取得します。  
3. 各ファイルについて `FileInfo` を作成し、`CreateEntry` を `"MyFolder/Report.pdf"` のようなパスで呼び出します。  

API が `FileInfo` を使用するため、各ファイルはディスクから直接ストリームされ、数百メガバイト規模のフォルダーでもメモリ使用量を低く抑えることができます。

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| **空の zip ファイル** | `FileInfo` が存在しないパスを指している | `dataDir` とファイル名を確認し、エントリ作成前に `File.Exists` でチェックしてください。 |
| **ファイル名エンコーディングが正しくない** | 非 ASCII 名でデフォルトエンコーディングを使用している | `ArchiveSaveOptions` の `Encoding = Encoding.UTF8` を設定してください。 |
| **大容量ファイルで OutOfMemoryException が発生** | ファイル全体をメモリに読み込んでいる | `FileInfo` がファイルをストリームするので、他の場所でバイト配列に読み込んでいないか確認してください。 |
| **アクセス拒否** | アプリケーションが出力フォルダーへの書き込み権限を持っていない | 適切な権限でアプリを実行するか、書き込み可能なディレクトリを選択してください。 |

## よくある質問

**Q: フォルダー全体を単一の呼び出しで zip アーカイブに追加できますか？**  
A: 単一呼び出しのメソッドはありませんが、`DirectoryInfo` でファイルを列挙し、`CreateEntry` で個別に追加すれば、同等の結果を効率的に得られます。

**Q: Aspose.Zip はパスワード保護をサポートしていますか？**  
A: はい、保存前に `Archive` オブジェクトにパスワードを設定して、アーカイブ全体を暗号化できます。

**Q: Aspose.Zip が扱える zip ファイルの最大サイズはどれくらいですか？**  
A: ライブラリは 4 GB を超えるファイルを処理でき、メモリに全体を読み込むことなく 10 GB を超えるアーカイブも作成可能です。

**Q: API は .NET 6 や .NET 8 と互換性がありますか？**  
A: 完全に対応しています。Aspose.Zip は .NET 5 から .NET 10 までをサポートしており、現在のすべての LTS リリースをカバーしています。

**Q: 利用可能な圧縮レベルは何ですか？**  
A: `CompressionLevel.NoCompression`、`Fast`、`Normal`、`Maximum` のいずれかを選択して、速度とサイズのバランスを調整できます。

## さらに読む

- 最新の Aspose.Zip パッケージをダウンロード: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- 本番利用向けにライセンスを購入: [purchase page](https://purchase.aspose.com/buy)  
- コミュニティからサポートを得る: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- 無料で Aspose.Zip を試す: [free trial here](https://releases.aspose.com/)  
- 評価用の一時ライセンスを取得: [this link](https://purchase.aspose.com/temporary-license/)

## 結論

これで、Aspose.Zip for .NET を使用して **add folder to zip** と **create zip archive** の方法、**add files to zip** の手順、そしてこの手法が ASP.NET やその他の .NET アプリケーションに最適である理由が分かりました。さまざまな圧縮レベル、エンコーディング、暗号化オプションを試して、アーカイブを正確なニーズに合わせて調整してください。圧縮を楽しんでください！

**最終更新日:** 2026-07-18  
**テスト環境:** Aspose.Zip for .NET 24.12 (latest)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Zip for .NET を使用したフォルダーの Zip 方法](/zip/net/directory-and-folder-compression/compress-directory/)
- [c# で複数ファイルを zip – Aspose.Zip for .NET で簡単圧縮](/zip/net/file-compression/compress-multiple-files/)
- [Zip アーカイブの作成 .NET – Aspose.Zip を使ったファイル圧縮](/zip/net/file-compression/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}