---
date: 2026-02-28
description: Aspose.Zip for .NET を使用してフォルダーを ZIP に追加し、ファイルを ZIP に追加する方法を学びます。このステップバイステップガイドでは、ASP.NET
  プロジェクトで FileInfo を使用してファイルを圧縮する方法を示します。
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用してフォルダーを Zip に追加する方法 – FileInfo でファイルを圧縮
url: /ja/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用してフォルダーを Zip に追加する方法

## はじめに

プログラムで **zip アーカイブを作成** する必要がある場合、Aspose.Zip for .NET は、任意の .NET（ASP.NET を含む）アプリケーションで動作するクリーンで高性能な API を提供します。このチュートリアルでは `FileInfo` クラスを使用したファイル圧縮の手順を解説し、**zip にファイルを追加**する方法を示し、なぜこのアプローチが最新の .NET プロジェクトに最適なのかを説明します。また、**フォルダーを zip に追加**する方法も取り上げ、ディレクトリ全体をワンステップでまとめられるようにします。さっそく始めましょう！

## よくある質問

- **zip アーカイブを作成する最も簡単な方法は何ですか？** Aspose.Zip の `Archive` クラスと `FileInfo` オブジェクトを組み合わせて使用します。  
- **複数のファイルを一度に追加できますか？** はい。各ファイルに対して `FileInfo` を作成し、`CreateEntry` を呼び出すだけです。  
- **ASP.NET 用に特別なライセンスが必要ですか？** 本番環境では商用の Aspose.Zip ライセンスが必要です。評価目的であれば無料トライアルで動作します。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **API はスレッドセーフですか？** はい、各スレッドが独自の `Archive` インスタンスを使用している限り安全です。

## Zipアーカイブとは何か、なぜ作成するのか？

Zip アーカイブは、1 つまたは複数のファイルを単一の圧縮コンテナにまとめます。これによりストレージ容量が削減され、ネットワーク転送が高速化され、配布が簡素化されます。ログの配信、レポートのエクスポート、クライアント向け資産のパッケージ化など、**zip アーカイブをプログラムで作成**する方法を知っていることは、すべての .NET 開発者にとって貴重なスキルです。

## Aspose.Zipを使用してファイルをZipに追加する理由

- **外部依存関係がゼロ** – 純粋な .NET 実装です。  
- **圧縮レベルとエンコーディング（ASCII、UTF‑8 など）を完全に制御**できます。  
- **大容量ファイル（4 GB 超）やパスワード保護に対応**しています。  
- **.NET Framework、.NET Core、.NET 5 以降で一貫した API**を提供します。

## 前提条件

コードに入る前に、以下が揃っていることを確認してください。

