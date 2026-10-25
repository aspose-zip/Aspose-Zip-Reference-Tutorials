---
date: 2026-10-25
description: Aspose.Zip for .NET を使用して zip パスワードを抽出し、tar ファイルを圧縮する際に compression algorithm
  を設定する方法を学び、storage efficiency と security を向上させます。
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: アーカイブ抽出とフォーマット
og_description: Aspose.Zip for .NET を使用して zip パスワードを抽出し、tar ファイルを圧縮する際に compression
  algorithm を設定する方法を学び、storage efficiency と security を向上させます。
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Aspose.Zip を使用して zip パスワードを抽出し、tar ファイルを圧縮
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Aspose.Zip を使用して zip パスワードを抽出し、tar ファイルを圧縮
url: /ja/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zip パスワードの抽出と Aspose.Zip を使用した tar ファイルの圧縮

## はじめに

このガイドでは **extract zip password** の手法を紹介し、tar ベースのアーカイブを作成する際の圧縮アルゴリズムの設定方法を学び、Aspose.Zip for .NET を使って TarGz、TarBz2、その他の形式を構築する方法を示します。バックアップサービス、クラウドストレージクライアント、データ処理パイプラインの構築に関わる方は、これらの操作をマスターすることでストレージコストを削減し、転送速度を向上させ、機密ファイルを保護できます。

## クイック回答
- **TarBz2 とは？** TAR パッケージに BZIP2 圧縮を組み合わせた高圧縮率のアーカイブです。  
- **なぜ Aspose.Zip for .NET を選ぶのか？** 50 以上のアーカイブ・圧縮形式に対応し、Windows、Linux、macOS で動作し、数百メガバイト規模のアーカイブでもメモリ使用量を 10 MB 未満に抑えます。  
- **TarGz アーカイブは作成できるか？** はい – Aspose.Zip は TarGz、TarLz、TarXz、TarZ などを提供しています。  
- **パスワード保護された zip アーカイブを抽出するには？** `Extract` を呼び出す前に各 `ArchiveEntry` の `Password` プロパティを設定します。  
- **本番利用にライセンスは必要か？** 本番環境では商用ライセンスが必要です。評価用の無料トライアルも利用可能です。

## tar 圧縮とは？

tar 圧縮は TAR コンテナに BZIP2、GZIP、LZMA、XZ などの圧縮アルゴリズムを組み合わせたものです。結果として単一ファイル（例: `.tar.gz`、`.tar.bz2`）が生成され、Linux、macOS、Windows で展開できます。元のディレクトリ階層を保持し、ランダムアクセス抽出を可能にし、コマンドラインツールやプログラミングライブラリで広くサポートされているため、クロスプラットフォーム配布やアーカイブ保存に最適です。

## .NET でこれらの形式を扱うために Aspose.Zip を使う理由

Aspose.Zip は統一された依存関係のない API を提供し、**50+** のアーカイブ・圧縮形式に対応しています。主要な tar 系形式すべてをサポートし、ストリーミングアーキテクチャにより 10 GB を超えるアーカイブでも RAM 使用量を 10 MB 未満に抑えて処理できます。  

**直接的な回答:** Aspose.Zip を使用すれば、外部ツールを必要とせず、単一のフルエント API で tar 系アーカイブやパスワード保護 zip の作成・圧縮・抽出が可能で、メモリ効率の高いストリーミングモードでマルチギガバイトのアーカイブも扱えます。

## 前提条件
- .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、または .NET 5–10。  
- Aspose.Zip for .NET NuGet パッケージ (`Install-Package Aspose.Zip`)。  
- C# のファイル I/O と .NET プロジェクトシステムに関する基本的な知識。

## ステップバイステップ ガイド

### tar ファイルの圧縮方法 – 直接的な回答
`Archive` インスタンスを作成し、バンドルしたいファイルを追加、`CompressionType.BZip2`（または他のアルゴリズム）を設定し、`ArchiveFormat.TarBz2` を指定して `Save` を呼び出します。ライブラリは TAR コンテナを書き込み、ストリーミングで圧縮を行うため、アーカイブ全体をメモリに読み込むことはありません。

### 手順 1: 必要なアーカイブ形式を選択
圧縮率と速度のトレードオフに合わせて、以下の tar 系形式から選びます：

- **TarBz2** – 最高の圧縮率（TarGz より約30 % 小さく）ですが速度は遅め。  
- **TarGz** – 速度とサイズのバランスが良く、ほとんどのクラウドストレージシナリオに最適。  
- **TarLz / TarXz** – 圧縮率は非常に高く、速度は中程度。アーカイブ保存に有用。  
- **TarZ** – 旧式の Unix ツールとの互換性のためのレガシーフォーマット。

### 手順 2: 新しい `Archive` インスタンスを作成
`Archive` は単一のアーカイブファイルを表し、エントリの追加や保存メソッドを提供します。  

`Archive` クラスはパッキングと圧縮のワークフローを管理し、エントリ追加や最終ファイル書き込みのメソッドを公開します。

### 手順 3: ファイルとフォルダーを追加
`AddAll` でディレクトリツリー全体を追加したり、`AddFile` で個別ファイルを追加したりできます。  

