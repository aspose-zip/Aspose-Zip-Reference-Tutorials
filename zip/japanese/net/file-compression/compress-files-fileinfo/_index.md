---
date: 2025-12-05
description: Aspose.Zip for .NET を使用して zip アーカイブを作成し、ファイルを zip に追加する方法を学びます。このステップバイステップガイドでは、ASP.NET
  プロジェクトで FileInfo を使用してファイルを圧縮する方法を示します。
language: ja
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用して Zip アーカイブを作成する方法 – FileInfo でファイルを圧縮
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した Zip アーカイブの作成方法

## はじめに

プログラムで **zip アーカイブを作成** する必要がある場合、Aspose.Zip for .NET はクリーンで高性能な API を提供し、任意の .NET（ASP.NET を含む）アプリケーションで動作します。このチュートリアルでは `FileInfo` クラスを使ったファイル圧縮の手順を解説し、**zip にファイルを追加** する方法を示し、なぜこのアプローチが最新の .NET プロジェクトに最適なのかを説明します。さっそく始めましょう！

## クイック回答
- **最も簡単に zip アーカイブを作成する方法は何ですか？** Aspose.Zip の `Archive` クラスと `FileInfo` オブジェクトを使用します。  
- **複数のファイルを一度に追加できますか？** はい – 各ファイルに対して `FileInfo` を作成し、`CreateEntry` を呼び出すだけです。  
- **ASP.NET 用に特別なライセンスが必要ですか？** 本番環境では商用 Aspose.Zip ライセンスが必要です。評価目的は無料トライアルで動作します。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **API はスレッドセーフですか？** はい、各スレッドが独自の `Archive` インスタンスを使用すれば安全です。

## Zip アーカイブとは何か、そして作成する理由

Zip アーカイブは、1 つまたは複数のファイルを単一の圧縮コンテナにまとめたものです。これによりストレージ容量が削減され、ネットワーク転送が高速化され、配布が簡素化されます。ログの配布、レポートのエクスポート、クライアント向け資産のパッケージ化など、**zip アーカイブをプログラムで作成** できることは、すべての .NET 開発者にとって価値あるスキルです。

## なぜ Aspose.Zip を使用してファイルを Zip に追加するのか

- **外部依存関係がゼロ** – 純粋な .NET 実装。  
- **圧縮レベルとエンコーディング（ASCII、UTF‑8 など）を完全に制御**。  
- **大容量ファイル（> 4 GB）やパスワード保護に対応**。  
- **.NET Framework、.NET Core、.NET 5+ で一貫した API**。

## 前提条件

コードに入る前に、以下が揃っていることを確認してください。

1. **Aspose.Zip for .NET** がインストール済み。最新パッケージは [Aspose.Zip ダウンロードページ](https://releases.aspose.com/zip/net/) から取得できます。  
2. 圧縮したいファイルが格納されたフォルダー（例: `alice29.txt` と `fields.c`）がローカルにあること。

## 名前空間のインポート

Zip アーカイブを扱う任意の C# ファイルで、次の `using` 文を追加します。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

これらの名前空間により、`Archive` クラスや保存オプション、標準 I/O ユーティリティにアクセスできます。

## ステップバイステップガイド

### ステップ 1: ドキュメントディレクトリの設定

まず、ソースファイルが格納されているフォルダーを定義します。プレースホルダーをシステム上の絶対パスまたは相対パスに置き換えてください。

```csharp
string dataDir = "Your Document Directory";
```

> **プロのコツ:** `Path.Combine` を使用して、クロスプラットフォーム対応のパスを構築しましょう。

### ステップ 2: 書き込み用 Zip ファイルを開く

出力 zip ファイルを指す `FileStream` を作成します。ストリームは **Create** モードで開かれ、同名の既存ファイルがあれば上書きされます。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### ステップ 3: 各ソースファイル用の `FileInfo` オブジェクトを準備する

`FileInfo` は Aspose.Zip にディスク上の実体ファイルへの直接アクセスを提供します。圧縮したいファイルごとにインスタンスを作成します。

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **`FileInfo` を使用する理由:** ファイル全体をメモリに読み込む必要がなくなるため、特に大容量ファイルの処理に有効です。

### ステップ 4: アーカイブを作成しエントリを追加する

`Archive` オブジェクトをインスタンス化し、各 `FileInfo` に対して `CreateEntry` を呼び出します。第1引数は zip 内でのファイル名、第2引数はソース `FileInfo` です。

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### ステップ 5: 任意のエンコーディングで Zip アーカイブを保存する

最後に、先ほど開いた `FileStream` にアーカイブを永続化します。ここではエントリ名に ASCII エンコーディングを使用していますが、ファイル名に非 ASCII 文字が含まれる場合は UTF‑8 に切り替えることができます。

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` ブロックが終了すると、ストリームは自動的にクローズされ、zip ファイルの作成が完了します。

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| **Empty zip file** | `FileInfo` が存在しないパスを指している | `dataDir` とファイル名を確認し、`File.Exists` で存在チェックを行ってからエントリを作成してください。 |
| **Incorrect filename encoding** | デフォルトエンコーディングで非 ASCII 名を使用している | `ArchiveSaveOptions` の `Encoding = Encoding.UTF8` を設定してください。 |
| **OutOfMemoryException on large files** | ファイル全体をメモリに読み込んでいる | `FileInfo` はストリーミングで処理します。別箇所でバイト配列に読み込んでいないか確認してください。 |
| **Permission denied** | 出力フォルダーへの書き込み権限がない | 適切な権限でアプリを実行するか、書き込み可能なディレクトリを選択してください。 |

## よくある質問

**Q: zip アーカイブにパスワード保護を追加できますか？**  
A: はい。`Archive` を作成した後、`Save` を呼び出す前に `archive.Password = "yourPassword"` と設定します。

**Q: 既存の zip ファイルを更新することは可能ですか？**  
A: Aspose.Zip は `Archive.Open` で既存アーカイブを開き、そこに新しいエントリを追加できます。

**Q: ASP.NET MVC コントローラでファイルを圧縮するにはどうすればよいですか？**  
A: 同じコードが使用可能です。出力ストリームを `FileResult` としてクライアントに返すだけです。

**Q: Aspose.Zip は暗号化アルゴリズムをサポートしていますか？**  
A: 標準の ZipCrypto と AES‑256 暗号化をサポートしています。

**Q: フォルダーを再帰的に圧縮したい場合はどうすればよいですか？**  
A: `Directory.GetFiles`（およびサブフォルダー）をループし、各ファイルに対して `FileInfo` を作成してアーカイブに追加します。

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## 結論

これで **Aspose.Zip for .NET を使用した zip アーカイブの作成方法**、**zip にファイルを追加** する手順、そしてこの方法が ASP.NET やその他の .NET アプリケーションに最適である理由が分かりました。圧縮レベル、エンコーディング、暗号化オプションをいろいろ試して、用途に合わせたアーカイブを作成してください。圧縮を楽しんでください！

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}