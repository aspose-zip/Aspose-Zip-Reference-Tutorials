---
date: 2026-06-19
description: Aspose.Zip for .NET を使用して tar ファイルを圧縮し、targz アーカイブを作成し、パスワード保護された zip
  ファイルを抽出する方法を学び、ストレージ効率とセキュリティを向上させます。
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: アーカイブの抽出とフォーマット
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
title: Aspose.Zip for .NET を使用した Tar ファイルの圧縮方法
url: /ja/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した Tar ファイルの圧縮方法

## はじめに

このガイドでは、Aspose.Zip for .NET を使用して **tar** ファイルを圧縮する方法を学び、TarGz アーカイブの作成方法やパスワード保護された zip アーカイブの抽出方法を確認します。効率的なアーカイブ処理は、最新の .NET 開発者にとって重要なスキルです—バックアップサービス、クラウドストレージクライアント、データ処理パイプラインの構築に関わらず、これらの形式をマスターすることでストレージコストを削減し、転送速度を向上させ、機密データを安全に保護できます。

## クイック回答
- **TarBz2 とは何ですか？** TAR パッケージングと BZIP2 圧縮を組み合わせた高圧縮率のアーカイブです。  
- **なぜ Aspose.Zip for .NET を選ぶのですか？** 外部依存関係なしで多数のアーカイブ形式の作成と抽出ができる、シンプルで流暢な API を提供します。  
- **TarGz アーカイブを作成できますか？** はい – Aspose.Zip は TarGz、TarLz、TarXz、TarZ などをサポートしています。  
- **パスワード保護された zip アーカイブを抽出するには？** 抽出時に `ArchiveEntry` オブジェクトの `Password` プロパティを使用します。  
- **本番環境で使用するにはライセンスが必要ですか？** 本番利用には商用ライセンスが必要です。評価用に無料トライアルが利用可能です。

## Tar 圧縮とは何ですか？

Tar（Tape Archive）は、�数のファイルやディレクトリを圧縮なしで単一のストリームにまとめるコンテナ形式です。BZIP2、GZip、LZMA、XZ などの圧縮アルゴリズムを適用すると、`.tar.bz2`、`.tar.gz`、`.tar.lz` などの **tar ベースのアーカイブ** が生成されます。これらの形式は Linux、macOS、Windows で広くサポートされており、クロスプラットフォームのデータ交換に最適です。

## これらの形式を扱うために Aspose.Zip for .NET を使用する理由

Aspose.Zip は **統一された依存関係のない API** を提供し、TarBz2、TarGz、TarLz、TarXz、TarZ を含む 50 以上のアーカイブおよび圧縮形式をサポートします。Windows、Linux、macOS 上で動作し、ストリームベースのアーキテクチャにより、数百メガバイト規模のアーカイブでもメモリ使用量を 10 MB 未満に抑えます。パスワード保護が組み込まれており、追加ライブラリなしでエントリ単位の暗号化が可能です。

## 前提条件
- .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、または .NET 5–10。  
- Aspose.Zip for .NET の NuGet パッケージがインストールされていること (`Install-Package Aspose.Zip`)。  
- C# のファイル I/O と .NET プロジェクトシステムの基本的な知識があること。

## ステップバイステップ ガイド

### Tar ファイルの圧縮方法 – 直接回答
`Archive` はアーカイブファイルを表し、エントリの追加や保存のメソッドを提供します。  
`Archive` インスタンスを作成し、バンドルしたいファイルを追加し、`CompressionType.BZip2` を設定し、`ArchiveFormat.TarBz2` で `Save` を呼び出します。ライブラリは TAR コンテナを書き込み、単一のストリーミングパスで圧縮するため、アーカイブ全体をメモリにロードすることはありません。

### 手順 1: 必要なアーカイブ形式を選択
圧縮率と速度のトレードオフに最適な tar ベースの形式を決定します：
- **TarBz2** – 最高の圧縮率（TarGz より約30 % 小さい）ですが、速度は遅めです。  
- **TarGz** – 速度とサイズのバランスが良く、ほとんどのクラウドストレージシナリオに最適です。  
- **TarLz / TarXz** – 非常に高い圧縮率と中程度の速度で、アーカイブ保存に有用です。  
- **TarZ** – 古い Unix ツールとの互換性のためのレガシーフォーマットです。

### 手順 2: 新しい `Archive` インスタンスを作成
`Archive` はメモリ内の単一アーカイブファイルを表すトップレベルオブジェクトです。  
`Archive` クラスはパッキングと圧縮のワークフローを管理し、エントリの追加や最終ファイルの書き込みメソッドを提供します。

### 手順 3: ファイルとフォルダーを追加
`AddAll` でディレクトリツリー全体を追加したり、`AddFile` で個別のファイルを追加できます。元のフォルダー階層を保持するには、ベースディレクトリパスを渡すだけです。

### 手順 4: 希望する圧縮タイプを設定
`CompressionType` はサポートされているアルゴリズムを列挙します。  
`CompressionType` は保存時に TAR ストリームに適用されるアルゴリズム（BZip2、GZip、LZMA、XZ など）を定義します。

