---
date: 2026-06-29
description: Aspose.Zip for .NET を使用してフォルダーを7zに圧縮する方法を学びます。LZMA2、BZip2、Store などの Seven
  Zip 圧縮方式をカバーしています。プログラムで7zアーカイブを作成するのに最適です。
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: さまざまな圧縮方式を使用した SevenZip
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: フォルダーを7zに圧縮する方法 – Aspose.Zip for .NET チュートリアル
url: /ja/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# フォルダーを7zに圧縮する方法 – Aspose.Zip for .NET チュートリアル

## はじめに

.NET アプリケーションでプログラム的に **compress folder to 7z** アーカイブを作成する必要がある場合、ここが適切な場所です。Aspose.Zip for .NET を使用すれば、サポートされている圧縮アルゴリズムのいずれでも Seven Zip アーカイブを簡単に生成できます。ディレクトリ全体を配布用にまとめたい場合でも、信頼できる **seven zip archive .net** ソリューションが必要な場合でも、問題ありません。本ガイドでは、人気のある 3 つの圧縮方式（LZMA2、BZip2、Store（圧縮なし））を順に解説し、C# の数行コードで 7z ファイルを作成する方法を正確に示します。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Zip for .NET は Seven Zip 機能の最も完全なセットを提供します。  
- **どの圧縮方式が最も高い圧縮率を提供しますか？** LZMA2 は通常、混合データに対して最高の圧縮率を実現します。  
- **圧縮なしで 7z を作成できますか？** はい—Store（圧縮なし）方式を使用します。  
- **開発にライセンスは必要ですか？** 無料トライアルが利用可能です。製品版の使用にはライセンスが必要です。  
- **.NET 6/7 と互換性がありますか？** はい—Aspose.Zip は .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、そして .NET 5–10 をサポートしています。  

## Seven Zip の圧縮方式とは？

Seven Zip は複数のアルゴリズムをサポートしており、シナリオに応じて最適化されています。**LZMA2** は最高の圧縮率を提供します（BZip2 よりも 30‑40 % 小さくなることが多いです）。**BZip2** はレガシー ツールのサポートが広く、堅実な圧縮を提供し、**Store** はファイルを縮小せずにそのままアーカイブし、元のタイムスタンプを完全に保持します。

## 前提条件

- C# と Visual Studio の基本的な知識。  
- Aspose.Zip for .NET ライブラリがインストールされていること。公式ダウンロードページ **[こちら](https://releases.aspose.com/zip/net/)** から取得してください。  
- アーカイブしたいファイルが入ったフォルダー（`dataDir`）があること。

## 名前空間のインポート

まず、C# ファイルに必要な名前空間を追加します。

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

これらのクラスにより、圧縮設定やアーカイブの操作が可能になります。

## LZMA2 圧縮 – 最大圧縮率で 7z を作成する方法

`Archive` クラスは、�数のファイルを含む 7z アーカイブを表します。  
LZMA2 アルゴリズムは、サポートされている方式の中で最も高い圧縮率を提供します。入力をブロックに分割し、洗練された辞書圧縮を適用して動作します。Aspose.Zip では、ファイルを追加する前に `Archive` オブジェクトの `CompressionMethod` を `CompressionMethod.Lzma2` に設定します。

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **プロのコツ:** ソースファイルが 1 MB より大きい場合に LZMA2 が最適に機能します。多数の小さなファイルの場合は BZip2 の方が速いことがあります。

## BZip2 圧縮 – バランスの取れた選択

`Archive` クラスは、複数のファイルを含む 7z アーカイブを表します。  
BZip2 は、古いツールとの互換性が高く、堅実な圧縮を提供します。Burrows‑Wheeler 変換とハフマン符号化を使用してサイズを削減します。Aspose.Zip では、`Archive` インスタンスを設定する際に `CompressionMethod.BZip2` を選択し、ほとんどのテキストおよびバイナリファイルに対して速度と圧縮率のバランスを取ります。

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 は、適度な速度を保ちつつ堅実な圧縮を提供するため、対象環境が LZMA2 をサポートしていない場合の良い代替手段となります。

## Store（圧縮なし） – サイズが問題でないとき

`Archive` クラスは、複数のファイルを含む 7z アーカイブを表します。  
Store メソッドはデータを圧縮せずにアーカイブを作成します。元のファイルをそのまま 7z コンテナにコピーし、タイムスタンプとディレクトリ構造を保持します。Aspose.Zip で使用するには、バンドルしたいファイルを追加する前に `Archive` の `CompressionMethod.Store` を設定します。

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

サイズを変更せずにファイルをまとめるだけでよい場合は Store メソッドを使用してください—元のタイムスタンプを保持したい場合や、アーカイブがリアルタイムで解凍される場合に最適です。

## 7z にファイルを追加する方法は？

`Archive` インスタンスを作成し、目的の `CompressionMethod` を設定し、`AddAllFiles(dataDir)` を呼び出すことで 7z アーカイブにファイルを追加できます。このメソッドは指定されたフォルダーを再帰的に走査し、アーカイブ内にディレクトリ階層を保持します。このアプローチにより、初期設定の後にコード一行で **compress folder to 7z** が可能になります。

## 一般的な使用例

| シナリオ | 推奨方法 |
|----------|--------------------|
| 大規模インストーラーの配布 | LZMA2 |
| レガシーツールでログを共有 | BZip2 |
| 迅速な展開のためにファイルをパッケージ化 | Store（圧縮なし） |
| Web サービスでリアルタイムに **compress folder to 7z** が必要 | LZMA2（最高の圧縮率） |

## トラブルシューティングとヒント

- **アーカイブにファイルが欠けていますか？** `dataDir` が正しいディレクトリを指していること、プロセスに読み取り権限があることを確認してください。  
- **古い 7‑Zip バージョンでアーカイブが開けませんか？** LZMA2 は新しい解凍ライブラリが必要になることがあるため、BZip2 または Store を使用してください。  
- **パフォーマンスのボトルネックですか？** 大規模データセットの場合、すべてのエントリをメモリにロードする代わりにアーカイブをストリーミングすることを検討してください。  

## よくある質問

**Q: Aspose.Zip for .NET は任意の種類のファイルで使用できますか？**  
A: はい、Aspose.Zip は幅広いファイル形式をサポートしており、実質的にすべてのファイルタイプを圧縮および解凍できます。

**Q: Aspose.Zip for .NET の無料トライアルは利用可能ですか？**  
A: はい、無料トライアルは **[こちら](https://releases.aspose.com/)** から取得できます。

**Q: Aspose.Zip for .NET のドキュメントはどこで見つけられますか？**  
A: 完全な API リファレンスは **[こちら](https://reference.aspose.com/zip/net/)** で利用可能です。

**Q: Aspose.Zip for .NET の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは **[こちら](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: Aspose.Zip for .NET のサポートはどこで受けられますか？**  
A: **[Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37)** でサポートを受けられます。

---

**最終更新日:** 2026-06-29  
**テスト環境:** Aspose.Zip for .NET 24.12  
**作者:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [C# でファイルを圧縮 – Aspose.Zip for .NET で 7z アーカイブを作成](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Aspose.Zip for .NET を使用してフォルダーを Zip する方法](/zip/net/directory-and-folder-compression/compress-directory/)
- [Aspose.Zip for .NET で LZMA を圧縮する方法](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}