---
date: 2026-02-28
description: Aspose.Zip for .NET を使用して、パスワード付きでファイルを圧縮し ZIP アーカイブを暗号化する方法を学びます。7z
  のパスワード保護や C# におけるファイルごとの ZIP パスワード設定もカバーしています。
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用して、パスワードでファイルを圧縮し、ZIP エントリを別々のパスワードで暗号化する方法
url: /ja/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# パスワードでファイルを圧縮し、異なるパスワードでZIPエントリを暗号化する方法（Aspose.Zip for .NET）

## はじめに

**パスワードでファイルを圧縮**し、各エントリに個別のパスワードを付与したい場合は、ここが最適です。このチュートリアルでは、Aspose.Zip ライブラリ for .NET を使用して、すべてのファイルがユニークなパスワードで保護された 7‑zip アーカイブを作成する手順を詳しく解説します。最後まで読むと、エントリ単位の暗号化が重要な理由、設定方法、そして自分のプロジェクトで結果を確認する方法が理解できるようになります。

## クイック回答
- **“encrypt zip” とは何ですか？** パスワードベースの保護（AES または ZipCrypto）を ZIP/7z アーカイブの内容に適用することを意味します。  
- **各エントリに異なるパスワードを設定できますか？** はい — Aspose.Zip を使えば、ファイルごとに別々のパスワードを割り当てることができます。  
- **対応している .NET バージョンは？** 最新の .NET Framework、.NET Core、.NET 5/6 すべてに対応しています。  
- **本番環境でライセンスは必要ですか？** 商用利用には商用ライセンスが必要です。無料トライアルも利用可能です。  
- **サンプルで使用している圧縮形式は？** サンプルは AES‑256 暗号化付きの 7z アーカイブを作成します。

## Aspose.Zip for .NET を使用したパスワード付きファイル圧縮方法
このセクションでは、主要な質問に直接答え、以降のステップバイステップガイドの土台を築きます。

## Aspose.Zip で “zip を暗号化する方法” とは？
ZIP（または 7z）ファイルを暗号化するとは、エントリを保護し、正しいパスワードがなければ開けないようにすることです。Aspose.Zip for .NET は従来の ZipCrypto と、より強力な AES 暗号化の両方をサポートし、エントリ単位で暗号化設定を指定できるため、細かいセキュリティ制御が可能です。

## エントリごとに異なるパスワードを使用する理由
- **セキュリティ分離:** 1 つのパスワードが漏洩しても、他のファイルは保護されたままです。  
- **規制遵守:** 業界によっては、データカテゴリごとに別々の認証情報が求められます。  
- **ユーザー別アクセス:** 1 つのアーカイブを複数のユーザーに配布し、各ユーザーが許可されたファイルだけを開くことができます。

## 前提条件

始める前に以下を用意してください。

- **Aspose.Zip for .NET** がインストール済み — ダウンロードとインストール手順は公式 [documentation](https://reference.aspose.com/zip/net/) を参照してください。  
- ソースファイルを保存するフォルダー（「Document Directory」）をローカルに用意。  
- C# と Visual Studio（またはお好みの .NET IDE）に基本的に慣れていること。

## 名前空間のインポート

必要なクラスが含まれる名前空間をインポートします。

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: ドキュメントディレクトリの設定

アーカイブ対象のファイルが格納されているパスを定義します。

```csharp
string dataDir = "Your Document Directory";
```

## ステップ 2: 異なるパスワードでエントリを作成

チュートリアルの核心です。新しい 7z ファイルを開き、3 つの `FileInfo` オブジェクトを作成し、それぞれに独自の AES パスワードでエントリとして追加します。

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### 仕組み

- `SevenZipArchive` は 7‑z アーカイブのコンテナです。  
- `CreateEntry` はエントリ名、ソースファイル、上書きフラグ、そして `SevenZipEntrySettings` オブジェクトを受け取ります。  
- `SevenZipEntrySettings` 内では、圧縮用の設定オブジェクト（`SevenZipStoreCompressionSettings`）と暗号化用の設定オブジェクト（`SevenZipAESEncryptionSettings`）の 2 つを提供します。  
- 各呼び出しで **異なるパスワード**（`"test1"`、`"test2"`、`"test3"`）を指定し、エントリ単位の保護を実現します。

## ステップ 3: 検証

アーカイブが保存されたら、簡単な確認メッセージを出力します。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

プログラムを実行し、7‑Zip などのツールで `archive.7z` を開いてみてください。エントリごとにパスワード入力が求められ、パスワードがそれぞれ異なることが確認できます。

## 一般的な問題と解決策

| Issue | Reason | Fix |
|-------|--------|-----|
| **Incorrect password error** | パスワード文字列に余分なスペースや不可視文字が含まれている。 | パスワード文字列を `Trim` してください（`new SevenZipAESEncryptionSettings(password.Trim())`）。 |
| **Archive not opening in older tools** | 一部の旧式 ZIP ツールは 7z で使用される AES‑256 暗号化に対応していません。 | 最新の抽出ツール（7‑Zip 19.00 以上）を使用してください。 |
| **File not added to archive** | ソースファイルのパスが間違っている、またはファイルが存在しない。 | `dataDir` とファイル名を確認するか、`Path.Combine(dataDir, "data1.bin")` を使用してください。 |

## よくある質問

### Q1: Aspose.Zip for .NET はすべての .NET バージョンに対応していますか？

A1: はい、Aspose.Zip for .NET はすべての .NET フレームワーク バージョンとシームレスに統合できるよう設計されています。

### Q2: 商用プロジェクトで Aspose.Zip for .NET を使用できますか？

A2: もちろんです！Aspose.Zip for .NET には商用ライセンスが用意されており、購入方法の詳細は [here](https://purchase.aspose.com/buy) にあります。

### Q3: 無料トライアルはありますか？

A3: はい、Aspose.Zip for .NET の機能を無料トライアルでお試しいただけます。開始は [here](https://releases.aspose.com/) から。

### Q4: Aspose.Zip for .NET のサポートはどこで受けられますか？

A4: ご質問やサポートが必要な場合は、[Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) をご利用ください。

### Q5: 永続的なライセンスなしで Aspose.Zip for .NET を使用できますか？

A5: はい、短期的なニーズに合わせた一時ライセンスを取得できます。詳細は [here](https://purchase.aspose.com/temporary-license/) をご覧ください。

## 結論

**パスワードでファイルを圧縮し、エントリ単位で異なるパスワードを使用して ZIP アーカイブを暗号化する方法** を Aspose.Zip for .NET で学びました。この手法により、各ファイルを個別に保護でき、より厳しいセキュリティ要件に対応しつつ、ユーザー別の配布も簡単になります。圧縮設定やファイル数を増やしたり、Web サービスに組み込んでリアルタイムに安全なアーカイブを生成したりと、ぜひ色々試してみてください。

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}