1. **Aspose.Zip for .NET** がインストールされていること。最新パッケージは [Aspose.Zip ダウンロードページ](https://releases.aspose.com/zip/net/) から取得できます。  
2. 圧縮したいファイルが入っているフォルダーがマシン上にあること（例：`alice29.txt` と `fields.c`）。

## 名前空間のインポート

zip アーカイブを扱う任意の C# ファイルで、以下の `using` 文を追加します。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

これらの名前空間により、`Archive` クラスや保存オプション、標準 I/O ユーティリティにアクセスできます。

## ステップバイステップガイド

### ステップ1：ドキュメントディレクトリの設定

まず、ソースファイルが格納されているフォルダーを定義します。プレースホルダーをシステム上の絶対パスまたは相対パスに置き換えてください。

```csharp
string dataDir = "Your Document Directory";
```

> **プロのコツ:** `Path.Combine` を使用して、クロスプラットフォーム対応のパスを構築しましょう。

### ステップ2：書き込み用にZipファイルを開く

`FileStream` を作成し、出力先の zip ファイルを指します。ストリームは **Create** モードで開かれ、同名の既存ファイルがあれば上書きされます。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### ステップ3：各ソースファイルの`FileInfo`オブジェクトの準備

`FileInfo` は Aspose.Zip にディスク上の実際のファイルへの直接アクセスを提供します。圧縮したいファイルごとにインスタンスを作成します。

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **`FileInfo` を使用する理由:** ファイル全体をメモリに読み込むことを回避できるため、特に大容量ファイルで有用です。

### ステップ4：アーカイブの作成とエントリの追加

`Archive` オブジェクトをインスタンス化し、各 `FileInfo` に対して `CreateEntry` を呼び出します。最初の引数は zip 内でのファイル名、2 番目の引数はソースの `FileInfo` です。

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### ステップ5：目的のエンコードでZipアーカイブを保存する

最後に、先ほど開いた `FileStream` にアーカイブを保存します。ここではエントリ名に ASCII エンコーディングを使用していますが、ファイル名に非 ASCII 文字が含まれる場合は UTF‑8 に切り替えることも可能です。

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` ブロックが終了すると、ストリームは自動的に閉じられ、zip ファイルは使用可能な状態になります。

## Aspose.Zipを使用してフォルダをZipに追加する方法

個別のファイルではなく **フォルダーを zip に追加** する必要がある場合、手順はシンプルです。

1. `DirectoryInfo.GetFiles`（再帰が必要な場合はオプションで `GetDirectories`）でフォルダーを列挙します。  
2. 発見した各ファイルに対して `FileInfo` を作成します。  
3. フォルダー名を含む相対パス（例: `"MyFolder/Report.pdf"`）で `CreateEntry` を呼び出します。

API が `FileInfo` を使用するため、ファイル全体をメモリに読み込む必要がなく、大規模なディレクトリでも安全に扱えます。この手法は、**zip multiple files asp.net** のようにレポートセットをリアルタイムで生成し、単一のアーカイブとして配信するシナリオでも有効です。

## よくある問題と解決策

| 問題 | 原因 | 解決策 |
|-------|-------|-----|
| **空の zip ファイル** | `FileInfo` が存在しないパスを指している | `dataDir` とファイル名を確認し、エントリ作成前に `File.Exists` で存在をチェックしてください。 |
| **ファイル名のエンコーディングが正しくない** | 非 ASCII 名にデフォルトエンコーディングを使用している | `ArchiveSaveOptions` の `Encoding = Encoding.UTF8` を設定します。 |
| **大容量ファイルで OutOfMemoryException が発生** | ファイル全体をメモリに読み込んでいる | `FileInfo` がストリーミングするので、他の場所でファイルをバイト配列に読み込んでいないか確認してください。 |
| **アクセス許可が拒否されました** | アプリケーションが出力フォルダーへの書き込み権限を持っていない | 適切な権限でアプリを実行するか、書き込み可能なディレクトリを選択してください。 |

### よくある質問

#### Q1: Aspose.Zip はすべてのファイルタイプに対応していますか？

A1: Aspose.Zip は幅広いファイルタイプをサポートしており、圧縮の汎用性が確保されています。

#### Q2: Aspose.Zip を商用プロジェクトで使用できますか？

A2: もちろんです！ライセンスオプションは [購入ページ](https://purchase.aspose.com/buy) でご確認ください。

#### Q3: Aspose.Zip のサポートを受けるには？

A3: サポートや議論は [Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37) のコミュニティに参加してください。

#### Q4: 無料トライアルは利用できますか？

A4: はい、[こちら](https://releases.aspose.com/) から無料トライアルを取得できます。

#### Q5: Aspose.Zip の一時ライセンスを取得するには？

A5: 一時ライセンスの取得情報は [このリンク](https://purchase.aspose.com/temporary-license/) をご覧ください。

## 結論

これで、Aspose.Zip for .NET を使用して **フォルダーを zip に追加**する方法、**zip アーカイブを作成**する方法、**ファイルを zip に追加**する方法、そしてこの手法が ASP.NET やその他の .NET アプリケーションに最適である理由が分かりました。さまざまな圧縮レベル、エンコーディング、暗号化オプションを試して、アーカイブを正確なニーズに合わせて調整してください。圧縮を楽しんでください！

---

**最終更新日:** 2026-02-28  
**テスト環境:** Aspose.Zip for .NET 24.12 (latest)  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}