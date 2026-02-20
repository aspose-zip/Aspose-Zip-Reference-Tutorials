---
date: 2026-02-20
description: Aspose.Zip for .NET を使用して、tarbz2 ファイルの圧縮方法、targz アーカイブの作成方法、パスワード保護された
  zip の抽出を含む .NET アーカイブ抽出方法を学びましょう。ストレージの効率とセキュリティを向上させます。
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET 用 Aspose.Zip で TarBz2 ファイルを圧縮する方法
url: /ja/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した TarBz2 ファイルの圧縮方法

## はじめに

このガイドでは、Aspose.Zip for .NET を使用して **tarbz2 ファイルの圧縮方法** を学びながら、TarGz アーカイブの作成方法やパスワード保護された zip ファイルの .net アーカイブ抽出方法も紹介します。効率的なファイル処理は最新の .NET 開発の基盤であり、これらの形式をマスターすることで、ストレージコストの削減、データ転送速度の向上、機密情報の保護が可能になります。バックアップサービス、クラウドストレージクライアント、データ処理パイプラインの構築など、ここで取り上げる技術はファイル管理タスクをよりスムーズかつ信頼性の高いものにします。

## クイック回答
- **What is TarBz2?** TAR パッケージングと BZIP2 圧縮を組み合わせた高圧縮率の圧縮アーカイブです。  
- **Why choose Aspose.Zip for .NET?** 外部依存なしで多数のアーカイブ形式の作成と抽出ができる単一のフルエント API を提供します。  
- **Can I create a TarGz archive?** はい – Aspose.Zip は TarGz、TarLz、TarXz、TarZ などをサポートしています。  
- **How do I extract a password‑protected zip archive?** 抽出時に `ArchiveEntry` オブジェクトの `Password` プロパティを使用します。  
- **Do I need a license for production use?** 本番環境では商用ライセンスが必要です。評価用に無料トライアルが利用可能です。

## TarBz2 ファイルの圧縮方法

ファイルを TarBz2 に圧縮するとは、まず複数のファイルやディレクトリを単一の **TAR** コンテナにまとめ、次に **BZIP2** 圧縮を適用することを意味します。その結果、転送が容易で高圧縮率の単一の `.tar.bz2` ファイルが生成されます。

## これらの形式を扱う際に Aspose.Zip for .NET を使用する理由

- **Unified API** – 1 つのライブラリで多数の形式（TarBz2、TarGz、TarLz、TarXz、TarZ）に対応します。  
- **No native dependencies** – Windows、Linux、macOS で追加のネイティブ依存なしに動作します。  
- **Password support** – エントリごとのパスワードでアーカイブを安全に保護および抽出できます。  
- **Performance‑focused** – ストリームベースの処理によりメモリ使用量を最小化します。

## 前提条件

- .NET 6.0 以降（または .NET Core 3.1+ / .NET Framework 4.5+）。  
- Aspose.Zip for .NET の NuGet パッケージがインストールされていること（`Install-Package Aspose.Zip`）。  
- C# とファイル I/O の基本的な理解。

## 手順ガイド

### 手順 1: 必要なアーカイブ形式を選択

**TarBz2**、**TarGz**、**TarLz**、**TarXz**、または **TarZ** のどれが圧縮率と互換性の要件に最適かを決定します。  
- **TarBz2** – 最高の圧縮率だが処理は遅め。  
- **TarGz** – 速度とサイズのバランスが良い（二次キーワード *how to create targz* をカバー）。  
- **TarZ** – レガシー形式で、古い Unix ツールとの互換性に有用です。

### 手順 2: 新しい `Archive` インスタンスを作成

`Archive` クラスのインスタンスを作成し、出力ファイルパスを指定します。このオブジェクトがパッキングと圧縮のプロセスを管理します。

### 手順 3: ファイルとフォルダーを追加

`AddAll` または `AddFile` メソッドを使用して圧縮したいファイルを追加します。ベースフォルダーを追加することでディレクトリ構造を保持できます。

### 手順 4: 希望する圧縮タイプを設定

アーカイブを保存する際に圧縮アルゴリズム（`CompressionType.BZip2`、`CompressionType.GZip` など）を指定します。ここで実際に **TarBz2 にファイルを圧縮** したり、他の形式に圧縮したりします。

### 手順 5: アーカイブを保存

