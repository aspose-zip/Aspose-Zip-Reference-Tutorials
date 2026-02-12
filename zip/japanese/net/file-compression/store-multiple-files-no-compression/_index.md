---
date: 2026-02-12
description: Aspose.Zip for .NET を使用して、圧縮なしの zip を作成する方法を学びましょう。このガイドでは、圧縮せずにファイルを
  zip に追加し、ファイルを非圧縮で保存し、アーカイブを効率的に管理する方法を示します。
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用して非圧縮 ZIP を作成する
url: /ja/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した圧縮なし ZIP の作成

最新の .NET 開発において、**uncompressed zip .net** を作成することは、アーカイブ速度を劇的に向上させ、ファイルサイズを予測可能に保ちます。例えば、規制要件を満たすためや、下流処理を高速化するために **圧縮せずにファイルを zip** する必要がある場合、Aspose.Zip for .NET はシンプルで分かりやすい API を提供します。本チュートリアルでは、圧縮なし ZIP アーカイブの作成手順、ファイルの追加方法、そしてソリューションをアプリケーションに統合する手順を詳しく解説します。

## Quick Answers
- **“uncompressed zip” とは何ですか？** それは各エントリが “store” メソッドで保存され、元のファイルバイトがそのまま保持される ZIP アーカイブです。  
- **なぜ圧縮を避けるのですか？** アーカイブ処理を高速化し、下流処理のために元のファイルサイズを保持するか、データ変更を禁じる規制要件を満たすためです。  
- **どの Aspose.Zip クラスがこれを扱いますか？** `ArchiveEntrySettings` と `StoreCompressionSettings` の組み合わせです。  
- **ライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework、.NET Core、.NET 5/6/7 以降です。  

## create uncompressed zip .net とは何ですか？

圧縮なし ZIP を作成するとは、*store* 圧縮方式を使用して各ファイルを ZIP コンテナに追加することです。ファイルは元のバイトと完全に同一のままで、迅速なアーカイブやデータを変更せずに保持したい場合に最適です。

## Why use Aspose.Zip for zip files without compression?

- **速度:** CPU 集中型の圧縮アルゴリズムが実行されません。  
- **予測可能なサイズ:** アーカイブサイズは元のファイルの合計に最小限の ZIP オーバーヘッドを加えたものと同じです。  
- **互換性:** 作成された ZIP は標準的な解凍ユーティリティで問題なく使用できます。  
- **柔軟性:** 必要に応じて、同じアーカイブ内で圧縮エントリと非圧縮エントリを混在させることができます。  

## Prerequisites
- **Aspose.Zip for .NET** – プロジェクトに統合します。インストール手順は公式 [documentation](https://reference.aspose.com/zip/net/) を参照してください。  
- **.NET 開発環境** – Visual Studio、VS Code、またはお好みの IDE。  
- **Document Directory** – アーカイブしたいファイルが格納されたローカルフォルダー（例: “Your Document Directory”）。  

## Import Namespaces
コードを書く前に、必要な名前空間をインポートしてコンパイラが Aspose クラスの所在を認識できるようにします。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Step 1: Set Document Directory
ソースファイルが存在するパスを定義します。プレースホルダーを実際のフォルダーに置き換えてください。

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create Zip Archive Without Compression
チュートリアルの核心 – `StoreCompressionSettings` を設定した `Archive` インスタンスを作成します。これにより Aspose.Zip は各エントリを *store*（圧縮しない）方式で保存します。

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **プロのコツ:** いくつかのファイルは圧縮し、他は圧縮せずに **zip に保存** したい場合は、各ファイルごとに別々の `ArchiveEntrySettings` インスタンスを作成し、同じ `Archive` に追加してください。

## Common Issues and Solutions
| 問題 | 発生理由 | 対策 |
|-------|----------------|-----|
| **ファイルが見つかりません** | `dataDir` パスが間違っているか、ファイル拡張子が欠落しています。 | パスを確認し、ファイルが存在することを確認してください。安全な結合のために `Path.Combine` を使用します。 |
| **アクセスが拒否されました** | プロセスにソースファイルの読み取りまたは ZIP の書き込み権限がありません。 | 適切な権限でアプリケーションを実行するか、書き込み可能なフォルダーを選択してください。 |
| **ZIP 内の予期しないファイルサイズ** | アーカイブがデフォルトの圧縮で作成されました。 | `ArchiveEntrySettings` に `new StoreCompressionSettings()` が渡されていることを確認してください。 |

## Frequently Asked Questions

**Q: 特定のファイルタイプだけ圧縮し、他は圧縮せずに保存できますか？**  
A: はい、各ファイルに対して異なる `ArchiveEntrySettings` を作成し、同じアーカイブ内で圧縮エントリと非圧縮エントリを混在させることができます。

**Q: Aspose.Zip for .NET は .NET Core や .NET 5/6 と互換性がありますか？**  
A: もちろんです。このライブラリは .NET Framework、.NET Core、.NET Standard、そして最新の .NET バージョンをサポートしています。

**Q: アーカイブ処理中の例外はどのように処理すべきですか？**  
A: アーカイブコードを `try‑catch` ブロックで囲み、例外の詳細をログに記録してください。これにより、優雅な失敗処理とデバッグが容易になります。

**Q: Aspose.Zip はマルチスレッドでのアーカイブをサポートしていますか？**  
A: はい、複数のファイルを並列に処理してアーカイブに追加できますが、`Archive` オブジェクト自体はスレッドセーフではないため、エントリを追加する際はアクセスを同期してください。

**Q: 既存プロジェクトに大幅なコード変更なしで Aspose.Zip を統合できますか？**  
A: もちろんです。API はシンプルに組み込めるよう設計されています。移行ガイドは公式 [documentation](https://reference.aspose.com/zip/net/) をご参照ください。

**最終更新日:** 2026-02-12  
**テスト環境:** Aspose.Zip for .NET (執筆時点での最新バージョン)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}