---
title: Aspose.Zip for .NET を使用した複数のファイルの解凍
linktitle: 複数のファイルを解凍する
second_title: ファイルの圧縮とアーカイブのための Aspose.Zip .NET API
description: Aspose.Zip for .NET を使用して複数のファイルを解凍する方法を学びます。効率的なファイル管理については、ステップバイステップのガイドに従ってください。
weight: 11
url: /ja/net/file-decompression/decompress-multiple-files/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した複数のファイルの解凍

## 導入

Aspose.Zip for .NET を使用して複数のファイルを解凍するための包括的なチュートリアルへようこそ!複数のエントリを含む圧縮ファイルを効率的に処理したい場合は、ここが最適な場所です。このガイドでは、Aspose.Zip for .NET を使用したプロセスを段階的に説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Zip for .NET: .NET 用の Aspose.Zip ライブラリがインストールされていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/zip/net/).

- ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを設定します。これをコードのベース ディレクトリとして使用します。

それでは、ステップバイステップのガイドを始めましょう。

## 名前空間のインポート

.NET プロジェクトで、Aspose.Zip に必要な名前空間をインポートすることから始めます。

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: 複数のファイルを圧縮する

複数のファイルを解凍するには、まず複数のエントリを含む圧縮ファイルが必要です。作成しましょう:

```csharp
string dataDir = "Your Document Directory";

//圧縮メソッドを実行する
CompressMultipleFiles.Run();
```

## ステップ 2: ファイルを解凍する

それでは、ファイルを段階的に解凍してみましょう。

### ステップ 2.1: 圧縮ファイルを開く

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    //...
}
```

### ステップ 2.2: エントリのリストと進行状況の追跡

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### ステップ 2.3: 最初のエントリの抽出

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        //解凍されたストリームから抽出ファイルにデータを読み書きします。
    }
}
```

### ステップ 2.4: 2 番目のエントリの抽出

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

そして、それができました！ Aspose.Zip for .NET を使用して複数のファイルを正常に解凍できました。

## 結論

このチュートリアルでは、Aspose.Zip for .NET を使用して複数のファイルを解凍するための重要な手順を説明しました。このガイドに従うことで、圧縮ファイルを簡単に効率的に管理できます。

## よくある質問

### Q1: Aspose.Zip for .NET は商用プロジェクトと個人プロジェクトの両方で使用できますか?

 A1: はい、Aspose.Zip for .NET は商用プロジェクトと個人プロジェクトの両方で使用できます。ライセンスの詳細については、以下を参照してください。[Aspose のライセンス情報](https://purchase.aspose.com/buy).

### Q2: Aspose.Zip for .NET の無料トライアルはありますか?

A2: はい、Aspose.Zip for .NET の無料トライアルを試すことができます。[ここ](https://releases.aspose.com/zip/net).

### Q3: Aspose.Zip for .NET の追加サポートはどこで見つけられますか?

 A3: にアクセスしてください。[Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37)コミュニティのサポートとディスカッションのために。

### Q4: Aspose.Zip for .NET の一時ライセンスはどのように購入できますか?

 A4: Aspose.Zip for .NET の一時ライセンスを取得します。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Zip for .NET を使用するための特定のシステム要件はありますか?

 A5: を参照してください。[ドキュメンテーション](https://reference.aspose.com/zip/net/)詳細なシステム要件については、
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
