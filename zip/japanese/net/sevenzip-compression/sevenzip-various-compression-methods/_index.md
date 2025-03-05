---
title: 7 つの ZIP ファイルの作成 - Aspose.Zip for .NET チュートリアル
linktitle: さまざまな圧縮方式を備えたSevenZip
second_title: ファイルの圧縮とアーカイブのための Aspose.Zip .NET API
description: Aspose.Zip for .NET を使用して、さまざまな圧縮方法を使用して Seven Zip ファイルを作成する方法を学びます。 LZMA2、BZip2、およびストア (圧縮なし) の簡単な手順。
type: docs
weight: 12
url: /ja/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## 導入

.NET 開発の分野では、ファイルの管理と圧縮は一般的なタスクです。 Aspose.Zip for .NET は、圧縮アーカイブを操作するための強力なソリューションを提供し、さまざまな圧縮方法を提供します。このチュートリアルでは、Aspose.Zip for .NET を使用して、さまざまな圧縮方法で Seven Zip ファイルを作成する方法を説明します。

## 前提条件

チュートリアルに入る前に、次のものが揃っていることを確認してください。

- C# プログラミングの基本的な理解。
- Visual Studio がマシンにインストールされていること。
-  .NET ライブラリ用の Aspose.Zip。ダウンロードできます[ここ](https://releases.aspose.com/zip/net/).

## 名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートします。開始するには、次のコード スニペットを使用します。

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## LZMA2 圧縮

```csharp
//例: SevenZip とさまざまな圧縮方法

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## BZip2圧縮

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## 保存、圧縮なし

```csharp
//保存、圧縮なし
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## 結論

このチュートリアルでは、さまざまな圧縮方法を使用して Seven Zip ファイルを作成する際の Aspose.Zip for .NET の多用途性を検討しました。高い圧縮率が必要な場合でも、まったく圧縮を行わない場合でも、Aspose.Zip は要件を満たす柔軟性を提供します。

## よくある質問

### Aspose.Zip for .NET はどのような種類のファイルでも使用できますか?
はい。Aspose.Zip for .NET は幅広いファイル タイプをサポートしており、さまざまな形式の圧縮と解凍が可能です。

### Aspose.Zip for .NET の無料トライアルは利用できますか?
はい、無料トライアルを利用できます[ここ](https://releases.aspose.com/).

### Aspose.Zip for .NET のドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/zip/net/).

### Aspose.Zip for .NET の一時ライセンスを取得するにはどうすればよいですか?
仮免許も取得できる[ここ](https://purchase.aspose.com/temporary-license/).

### Aspose.Zip for .NET のサポートはどこで入手できますか?
サポートを求めることができます。[Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37).
