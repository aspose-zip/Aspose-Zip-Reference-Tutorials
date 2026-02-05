---
date: 2026-02-05
description: Aspose.Zip を使用して C# で複数のファイルを zip 圧縮し、.NET で zip アーカイブを作成する方法を学びましょう。このステップバイステップガイドでは、ASP.NET
  プロジェクトで FileInfo を使ってファイルを圧縮する方法を示します。
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用して C# で複数のファイルを zip する方法
url: /ja/net/file-compression/compress-files-fileinfo/
weight: 11
---

 unchanged.

Now produce final content with all translations.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した C# で複数ファイルを zip する方法

## はじめに

プログラムで **zip multiple files c#** が必要な場合、Aspose.Zip for .NET はクリーンで高性能な API を提供し、任意の .NET（ASP.NET を含む）アプリケーションで動作します。このチュートリアルでは `FileInfo` クラスを使ったファイル圧縮の手順を解説し、**add files to zip** の方法を示し、なぜこのアプローチが最新の .NET プロジェクトに最適なのかを説明します。さっそく始めましょう！

## クイック回答
- **zip アーカイブを作成する最も簡単な方法は何ですか？** Aspose.Zip の `Archive` クラスと `FileInfo` オブジェクトを使用します。  
- **複数のファイルを一度に追加できますか？** はい – 各ファイルに対して `FileInfo` を作成し、`CreateEntry` を呼び出すだけです。  
- **ASP.NET 用に特別なライセンスが必要ですか？** 本番環境では商用 Aspose.Zip ライセンスが必要です。評価目的は無料トライアルで利用できます。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **API はスレッドセーフですか？** はい、各スレッドが独自の `Archive` インスタンスを使用すれば安全です。  
- **メモリにロードせずに c# でファイルを zip する方法は？** `FileInfo` オブジェクトを使用すれば、データは直接ストリームされます。  

## C# で複数ファイルを zip する方法
zip アーカイブは、1 つまたは複数のファイルを単一の圧縮コンテナにまとめます。これによりストレージ容量が削減され、ネットワーク転送が高速化され、配布が簡素化されます。ログの配布、レポートのエクスポート、クライアント向け資産のパッケージ化など、**how to zip files c#** をプログラムで実行できることは、すべての .NET 開発者にとって貴重なスキルです。

## なぜ Aspose.Zip を使用してファイルを zip に追加するのか？
- **外部依存関係ゼロ** – 純粋な .NET 実装。  
- **圧縮レベルとエンコーディング（ASCII、UTF‑8 など）をフルコントロール**。  
- **大容量ファイル（> 4 GB）やパスワード保護に対応**。  
- **.NET Framework、.NET Core、.NET 5+ で一貫した API**。

## 前提条件

コードに入る前に、以下が揃っていることを確認してください。

