---
date: 2026-05-30
description: .NETでAspose.Zip for .NETを使用して圧縮なしでzipを作成する方法を学びます。このガイドでは、圧縮せずにファイルをzipする方法、ファイルを非圧縮で保存する方法、そしてアーカイブを効率的に管理する方法を示します。
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: 圧縮せずに複数のファイルを保存する
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NETでAspose.Zipを使用して圧縮なしでzipを作成する
url: /ja/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET で Aspose.Zip を使用して圧縮なしで zip を作成する

最新の .NET 開発では、**圧縮なしで zip を作成する**ことで、アーカイブ速度が大幅に向上し、ファイルサイズを予測可能に保つことができます。**圧縮なしでファイルを zip**する必要がある場合—たとえば、規制要件を満たすため、下流処理を高速化するため、または元のバイト列をそのまま保持することを保証するために—Aspose.Zip for .NET はシンプルで分かりやすい API を提供します。このチュートリアルでは、圧縮されていない ZIP アーカイブを作成し、ファイルを追加し、ソリューションをアプリケーションに統合する正確な手順を解説します。

## クイック回答
- **“uncompressed zip” とは何ですか？** それは各エントリが “store” メソッドで保存され、元のファイルバイトがそのまま保持される ZIP アーカイブです。  
- **圧縮を避ける理由は？** アーカイブを高速化し、下流処理のために元のファイルサイズを保持するか、データ変更を禁じる規制要件を満たすためです。  
- **どの Aspose.Zip クラスがこれを扱いますか？** `ArchiveEntrySettings` と `StoreCompressionSettings` の組み合わせです。  
- **ライセンスは必要ですか？** 無料トライアルはテストに使用できますが、製品環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、そして .NET 5–10 です。  

## 圧縮なし zip とは何か？

**圧縮なし zip** は、各ファイルエントリが *store* メソッドを使用する ZIP アーカイブで、データが圧縮アルゴリズムを適用せずにそのままアーカイブにコピーされます。その結果、アーカイブのサイズは実質的に元のファイルの合計に数バイトの ZIP オーバーヘッドを加えたものになります。

## 圧縮なし zip ファイルに Aspose.Zip を使用する理由は？

Aspose.Zip は高性能なアーカイブ向けに最適化されており、圧縮アルゴリズムのオーバーヘッドなしでファイルを即座に保存できます。完全な ZIP 互換性を保証し、保存エントリと圧縮エントリを混在させることができ、低レベルの ZIP 構造を抽象化したシンプルな API を提供するため、実装が迅速かつ信頼性があります。

## 前提条件
- **Aspose.Zip for .NET** – プロジェクトに統合されています。インストール手順は公式の [documentation](https://reference.aspose.com/zip/net/) を参照してください。  
- **.NET 開発環境** – Visual Studio、VS Code、またはお好みの IDE。  
- **Document Directory** – アーカイブしたいファイルが格納されたマシン上のフォルダー（例: “Your Document Directory”）。

## 名前空間のインポート
コードを書く前に、必要な名前空間をインポートしてコンパイラが Aspose クラスの所在を認識できるようにします。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 手順 1: Document Directory の設定
ソースファイルが存在するパスを定義します。プレースホルダーをシステム上の実際のフォルダーに置き換えてください。

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: 圧縮なしで Zip アーカイブを作成する
チュートリアルの核心 – `StoreCompressionSettings` で構成された `Archive` インスタンスを作成します。`Archive` は�数のエントリを保持できる ZIP コンテナを表します。`StoreCompressionSettings` はエントリを圧縮せずに保存すべきことを指定します。これにより Aspose.Zip は各エントリを *store*（つまり圧縮しない）します。

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

> **プロのコツ:** いくつかのファイルは圧縮し、他のファイルは圧縮せずに **zip に保存** する必要がある場合は、各ファイル用に個別の `ArchiveEntrySettings` インスタンスを作成し、同じ `Archive` に追加してください。

## .NET で圧縮なし zip を作成する方法は？
ソースファイルを読み込み、`Archive` オブジェクトをインスタンス化し、`new StoreCompressionSettings()` を使用した `ArchiveEntrySettings` で各ファイルを追加します。全体の操作はコード3行だけで済み、総ファイルサイズに対して線形時間で実行され、可能な限り高速なアーカイブ体験を提供します。

### 手順ごとのウォークスルー
1. **アーカイブの作成** – ターゲットストリームまたはファイルパスで `Archive` をインスタンス化します。  
2. **エントリ設定の構成** – 各ファイルについて `ArchiveEntrySettings` オブジェクトを作成し、その `Compression` プロパティに `new StoreCompressionSettings()` を割り当てます。  
3. **エントリの追加** – 各ファイルに対して `archive.Add(entrySettings)` を呼び出し、最後に `archive.Save()` で完了します。

## よくある問題と解決策
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **ファイルが見つかりません** | `dataDir` パスが間違っているか、ファイル拡張子が欠落しています。 | パスを確認し、ファイルが存在することを確認してください。安全な結合のために `Path.Combine` を使用します。 |
| **アクセスが拒否されました** | プロセスにソースファイルの読み取りまたは ZIP の書き込み権限がありません。 | 適切な権限でアプリケーションを実行するか、書き込み可能なフォルダーを選択してください。 |
| **ZIP 内の予期しないファイルサイズ** | アーカイブがデフォルトの圧縮で作成されました。 | `ArchiveEntrySettings` に `new StoreCompressionSettings()` が渡されていることを確認してください。 |

## よくある質問

**Q: 特定のファイルタイプだけ圧縮し、他を圧縮せずに保存できますか？**  
A: はい、各ファイルに対して異なる `ArchiveEntrySettings` を作成し、同じアーカイブ内で圧縮エントリと非圧縮エントリを混在させることができます。

**Q: Aspose.Zip for .NET は .NET Core や .NET 5/6 と互換性がありますか？**  
A: もちろんです。このライブラリは .NET Framework、.NET Core、.NET Standard、そして最新の .NET バージョンをサポートしています。

**Q: アーカイブ処理中の例外はどのように処理すべきですか？**  
A: アーカイブコードを `try‑catch` ブロックで囲み、例外の詳細をログに記録してください。これにより、優雅な失敗とデバッグが容易になります。

**Q: Aspose.Zip はマルチスレッドのアーカイブをサポートしていますか？**  
A: はい、複数のファイルを並行処理してアーカイブに追加できますが、`Archive` オブジェクト自体はスレッドセーフではないため、エントリを追加する際はアクセスを同期してください。

**Q: 既存プロジェクトに大幅なコード変更なしで Aspose.Zip を統合できますか？**  
A: 確実に可能です。API はシンプルなドロップイン使用を想定して設計されています。移行ガイドは公式の [documentation](https://reference.aspose.com/zip/net/) を参照してください。

---

**最終更新日:** 2026-05-30  
**テスト環境:** Aspose.Zip for .NET (latest version at time of writing)  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}