### 手順 5: アーカイブを保存
`ArchiveFormat` は列挙型セット（例: `TarBz2`、`TarGz`）で、ライターに使用するコンテナと圧縮方式を指示します。  
`Save` を呼び出すと、選択した形式でアーカイブがディスクに書き込まれます。

### 手順 6: パスワード付きアーカイブの抽出
`ArchiveEntry` はアーカイブ内の単一のファイルまたはディレクトリエントリを表します。  
パスワード保護された zip を抽出するには、アーカイブを開き、各 `ArchiveEntry` を見つけ、その `Password` プロパティを設定してから `Extract` を呼び出します。このエントリ単位のパスワードモデルにより、単一の zip 内の個別ファイルを保護できます。

### 手順 7: 結果を検証
抽出後、ファイルサイズと SHA‑256 チェックサムを比較し、アーカイブの往復でデータの完全性が保たれたことを確認します。

## 一般的な使用例
- **バックアップユーティリティ** – 毎日のバックアップを `.tar.bz2` として保存し、ストレージコストを最大 30 % 削減します。  
- **クロスプラットフォームデータ交換** – Tar ベースの形式は Linux、macOS、Windows のツールでネイティブにサポートされています。  
- **安全な配布** – 機密エントリにパスワードを割り当て、追加の暗号化ツールなしでコンプライアンス要件を満たします。

## トラブルシューティングとヒント
- **大規模アーカイブ** – メモリ使用量を抑えるためにストリーミング API（`Archive.CreateEntryFromFile`）を使用してください。  
- **パスワード不一致** – 各 `ArchiveEntry` に設定されたパスワードは完全に一致する必要があり、そうでない場合は `InvalidPasswordException` がスローされます。  
- **圧縮レベル** – BZIP2 はカスタムレベルを提供しません。より細かい制御が必要な場合は、LZMA（`CompressionType.LZMA`）または XZ（`CompressionType.XZ`）に切り替えてください。  

## よくある質問

**Q: TarGz アーカイブはどうやって作成しますか？**  
A: `CompressionType.GZip` を設定し、`Save` 呼び出し時に `ArchiveFormat.TarGz` を使用します。これにより、単一ステップで `.tar.gz` ファイルが生成されます。

**Q: パスワードを知らずにパスワード保護されたアーカイブを抽出できますか？**  
A: できません。各エントリに正しいパスワードを提供する必要があり、そうでない場合は `InvalidPasswordException` が発生して抽出に失敗します。

**Q: Aspose.Zip はエントリごとに異なるパスワードでアーカイブを抽出することをサポートしていますか？**  
A: はい。`Extract` を呼び出す前に、各 `ArchiveEntry` に個別にパスワードを割り当てます。

**Q: どの形式が最も高い圧縮率を提供しますか？**  
A: 通常、TarBz2 が最小サイズを実現し、次に TarLz と TarXz が続きます。TarGz はより高速で、依然として効果的な代替手段です。

**Q: TAR アーカイブに追加できるファイル数に制限はありますか？**  
A: 実質的に制限はありませんが、非常に大きなアーカイブ（>10 GB）は、取り扱いを容易にするために複数のパーツに分割した方が良い場合があります。

## アーカイブ抽出と形式のチュートリアル

### [Aspose.Zip for .NET を使用した TarBz2 へのファイル圧縮](./compress-to-tar-bz2/)
Aspose.Zip を使用して .NET でファイルを TarBz2 形式に圧縮する方法を学びます。効率的なファイル圧縮のためのステップバイステップガイドに従ってください。

### [Aspose.Zip for .NET を使用した TarGz への圧縮](./compress-to-tar-gz/)
Aspose.Zip を使用して .NET で効率的なファイル圧縮を体験してください。簡単に TarGz に圧縮できます。

### [Aspose.Zip for .NET を使用した TarLz への圧縮](./compress-to-tar-lz/)
Aspose.Zip を使用して .NET でファイルを簡単に圧縮し、ステップバイステップで TarLz アーカイブの作成方法を学びます。

### [Aspose.Zip for .NET を使用した TarXz への圧縮](./compress-to-tar-xz/)
Aspose.Zip を使用して .NET でファイルを TarXz 形式に圧縮する方法を学びます。効率的な保存と転送のためのガイドに従ってください。

### [Aspose.Zip for .NET を使用した TarZ への圧縮](./compress-to-tar-z/)
Aspose.Zip for .NET を使用した TarZ へのステップバイステップ圧縮を探求してください。 .NET プロジェクトの効率的なファイル処理に役立ちます。

### [Aspose.Zip for .NET でエントリごとに異なるパスワードでアーカイブを抽出](./extract-archive-different-passwords/)
Aspose.Zip for .NET でエントリごとに異なるパスワードでアーカイブを抽出する方法を学び、アプリケーションのセキュリティと柔軟性を向上させます。

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## 関連チュートリアル

- [Aspose.Zip for .NET を使用して tar アーカイブを作成し、ファイルを tar に追加](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip for .NET を使用して tar を圧縮し、TarBz2 を作成する方法](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Aspose.Zip を使用してファイルを tar に追加し、tarxz アーカイブを作成](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}