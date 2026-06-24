---
date: 2026-06-24
description: Aspose.Zip for .NET で LZMA を圧縮し、ストレージとデータ転送の効率を最適化する方法を学びます。
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: LZMA に圧縮
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET で LZMA を圧縮する方法
url: /ja/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET で LZMA を圧縮する方法

## はじめに

このチュートリアルでは、Aspose.Zip for .NET で **LZMA を圧縮する方法** を学びます。これは、ストレージ容量の最適化とデータ転送効率の向上に不可欠なスキルです。LZMA（Lempel‑Ziv‑Markov chain アルゴリズム）は、従来の ZIP と比較して最大 70 % 小さなアーカイブを実現し、かつ高速な解凍を維持するため、帯域幅が制限されたシナリオに最適です。

## クイック回答
- **必要なライブラリは？** Aspose.Zip for .NET  
- **このガイドで扱うアルゴリズムは？** LZMA 圧縮  
- **ライセンスは必要ですか？** テストには一時ライセンスで十分ですが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、そして .NET 5–10  
- **実装にかかる時間は？** 基本的なファイルで通常 10 分未満です。

## LZMA 圧縮とは？

LZMA は、辞書圧縮とレンジエンコーディングを使用する高圧縮率のロスレス圧縮アルゴリズムです。テキストファイルを 30‑70 % 縮小でき、解凍速度は ZIP と同等です。大規模データセットにおいて、LZMA はストレージコストを削減し、データの完全性を損なうことなくネットワーク転送を高速化します。

## なぜ Aspose.Zip を LZMA に使用するのか？

Aspose.Zip は **5 つの圧縮アルゴリズム**（ZIP、Deflate、BZIP2、LZMA、ZSTD）をサポートし、**4 GB** までのアーカイブをメモリに全体を読み込まずに処理できます。一般的なサーバー上で数百ページのドキュメントを **2 秒** 未満で処理でき、パフォーマンスとスケーラビリティの両方を提供します。

## 前提条件

始める前に、以下が揃っていることを確認してください：

- Aspose.Zip for .NET: Aspose.Zip ライブラリがインストールされていることを確認してください。ドキュメントは[こちら](https://reference.aspose.com/zip/net/)にあります。
- ドキュメントディレクトリ: 圧縮したいファイルが入っているフォルダーを選択または作成してください。

## 名前空間のインポート

C# ファイルの先頭に必要な名前空間を追加し、Aspose.Zip の LZMA 機能にアクセスできるようにします:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## 圧縮のためのソースフォルダーはどう設定しますか？

アーカイブ対象のファイルが格納されているフォルダーを指定します。専用のソースディレクトリを用意することで、意図したファイルだけが処理され、不要なデータが含まれるリスクが減少し、同一プロジェクト内で複数の圧縮タスクを扱う際のパス管理がシンプルになります。

```csharp
string dataDir = "Your Document Directory";
```

## LZMA を使用してファイルを圧縮する方法

`LzmaArchive` は、LZMA アーカイブの作成と管理を行う Aspose.Zip のクラスです。

`LzmaArchive` インスタンスを作成し、ソースファイルを指定して `Save` を呼び出すと、`.lzma` アーカイブが生成されます。この 2 行のパターンで圧縮の全工程が実行され、ストリーム管理は内部で処理され、配布や保存に適したコンパクトなファイルが生成されます。

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## 圧縮が成功したことを確認する方法

`Console.WriteLine` は標準出力コンソールにテキスト行を書き込みます。

アーカイブが保存された後、`Console.WriteLine` を使用して簡単な確認メッセージを出力します。この即時フィードバックにより、開発者は圧縮ステップがエラーなく完了したことを確認でき、自動ビルド時のデバッグが容易になり、ルーチンを大規模なアプリケーションやスクリプトに統合した際に明確なステータス情報を提供します。

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## よくある問題と解決策

- **ファイルが見つかりません** – パス文字列が二重バックスラッシュ (`\\`) または逐語的文字列 (`@"C:\\Path"`) を使用しているか確認してください。  
- **メモリ不足** – Aspose.Zip はデータをストリーミングしますが、極めて大きなファイルではプロセスのメモリ上限を増やす必要がある場合があります。  
- **ライセンスが適用されていません** – 任意の Aspose.Zip 操作の前に `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` を呼び出していることを確認してください。

## よくある質問

**Q: 複数のファイルを単一の LZMA アーカイブに圧縮できますか？**  
A: はい。`archive.Save()` を呼び出す前に各ファイルに対して `archive.AddFile()` を実行してください。

**Q: LZMA の圧縮レベルを設定する方法はありますか？**  
A: `LzmaArchive` クラスはデフォルトの圧縮レベルを使用し、速度とサイズのバランスが良好です。細かい制御が必要な場合は `LzmaEncoder` を通じて高度な設定が利用可能です。

**Q: 作成された .lzma ファイルは非 Windows プラットフォームでも動作しますか？**  
A: 完全に対応しています。LZMA フォーマットはプラットフォームに依存しないため、LZMA 対応ツールがあれば任意の OS で解凍できます。

**Q: Aspose.Zip を使用して LZMA アーカイブを解凍するには？**  
A: アーカイブパスを指定して `LzmaArchive` コンストラクタを使用し、続いて `ExtractToDirectory()` を呼び出して内容を抽出します。

**Q: Aspose.Zip はストリーミング圧縮をサポートし、ファイル全体をメモリにロードせずに済みますか？**  
A: はい。`SetSource()` と `Save()` メソッドに `Stream` オブジェクトを渡すことで、ストリームでの処理が可能です。

---

**最終更新日:** 2026-06-24  
**テスト環境:** Aspose.Zip for .NET（執筆時点での最新バージョン）  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Zip for .NET でファイルを圧縮する方法](/zip/net/file-compression/compress-file/)
- [Aspose.Zip for .NET で GZip アーカイブやその他の圧縮手法を開く方法](/zip/net/other-compression-techniques/)
- [C# でファイルを圧縮 – Aspose.Zip for .NET を使用した 7z アーカイブの作成](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}