適切なフォーマット列挙子（`ArchiveFormat.TarBz2`、`ArchiveFormat.TarGz` など）を指定して `Save` を呼び出します。ライブラリは TAR コンテナを書き込み、選択した圧縮を一度の処理で適用します。

### 手順 6: パスワード付きアーカイブの抽出

**エントリごとに異なるパスワードでアーカイブエントリを抽出** する必要がある場合（二次キーワード *password protected zip extraction*）、アーカイブを開き、各エントリを見つけてパスワードを割り当て、抽出します。

### 手順 7: 結果を検証

抽出後、ファイルサイズとチェックサムを比較して、アーカイブが正しく作成・展開されたことを確認します。

## 一般的なユースケース

- **Backup utilities** – ストレージコストを削減するために、日次バックアップを `.tar.bz2` として保存します。  
- **Cross‑platform data exchange** – Tar 系形式は Linux、macOS、Windows で普遍的に理解されます。  
- **Secure distribution** – コンプライアンス重視の環境向けに、個々のエントリをパスワードで保護します。

## トラブルシューティングとヒント

- **Large archives** – ストリーミング API（`Archive.CreateEntryFromFile`）を使用して、ファイル全体をメモリに読み込むのを回避します。  
- **Password mismatches** – 各 `ArchiveEntry` に設定したパスワードが抽出時に使用したものと一致していることを確認してください。一致しない場合、`InvalidPasswordException` が発生します。  
- **Unsupported compression level** – BZIP2 はカスタム圧縮レベルをサポートしていません。より細かい制御が必要な場合は TarLz または TarXz を検討してください。

## よくある質問

**Q: How do I create a TarGz archive?**  
A: `Save` 呼び出し時に圧縮タイプを `CompressionType.GZip`、フォーマットを `ArchiveFormat.TarGz` に設定します。

**Q: Can I extract a password‑protected archive without knowing the password?**  
A: できません。各エントリには正しいパスワードを提供する必要があり、そうでなければ抽出は失敗します。

**Q: Does Aspose.Zip support extracting archives with different passwords per entry?**  
A: はい。抽出前に各 `ArchiveEntry` に個別にパスワードを割り当てることができます。

**Q: Which format gives the best compression?**  
A: 通常、TarBz2 が最も高い圧縮率を提供し、次に TarLz と TarXz が続きます。TarGz は速度とサイズのバランスが良いです。

**Q: Is there a limit to the number of files I can add to a TAR archive?**  
A: 実質的に制限はありませんが、極めて大きなアーカイブは取り扱いを容易にするために複数パートに分割した方が良い場合があります。

## アーカイブ抽出と形式のチュートリアル

### [Aspose.Zip for .NET を使用した TarBz2 へのファイル圧縮](./compress-to-tar-bz2/)
Aspose.Zip を使用して .NET でファイルを TarBz2 形式に圧縮する方法を学びます。効率的なファイル圧縮のためのステップバイステップガイドに従ってください。

### [Aspose.Zip for .NET を使用した TarGz への圧縮](./compress-to-tar-gz/)
Aspose.Zip を使用して .NET で効率的なファイル圧縮を体験してください。簡単に TarGz に圧縮できます。

### [Aspose.Zip for .NET を使用した TarLz への圧縮](./compress-to-tar-lz/)
Aspose.Zip を使用して .NET でファイルを簡単に圧縮します。ステップバイステップで TarLz アーカイブの作成方法を学びます。

### [Aspose.Zip for .NET を使用した TarXz への圧縮](./compress-to-tar-xz/)
Aspose.Zip を使用して .NET でファイルを TarXz 形式に圧縮する方法を学びます。効率的なファイル保存と転送のためのステップバイステップガイドに従ってください。

### [Aspose.Zip for .NET を使用した TarZ への圧縮](./compress-to-tar-z/)
Aspose.Zip for .NET を使用して TarZ にステップバイステップで圧縮する方法を探ります。 .NET プロジェクトの効率的なファイル処理に役立ちます。

### [Aspose.Zip for .NET で異なるパスワードのアーカイブエントリを抽出する方法](./extract-archive-different-passwords/)
Aspose.Zip for .NET で異なるパスワードを持つアーカイブエントリを抽出する方法を学びます。アプリケーションのセキュリティと柔軟性を向上させます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-02-20  
**テスト環境:** Aspose.Zip for .NET 24.11  
**作者:** Aspose