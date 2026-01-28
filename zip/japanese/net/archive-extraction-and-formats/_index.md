---
date: 2026-01-28
description: Aspose.Zip for .NET を使用して、パスワード付きアーカイブの抽出、ファイルを TarBz2 に圧縮、TarGz アーカイブの作成方法を学びましょう。ストレージの効率とセキュリティを向上させます。
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: パスワード付きアーカイブを抽出し、TarBz2に圧縮 (.NET)
url: /ja/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# パスワード付きアーカイブの抽出と TarBz2 への圧縮 (.NET)

このガイドでは、Aspose.Zip for .NET を使用して **パスワード付きアーカイブの抽出方法** と **TarBz2 へのファイル圧縮** をマスターできます。バックアップサービス、クラウドストレージクライアント、データ処理パイプラインの構築に関わらず、これらの手法によりストレージ容量を削減し、転送速度を向上させ、機密データを保護できます。

## Quick Answers
- **TarBz2 とは何ですか？** TAR パッケージングと BZIP2 圧縮を組み合わせた圧縮アーカイブで、高い圧縮率を実現します。  
- **なぜ Aspose.Zip for .NET を選ぶのですか？** ネイティブ依存関係が不要で、さまざまなアーカイブ形式に対して単一の流暢な API を提供します。  
- **TarGz アーカイブを作成できますか？** はい – Aspose.Zip は TarGz、TarLz、TarXz、TarZ などをサポートしています。  
- **パスワードで保護されたアーカイブを抽出するには？** 抽出前に各 `ArchiveEntry` の `Password` プロパティを設定します。  
- **本番環境で使用するにはライセンスが必要ですか？** 本番利用には商用ライセンスが必要です。評価用に無料トライアルが利用可能です。

## How to extract archive with password using Aspose.Zip for .NET
**パスワードで保護された zip アーカイブ** を抽出するのは簡単です。アーカイブを開き、必要なエントリを見つけ、パスワードを割り当て、`Extract` を呼び出すだけです。この方法は TarBz2、TarGz などのサポートされている形式でも機能します。

## What does “compress files to TarBz2” actually mean?
ファイルを TarBz2 に圧縮するとは、まず複数のファイルやディレクトリを単一の **TAR** コンテナにまとめ、次に **BZIP2** 圧縮を適用することです。その結果、転送が容易で高圧縮率の `.tar.bz2` ファイルが生成されます。

## Why use Aspose.Zip for .NET to handle these formats?
- **統一 API** – 1 つのライブラリで多数の形式（TarBz2、TarGz、TarLz、TarXz、TarZ）を扱えます。  
- **ネイティブ依存なし** – Windows、Linux、macOS でそのまま動作します。  
- **パスワードサポート** – エントリ単位のパスワードでアーカイブを安全に保護・抽出できます。  
- **パフォーマンス重視** – ストリームベースの処理でメモリ使用量を最小化します。

## Prerequisites
- .NET 6.0 以降（または .NET Core 3.1+ / .NET Framework 4.5+）。  
- Aspose.Zip for .NET の NuGet パッケージがインストールされていること（`Install-Package Aspose.Zip`）。  
- C# とファイル I/O の基本知識。

## Step‑by‑Step Guide

### Step 1: Choose the archive format you need
**TarBz2**、**TarGz**、**TarLz**、**TarXz**、または **TarZ** のどれが圧縮率と互換性の要件に最適かを決定します。  
- **TarBz2** – 最高の圧縮率、処理は遅め。  
- **TarGz** – 速度とサイズのバランスが良い（二次キーワード *compress files to targz* を含む）。  
- **TarZ** – 古い Unix ツール向けのレガシーフォーマット。

### Step 2: Create a new `Archive` instance
`Archive` クラスのインスタンスを作成し、出力ファイルパスを指定します。このオブジェクトがパッキングと圧縮プロセスを管理します。

### Step 3: Add files and folders
圧縮したいファイルを追加するには `AddAll` または `AddFile` メソッドを使用します。ベースフォルダーを追加してディレクトリ構造を保持します。

