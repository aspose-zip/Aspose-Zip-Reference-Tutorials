---
date: 2025-12-10
description: .NETでAspose.Zipを使用した並列ファイル圧縮を学びましょう。ステップバイステップのガイドで複数のファイルを効率的に圧縮できます。
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用した並列ファイル圧縮
url: /ja/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した並列ファイル圧縮

## はじめに

.NET 開発の世界では、**並列ファイル圧縮**はストレージ容量の最適化とデータ転送速度の向上に不可欠です。Aspose.Zip for .NET は強力なソリューションを提供し、その特長の一つは圧縮に並列処理を活用できることです。このチュートリアルでは、Aspose.Zip for .NET を使用して **複数のファイルを効率的に圧縮**する方法をステップバイステップで解説します。

## クイック回答
- **並列ファイル圧縮とは何ですか？** 複数のファイルを同時に圧縮し、複数の CPU コアを使用して全体の処理時間を短縮する手法です。  
- **.NET でこれをサポートしているライブラリはどれですか？** Aspose.Zip for .NET は組み込みの並列圧縮オプションを提供しています。  
- **ライセンスは必要ですか？** テスト用の一時ライセンスは利用可能ですが、本番環境では正式なライセンスが必要です。  
- **リアルタイムでファイルを zip に追加できますか？** はい、追加したい各ファイルに対して `Archive.CreateEntry` を使用します。  
- **.NET Core/5/6 と互換性がありますか？** 完全に対応しており、API はすべての最新 .NET ランタイムで動作します。

## 並列ファイル圧縮とは何か？

並列ファイル圧縮とは、圧縮作業を複数のスレッドやコアに分割し、複数のファイル（または大きなファイルの一部）を同時に圧縮できるようにすることです。この手法は、従来のシーケンシャル圧縮に比べて **zip archive c#** の作成に要する時間を大幅に短縮します。

## なぜ Aspose.Zip を使って並列圧縮するのか？

- **速度:** マルチコア CPU を最大限に活用します。  
- **スケーラビリティ:** 処理時間が比例して増加しない大規模なファイルバッチを処理できます。  
- **シンプルさ:** 高レベル API がスレッド処理の複雑さを抽象化します。  
- **柔軟性:** 任意の .NET バージョンで動作し、既存のコードベースにスムーズに統合できます。

## 前提条件

本格的に始める前に、以下が揃っていることを確認してください。

- C# と .NET 開発の基本的な知識。  
- Aspose.Zip for .NET ライブラリがインストールされていること。ダウンロードは **[here](https://releases.aspose.com/zip/net/)** から可能です。  
- 標準的なファイル圧縮の概念に関する理解。

## 名前空間のインポート

まず、必要な名前空間を C# ファイルにインポートし、コンパイラが使用するクラスの所在を認識できるようにします。

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## ステップ 1: ドキュメントディレクトリの設定

圧縮対象のファイルが格納されているフォルダーを定義します。このパスは `dataDir` 変数に格納されます。

```csharp
string dataDir = "Your Document Directory";
```

## ステップ 2: 圧縮プロセスの初期化

書き込み用に新しい ZIP ファイルを開きます。`using` ステートメントにより、操作後にファイルストリームが適切に破棄されます。

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## ステップ 3: ファイルを並列で読み取り圧縮

アーカイブに追加する各ソースファイルを開きます。この例では 2 つの古典テキストを使用していますが、任意の数のドキュメントに対して **add files to zip** できます。

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## ステップ 4: アーカイブエントリの作成

`Archive` インスタンスを作成し、各ファイルを個別のエントリとして追加します。ここが **create zip archive c#** のステップです。

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## ステップ 5: 並列処理基準の定義

`ParallelOptions` を設定して圧縮を並列で実行するよう構成します。`ParallelCompressInMemory` フラグは Aspose.Zip に常に並列処理を使用させます。

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## ステップ 6: 圧縮アーカイブの保存

最後に、エンコーディング、コメント、先ほど定義した並列設定など、必要なオプションを指定してアーカイブをディスクに書き込みます。

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

おめでとうございます！Aspose.Zip for .NET を使用して **parallel file compression** を実行し、複数のファイルを単一のアーカイブに効率的に **compressing multiple files** しました。

## よくある問題とヒント

- **大きなファイル:** メモリ使用量が高くなる場合は、ファイル全体をメモリに読み込むのではなく、チャンク単位で圧縮することを検討してください。  
- **スレッド安全性:** Aspose.Zip API は並列モードでスレッドセーフです。ライブラリ外で同じストリームを複数スレッドから変更しないでください。  
- **パフォーマンスチューニング:** 共有サーバーで CPU 使用率を制限したい場合は、`ParallelOptions.MaxDegreeOfParallelism` を調整してみてください。  

## FAQ

### Q1: Can I use Aspose.Zip for .NET with other .NET libraries?

A1: はい、Aspose.Zip for .NET は他の .NET ライブラリとシームレスに統合できるよう設計されています。

### Q2: Is a temporary license available for testing purposes?

A2: はい、テスト用の一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から取得できます。

### Q3: Where can I find additional support or ask questions?

A3: コミュニティサポートやディスカッションは **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** をご利用ください。

### Q4: Are there any examples or documentation available?

A4: 包括的なサンプルとドキュメントは **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** でご確認ください。

### Q5: How can I purchase Aspose.Zip for .NET?

A5: Aspose.Zip for .NET の購入は **[here](https://purchase.aspose.com/buy)** から可能です。

---

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}