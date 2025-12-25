---
date: 2025-12-25
description: Aspose.Zip for .NET を使用して 7z ファイルの作成方法を学び、LZMA2、BZip2、Store などの 7z 圧縮方式を網羅します。フォルダーを
  7z に圧縮するシナリオに最適です。
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 7zファイルの作成方法 – Aspose.Zip for .NET チュートリアル
url: /ja/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 7z ファイルの作成方法 – Aspose.Zip for .NET チュートリアル

## はじめに

.NET アプリケーションで **7z アーカイブをプログラムで作成する方法** が必要な場合、ここが最適な場所です。Aspose.Zip for .NET を使用すれば、サポートされている任意の圧縮アルゴリズムで Seven Zip アーカイブを簡単に生成できます。配布用に **フォルダーを 7z に圧縮** したい場合や、信頼性の高い **seven zip archive .net** ソリューションが必要な場合にも対応しています。本ガイドでは、LZMA2、BZip2、Store（圧縮なし）の 3 つの一般的な圧縮方法を取り上げ、数行の C# コードで 7z ファイルを作成する手順を詳しく解説します。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Zip for .NET が最も完全な Seven Zip 機能を提供します。  
- **どの圧縮方式が最も高い圧縮率を実現しますか？** LZMA2 が混合データに対して通常最高の圧縮率を提供します。  
- **圧縮なしで 7z を作成できますか？** はい、Store（圧縮なし）方式を使用します。  
- **開発用にライセンスは必要ですか？** 無料トライアルがありますが、本番環境で使用する場合はライセンスが必要です。  
- **.NET 6/7 と互換性がありますか？** 完全に対応しています。Aspose.Zip は .NET Framework、.NET Core、.NET 5 以降をサポートします。

## Seven Zip 圧縮方式とは？

Seven Zip はシナリオに応じて最適化された複数のアルゴリズムをサポートしています。

* **LZMA2** – 高い圧縮率を実現し、大容量の混合タイプファイルに最適です。  
* **BZip2** – 圧縮率は高いものの LZMA2 より遅く、古いツールとの互換性が必要な場合に有用です。  
* **Store** – 圧縮なし。サイズ削減が不要で、元のファイルタイムスタンプを保持したい場合に最適です。

これらの **seven zip compression methods** を理解することで、プロジェクトに最適な設定を選択できます。

## 前提条件

作業を始める前に、以下を用意してください。

- C# と Visual Studio の基本的な知識。  
- Aspose.Zip for .NET ライブラリのインストール。公式ダウンロードページ **[here](https://releases.aspose.com/zip/net/)** から取得できます。  
- アーカイブしたいファイルが入っているフォルダー（`dataDir`）。

## 名前空間のインポート

まず、C# ファイルに必要な名前空間を追加します。

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

これらのクラスにより、圧縮設定やアーカイブ操作にアクセスできます。

## LZMA2 圧縮 – 最大圧縮率で 7z を作成する方法

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

> **プロのコツ:** LZMA2 はソースファイルが 1 MB 以上の場合に最適に機能します。多数の小さなファイルでは BZip2 の方が高速になることがあります。

## BZip2 圧縮 – バランスの取れた選択

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 は適度な速度でしっかりとした圧縮率を提供し、ターゲット環境で LZMA2 がサポートされていない場合の良い代替手段です。

## Store（圧縮なし） – サイズが問題でないとき

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

サイズを変更せずにファイルをまとめたい場合は Store 方法を使用します。元のタイムスタンプを保持したいときや、アーカイブをその場で解凍するシナリオに最適です。

## 一般的な使用例

| シナリオ | 推奨方法 |
|----------|--------------------|
| 大容量インストーラの配布 | LZMA2 |
| 旧ツールでログを共有 | BZip2 |
| 素早い展開が必要なパッケージ | Store (no compression) |
| Web サービスで **フォルダーを 7z に圧縮** したい | LZMA2（最高の圧縮率） |

## トラブルシューティングとヒント

- **アーカイブにファイルが欠けていますか？** `dataDir` が正しいディレクトリを指しているか、プロセスに読み取り権限があるか確認してください。  
- **古い 7‑Zip バージョンでアーカイブが開けませんか？** LZMA2 は新しい解凍ライブラリを必要とすることがあるため、BZip2 または Store を使用してください。  
- **パフォーマンスがボトルネックになっていますか？** 大規模データセットの場合、すべてのエントリをメモリにロードするのではなく、ストリーミングでアーカイブを作成することを検討してください。

## よくある質問

**Q: Aspose.Zip for .NET は任意のファイルタイプで使用できますか？**  
A: はい、Aspose.Zip は幅広いファイル形式をサポートしており、実質的にすべてのファイルタイプの圧縮・解凍が可能です。

**Q: Aspose.Zip for .NET の無料トライアルはありますか？**  
A: はい、無料トライアルは **[here](https://releases.aspose.com/)** から取得できます。

**Q: Aspose.Zip for .NET のドキュメントはどこで見つけられますか？**  
A: 完全な API リファレンスは **[here](https://reference.aspose.com/zip/net/)** にあります。

**Q: Aspose.Zip for .NET の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: Aspose.Zip for .NET のサポートはどこで受けられますか？**  
A: **[Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37)** でサポートを受けられます。

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**最終更新日:** 2025-12-25  
**テスト環境:** Aspose.Zip for .NET 24.12  
**作成者:** Aspose  

---