`AddAll` はディレクトリツリー全体をアーカイブに追加し、構造を保持します。  
`AddFile` は単一ファイルをアーカイブに追加します。元のフォルダー階層はベースディレクトリパスを渡すだけで保持されます。

### 手順 4: 圧縮タイプを設定
`CompressionType` 列挙体は TAR ストリームに適用する圧縮アルゴリズムを指定します。  

`CompressionType` には BZip2、GZip、LZMA、XZ など、サポートされているアルゴリズムが列挙されています。

### 手順 5: アーカイブを保存
`ArchiveFormat` 列挙体で出力ファイルのコンテナと圧縮の組み合わせを選択します。  

`Save` を呼び出すと、選択した形式でディスクにアーカイブが書き込まれます。

### 手順 6: パスワード付きアーカイブの抽出
`ArchiveEntry` はアーカイブ内の単一ファイルまたはディレクトリエントリを表します。  

パスワード保護された zip を抽出するには、アーカイブを開き各 `ArchiveEntry` を取得し、`Password` プロパティにパスワードを設定してから `Extract` を呼び出します。`Password` プロパティは zip エントリの復号パスワードを設定します。このエントリ単位のパスワードモデルにより、単一 zip 内の個別ファイルを保護できます。

### 手順 7: 結果を検証
抽出後、ファイルサイズと SHA‑256 チェックサムを比較し、アーカイブの往復でデータ整合性が保たれたことを確認します。

## 主なユースケース
- **バックアップユーティリティ** – `.tar.bz2` で日次バックアップを保存し、最大 30 % のストレージコスト削減を実現。  
- **クロスプラットフォームデータ交換** – Tar 系形式は Linux、macOS、Windows のツールでネイティブに扱える。  
- **安全な配布** – 敏感なエントリにパスワードを設定し、追加の暗号化ツールなしでコンプライアンス要件を満たす。

## トラブルシューティングとヒント
- **大容量アーカイブ** – ストリーミング API (`Archive.CreateEntryFromFile`) を使用してメモリ使用量を抑える。  
- **パスワード不一致** – 各 `ArchiveEntry` に設定したパスワードは完全に一致する必要があり、違うと `InvalidPasswordException` がスローされます。  
- **圧縮レベル** – BZIP2 はカスタムレベルを公開していません。より細かい制御が必要な場合は LZMA (`CompressionType.LZMA`) または XZ (`CompressionType.XZ`) に切り替えてください。

## よくある質問

**Q: TarGz アーカイブはどうやって作成しますか？**  
A: `CompressionType.GZip` を設定し、`Save` 呼び出し時に `ArchiveFormat.TarGz` を指定します。これだけで `.tar.gz` ファイルが生成されます。

**Q: パスワード保護されたアーカイブをパスワードなしで抽出できますか？**  
A: できません。各エントリに正しいパスワードを提供する必要があり、そうでなければ `InvalidPasswordException` が発生します。

**Q: Aspose.Zip はエントリごとに異なるパスワードでの抽出をサポートしていますか？**  
A: はい。`Extract` を呼び出す前に各 `ArchiveEntry` に個別にパスワードを割り当てます。

**Q: どの形式が最も高い圧縮率を提供しますか？**  
A: 通常、TarBz2 が最小サイズを実現し、次に TarLz と TarXz が続きます。TarGz は高速でありながら十分な圧縮率を提供します。

**Q: TAR アーカイブに追加できるファイル数に上限はありますか？**  
A: 実質的な上限はありませんが、極めて大きなアーカイブ（>10 GB）では取り扱いを容易にするために複数パートに分割することを検討してください。

## アーカイブ抽出と形式のチュートリアル
### [File Compressing to TarBz2 with Aspose.Zip for .NET](./compress-to-tar-bz2/)
Aspose.Zip を使用して .NET でファイルを TarBz2 形式に圧縮する方法を学びます。効率的なファイル圧縮のステップバイステップガイドです。  
### [Compressing to TarGz with Aspose.Zip for .NET](./compress-to-tar-gz/)
Aspose.Zip で .NET のファイルを TarGz に圧縮する方法を探ります。手軽に TarGz 圧縮が可能です。  
### [Compressing to TarLz with Aspose.Zip for .NET](./compress-to-tar-lz/)
Aspose.Zip を使用して .NET でファイルを TarLz アーカイブに圧縮する手順を学びます。  
### [Compressing to TarXz with Aspose.Zip for .NET](./compress-to-tar-xz/)
Aspose.Zip を利用して .NET でファイルを TarXz 形式に圧縮する方法を紹介します。効率的な保存と転送のためのガイドです。  
### [Compressing to TarZ with Aspose.Zip for .NET](./compress-to-tar-z/)
Aspose.Zip for .NET を使った TarZ 圧縮のステップバイステップチュートリアルです。 .NET プロジェクトでの効率的なファイル処理を実現します。  
### [Extracting archive entries with different passwords in Aspose.Zip for .NET](./extract-archive-different-passwords/)
Aspose.Zip for .NET でエントリごとに異なるパスワードを持つアーカイブを抽出する方法を学びます。アプリケーションのセキュリティと柔軟性を向上させます。

## 関連チュートリアル

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [How to compress tar and create TarBz2 with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Add files to tar and create tarxz archive with Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**最終更新日:** 2026-10-25  
**テスト環境:** Aspose.Zip for .NET 24.11  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}