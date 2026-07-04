---
date: 2026-07-04
description: Aspose.Zip for .NET を使用して複数のファイルを tar 圧縮し、tar.lz アーカイブを効率的に作成する方法を学びます。
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: TarLz への圧縮
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用して複数のファイルを tar 圧縮する方法
url: /ja/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した複数ファイルの tar 圧縮方法

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Zip for .NET.  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約5〜10分です。  
- **ライセンスは必要ですか？** テストには無料トライアルで動作しますが、製品版には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **複数のファイルを一度に圧縮できますか？** はい、保存する前にエントリを追加するだけです。

## Aspose.Zip for .NET で複数ファイルの tar を圧縮する方法
ソースファイルを読み込み、`TarArchive` インスタンスを作成し、`CreateEntry` で各ファイルを追加し、`SaveLzipped` を呼び出して完了します。ライブラリは内部で TAR 構造と LZ 圧縮を処理するため、数行のコードで単一の `*.tar.lz` ファイルが生成されます。このアプローチは Windows、Linux、macOS でネイティブ依存関係なしに動作します。

## tar.lz 圧縮とは何ですか？
`tar.lz` は LZMA アルゴリズム（一般に **LZ** と呼ばれる）で圧縮された TAR アーカイブです。TAR のファイルグルーピングのシンプルさと LZ の高い圧縮率を組み合わせており、バックアップファイルやパッケージ配布、帯域幅が重要なシナリオに最適です。

## なぜ Aspose.Zip for .NET を使用するのか？
Aspose.Zip は純粋なマネージド・クロスプラットフォームのソリューションで、外部ツールなしで TAR、ZIP、LZ 系アーカイブを作成し、30 以上のアーカイブ形式に対応し、大きなファイルで最大 30 % の圧縮率向上を実現します。また、詳細な例外情報により堅牢なエラーハンドリングが可能です。さらに .NET のロギングフレームワークとシームレスに統合され、詳細な進行状況イベントを提供します。

## 前提条件
- **Aspose.Zip for .NET** ライブラリ – [here](https://releases.aspose.com/zip/net/) からダウンロードしてください。  
- アーカイブしたいファイルが入っているフォルダー。フォルダーへのパスは `dataDir` 変数に格納されます（Step 3 で設定します）。

## 名前空間のインポート
使用するクラスが所在する名前空間をインポートし、コンパイラに認識させます。

```csharp
using System;
using Aspose.Zip.Tar;
```

## tar.lz アーカイブの作成方法 – ステップバイステップガイド

### 手順 1: 単一ファイルの圧縮
最初の例は最も基本的なシナリオを示しています – 1 つのファイルを TAR アーカイブに追加し、**tar.lz** ファイルとして保存します。

`TarArchive` クラスは、単一のアーカイブ内に複数のファイルを保持できる TAR コンテナを表します。  

**説明**

- `new TarArchive()` は空の TAR コンテナを作成します。  
- `CreateEntry` は `dataDir` から `alice29.txt` ファイルを追加します。  
- `SaveLzipped` はアーカイブをディスクに書き込み、LZ 圧縮を適用して `archive.tar.lz` を生成します。

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### 手順 2: 1 つのアーカイブに複数ファイルを圧縮
複数のファイルをまとめてアーカイブする必要があることがよくあります。保存する前に各ファイルに対して `CreateEntry` を呼び出すだけです。これにより **add files to tar lz** と実質的に **compress multiple files tar** を実演します。

**説明**

- コードは手順 1 と同じパターンですが、2 番目のエントリ (`lcet10.txt`) を追加します。  
- 必要に応じて `CreateEntry` を繰り返し呼び出すことができ、ライブラリが内部の TAR 構造を自動的に処理します。

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### 手順 3: ドキュメントディレクトリの指定
プレースホルダーを、ソースファイルが存在する実際のパスに置き換えます。このパスは上記のサンプルで使用されます。

**説明**

- `dataDir` を完全修飾パス（例: `@"C:\\MyFiles\\"`）に設定します。  
- ディレクトリを変数に保持することで、コードの再利用性と保守性が向上します。

```csharp
string dataDir = "Your Document Directory";
```

## よくある落とし穴とトラブルシューティング
| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| `FileNotFoundException` がサンプル実行時に発生する | `dataDir` が存在しないフォルダーを指している、またはファイル名が間違っている | パスとファイル名を確認し、安全のために `Path.Combine` を使用してください。 |
| 出力ファイルが **0 KB** になる | `archive.SaveLzipped` がエントリを追加する前に呼び出された | `CreateEntry` を少なくとも1回呼び出してから `SaveLzipped` を実行してください。 |
| 圧縮が遅いように見える | デフォルトのバッファサイズで大きなファイルを処理している | パフォーマンスが重要な場合は、ファイルをチャンクで処理するか、非同期 I/O の使用を検討してください。 |

## 結論
これで、Aspose.Zip for .NET を使用して **tar.lz** ファイルを圧縮する方法が分かりました。単一のドキュメントでも複数ファイルのコレクションでも対応可能です。この **tar.lz 圧縮例** は、簡潔で本番環境でも使用できる **tar lz アーカイブ** の作成方法を示しています。すべてのエントリを追加した後に `SaveLzipped` を呼び出すだけで、同じ API でファイルを tar.lz に圧縮できます。

## よくある質問

**Q:** Aspose.Zip for .NET で任意のサイズのファイルを圧縮できますか？  
**A:** はい、ライブラリは小さなファイルから非常に大きなファイルまで対応します。テンポラリの TAR 構造用に十分なメモリとディスク容量があることを確認してください。

**Q:** コードは最新の Aspose.Zip リリースと互換性がありますか？  
**A:** サンプルは現在のバージョンを対象としています。バグ修正や新機能のために、常に NuGet パッケージを最新に保ってください。

**Q:** ライセンスに関する考慮点はありますか？  
**A:** 本番環境での使用には商用ライセンスが必要です。ライセンスの詳細は [Aspose website](https://purchase.aspose.com/buy) をご覧ください。

**Q:** 商用プロジェクトで使用できますか？  
**A:** もちろんです。有効なライセンスを取得すれば、任意の商用アプリケーションに組み込むことができます。

**Q:** 問題が発生した場合、どこでサポートを受けられますか？  
**A:** コミュニティサポートと公式支援のために、[Aspose.Zip forum](https://forum.aspose.com/c/zip/37) をご利用ください。

---

**最終更新日:** 2026-07-04  
**テスト環境:** Aspose.Zip for .NET (latest release)  
**作者:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Zip for .NET を使用して tar アーカイブを作成し、ファイルを tar に追加する](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip for .NET で tar を圧縮し TarBz2 を作成する方法](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Aspose.Zip を使用してファイルを tar に追加し、tarxz アーカイブを作成する](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}