1. **Aspose.Zip for .NET** がインストール済み。最新パッケージは [Aspose.Zip download page](https://releases.aspose.com/zip/net/) からダウンロードできます。  
2. 圧縮したいファイルが格納されたフォルダー（例: `alice29.txt` と `fields.c`）がローカルに存在すること。  

## 名前空間のインポート

zip アーカイブを扱う任意の C# ファイルで、次の `using` 文を追加します。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

これらの名前空間により、`Archive` クラスや保存オプション、標準 I/O ユーティリティにアクセスできます。

## ステップバイステップガイド

### ステップ 1: ドキュメントディレクトリの設定

まず、ソースファイルが格納されているフォルダーを定義します。プレースホルダーを、システム上の絶対パスまたは相対パスに置き換えてください。

```csharp
string dataDir = "Your Document Directory";
```

> **プロのコツ:** `Path.Combine` を使用して、クロスプラットフォームでパスを構築しましょう。

### ステップ 2: 書き込み用に Zip ファイルを開く

出力 zip ファイルを指す `FileStream` を作成します。ストリームは **Create** モードで開かれ、同名の既存ファイルがある場合は上書きされます。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### ステップ 3: 各ソースファイル用に `FileInfo` オブジェクトを準備する

`FileInfo` は Aspose.Zip にディスク上の実体ファイルへの直接アクセスを提供します。圧縮したいファイルごとにインスタンスを作成します。

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **`FileInfo` を使用する理由:** ファイル全体をメモリに読み込む必要がなく、大容量ファイルでも効率的に処理できます。

### ステップ 4: アーカイブを作成しエントリを追加する

`Archive` オブジェクトをインスタンス化し、各 `FileInfo` に対して `CreateEntry` を呼び出します。第1引数は zip 内でのファイル名、第2引数は元の `FileInfo` です。

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### ステップ 5: 任意のエンコーディングで Zip アーカイブを保存する

最後に、先ほど開いた `FileStream` にアーカイブを永続化します。ここではエントリ名に ASCII エンコーディングを使用していますが、ファイル名に非 ASCII 文字が含まれる場合は UTF‑8 に切り替えることができます。

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` ブロックが終了すると、ストリームは自動的に閉じられ、zip ファイルの使用準備が整います。

## よくある問題と解決策

| 問題 | 原因 | 解決策 |
|------|------|--------|
| **空の zip ファイル** | `FileInfo` が存在しないパスを指している | `dataDir` とファイル名を確認し、エントリ作成前に `File.Exists` で存在チェックを行う。 |
| **ファイル名のエンコーディングが正しくない** | デフォルトエンコーディングを使用し、非 ASCII 名がある | `ArchiveSaveOptions` の `Encoding = Encoding.UTF8` を設定する。 |
| **大きなファイルで OutOfMemoryException が発生** | ファイル全体をメモリに読み込んでいる | `FileInfo` がストリームするので、他の場所でバイト配列に読み込んでいないか確認する。 |
| **アクセス許可が拒否されました** | アプリケーションが出力フォルダーへの書き込み権限を持っていない | 適切な権限で実行するか、書き込み可能なディレクトリを選択する。 |

## よくある質問

**Q: zip アーカイブにパスワード保護を追加できますか？**  
A: はい。`Archive` を作成した後、`archive.Password = "yourPassword"` を設定してから `Save` を呼び出します。

**Q: 既存の zip ファイルを更新することは可能ですか？**  
A: Aspose.Zip は `Archive.Open` で既存アーカイブを開き、そこに新しいエントリを追加できます。

**Q: ASP.NET MVC コントローラでファイルを圧縮するにはどうすればよいですか？**  
A: 同じコードが使用できます。出力ストリームを `FileResult` としてクライアントに返すだけです。

**Q: Aspose.Zip は暗号化アルゴリズムをサポートしていますか？**  
A: 標準の ZipCrypto と AES‑256 暗号化をサポートしています。

**Q: フォルダーを再帰的に圧縮したい場合は？**  
A: `Directory.GetFiles`（およびサブフォルダー）をループし、各ファイルの `FileInfo` を作成してアーカイブに追加します。

## 既存の FAQ セクション（変更なし）

### FAQ's

#### Q1: Aspose.Zip はすべてのファイルタイプと互換性がありますか？

A1: Aspose.Zip は幅広いファイルタイプをサポートしており、圧縮の汎用性が高いです。

#### Q2: 商用プロジェクトで Aspose.Zip を使用できますか？

A2: もちろんです！ライセンスオプションは [purchase page](https://purchase.aspose.com/buy) でご確認ください。

#### Q3: Aspose.Zip のサポートはどこで受けられますか？

A3: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) のコミュニティに参加して質問や議論ができます。

#### Q4: 無料トライアルはありますか？

A4: はい、[free trial here](https://releases.aspose.com/) から取得できます。

#### Q5: Aspose.Zip の一時ライセンスはどのように取得できますか？

A5: 一時ライセンスの取得方法は [this link](https://purchase.aspose.com/temporary-license/) をご覧ください。

## 結論

これで **C# で複数ファイルを zip する方法** として Aspose.Zip for .NET の使い方、**add files to zip** の手順、そしてこの手法が ASP.NET やその他の .NET アプリケーションに最適な理由が分かりました。圧縮レベル、エンコーディング、暗号化オプションを色々試して、用途に合わせたアーカイブを作成してください。圧縮作業を楽しんでください！

---

**最終更新日:** 2026-02-05  
**テスト対象:** Aspose.Zip for .NET 24.12 (latest)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}