### Step 4: Set the desired compression type
アーカイブを保存する際に圧縮アルゴリズム（`CompressionType.BZip2`、`CompressionType.GZip` など）を指定します。ここで実際に **compress files to tarbz2** や他の形式に圧縮します。

### Step 5: Save the archive
適切な形式列挙体（`ArchiveFormat.TarBz2`、`ArchiveFormat.TarGz` など）を指定して `Save` を呼び出します。ライブラリは TAR コンテナを書き込み、選択した圧縮を一度の処理で適用します。

### Step 6: Extract archives with passwords
**異なるパスワードでアーカイブエントリを抽出する** 必要がある場合（二次キーワード *how to extract password protected archive*）、アーカイブを開き、各エントリを見つけ、パスワードを割り当て、抽出します。

### Step 7: Verify the result
抽出後、ファイルサイズとチェックサムを比較して、アーカイブが正しく作成・展開されたことを確認します。

## Common Use Cases
- **バックアップユーティリティ** – ストレージコスト削減のため、日次バックアップを `.tar.bz2` として保存します。  
- **クロスプラットフォームデータ交換** – Tar 系フォーマットは Linux、macOS、Windows で普遍的に理解されます。  
- **安全な配布** – コンプライアンス重視の環境向けに、個々のエントリをパスワードで保護します。

## Troubleshooting & Tips
- **大規模アーカイブ** – `Archive.CreateEntryFromFile` などのストリーミング API を使用して、ファイル全体をメモリに読み込むのを回避します。  
- **パスワード不一致** – 各 `ArchiveEntry` に設定したパスワードが抽出時に使用したものと一致していることを確認してください。そうでないと `InvalidPasswordException` が発生します。  
- **サポートされていない圧縮レベル** – BZIP2 はカスタム圧縮レベルをサポートしていません。より細かい制御が必要な場合は TarLz または TarXz を検討してください。  
- **パフォーマンスのヒント** – **create tarbz2 archive** を作成する際は、基礎となるストリームでバッファリングを有効にして書き込み速度を向上させます。

## Frequently Asked Questions

**Q: TarGz アーカイブはどう作成しますか？**  
A: `Save` 呼び出し時に圧縮タイプを `CompressionType.GZip`、形式を `ArchiveFormat.TarGz` に設定します。

**Q: パスワードが分からなくてもパスワード保護されたアーカイブを抽出できますか？**  
A: できません。各エントリに正しいパスワードを提供する必要があり、そうでなければ抽出は失敗します。

**Q: Aspose.Zip はエントリごとに異なるパスワードでアーカイブを抽出することをサポートしていますか？**  
A: はい。抽出前に各 `ArchiveEntry` に個別にパスワードを割り当てることができます。

**Q: どの形式が最も高い圧縮率を提供しますか？**  
A: 通常、TarBz2 が最も高い圧縮率を提供し、次に TarLz と TarXz が続きます。TarGz は速度とサイズのバランスが良いです。

**Q: TAR アーカイブに追加できるファイル数に制限はありますか？**  
A: 実質的にはありませんが、極めて大きなアーカイブは取り扱いを容易にするために複数のパートに分割した方が良い場合があります。

## Archive Extraction and Formats Tutorials
### [Aspose.Zip for .NET を使用した TarBz2 へのファイル圧縮](./compress-to-tar-bz2/)
### [Aspose.Zip for .NET を使用した TarGz への圧縮](./compress-to-tar-gz/)
### [Aspose.Zip for .NET を使用した TarLz への圧縮](./compress-to-tar-lz/)
### [Aspose.Zip for .NET を使用した TarXz への圧縮](./compress-to-tar-xz/)
### [Aspose.Zip for .NET を使用した TarZ への圧縮](./compress-to-tar-z/)
### [Aspose.Zip for .NET でエントリごとに異なるパスワードでアーカイブエントリを抽出する方法](./extract-archive-different-passwords/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-01-28  
**テスト環境:** Aspose.Zip for .NET 24.11  
**作者:** Aspose  

---