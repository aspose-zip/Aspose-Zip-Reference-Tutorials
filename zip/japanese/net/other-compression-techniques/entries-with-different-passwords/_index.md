---
date: 2025-12-18
description: Aspose.Zip for .NET を使用して、異なるパスワードで zip ファイルを暗号化する方法を学びましょう。このガイドでは、パスワード付きでファイルを圧縮し、C#
  で 7z アーカイブを作成する方法を示します。
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET 用 Aspose.Zip で異なるパスワードを使用して ZIP ファイルを暗号化する方法
url: /ja/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET でエントリごとに異なるパスワードで ZIP ファイルを暗号化する方法

## はじめに

エントリごとに個別のパスワードを設定して **ZIP を暗号化する方法** を探しているなら、ここが最適です。このチュートリアルでは、Aspose.Zip ライブラリ for .NET を使用して、すべてのファイルがユニークなパスワードで保護された 7‑zip アーカイブを作成する手順を詳しく解説します。最後まで読むと、エントリ単位の暗号化が重要な理由、設定方法、そして自分のプロジェクトで結果を確認する方法が分かります。

## クイック回答
- **「encrypt zip」とは何ですか？** パスワードベースの保護（AES または ZipCrypto）を ZIP/7z アーカイブの内容に適用することです。  
- **各エントリに異なるパスワードを設定できますか？** はい。Aspose.Zip ではファイルごとに別々のパスワードを割り当てられます。  
- **対応している .NET バージョンは？** 最新の .NET Framework、.NET Core、.NET 5/6 すべてに対応しています。  
- **本番環境でライセンスは必要ですか？** 本番利用には商用ライセンスが必要です。無料トライアルも利用可能です。  
- **サンプルで使用している圧縮形式は？** AES‑256 暗号化を施した 7z アーカイブを作成します。

## Aspose.Zip での「how to encrypt zip」とは？

ZIP（または 7z）ファイルを暗号化するとは、エントリを保護し、正しいパスワードがなければ開けないようにすることです。Aspose.Zip for .NET は従来の ZipCrypto と、より強力な AES 暗号化の両方をサポートし、エントリ単位で暗号化設定を指定できるため、細かなセキュリティ制御が可能です。

## エントリごとに異なるパスワードを使用する理由

- **セキュリティの分離:** 1 つのパスワードが漏洩しても、他のファイルは保護されたままです。  
- **規制遵守:** 業界によってはデータカテゴリごとに別々の認証情報が求められます。  
- **ユーザー別アクセス:** 1 つのアーカイブを複数のユーザーに配布し、各ユーザーが許可されたファイルだけを解凍できるようにできます。

## 前提条件

作業を始める前に以下を用意してください。

- **Aspose.Zip for .NET** がインストール済み – 公式の[ドキュメント](https://reference.aspose.com/zip/net/)でダウンロードとインストール手順をご確認ください。  
- ソースファイルを格納するフォルダー（「Document Directory」）  
- C# と Visual Studio（またはお好みの .NET IDE）に関する基本的な知識

## 名前空間のインポート

必要なクラスが含まれる名前空間を取り込みます。

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

## 手順 1: ドキュメントディレクトリを設定

アーカイブ対象のファイルが格納されているパスを定義します。

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: 異なるパスワードでエントリを作成

チュートリアルの核心です。新しい 7z ファイルを開き、3 つの `FileInfo` オブジェクトを作成し、それぞれに固有の AES パスワードを付与してエントリとして追加します。

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

### 動作の概要

- `SevenZipArchive` は 7‑z アーカイブのコンテナです。  
- `CreateEntry` はエントリ名、ソースファイル、上書きフラグ、`SevenZipEntrySettings` オブジェクトを受け取ります。  
- `SevenZipEntrySettings` では、圧縮設定 (`SevenZipStoreCompressionSettings`) と暗号化設定 (`SevenZipAESEncryptionSettings`) の 2 つのオブジェクトを提供します。  
- 各呼び出しで **異なるパスワード**（`"test1"`、`"test2"`、`"test3"`）を指定し、エントリ単位の保護を実現しています。

## 手順 3: 検証

アーカイブ保存後、簡単な確認メッセージを出力します。

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

プログラムを実行し、7‑Zip などのツールで `archive.7z` を開いてみてください。エントリごとにパスワード入力が求められ、パスワードがそれぞれ異なることが確認できます。

## よくある問題と対策

| 問題 | 原因 | 対策 |
|------|------|------|
| **パスワードが正しくないエラー** | パスワード文字列に余分なスペースや不可視文字が含まれている | パスワード文字列を `Trim()` して渡す（`new SevenZipAESEncryptionSettings(password.Trim())`） |
| **古いツールでアーカイブが開けない** | 7z で使用される AES‑256 暗号化をサポートしていない | 最新の抽出ツール（7‑Zip 19.00 以降）を使用 |
| **ファイルがアーカイブに追加されない** | ソースファイルのパスが間違っている、またはファイルが存在しない | `dataDir` とファイル名を確認するか、`Path.Combine(dataDir, "data1.bin")` のように組み立て直す |

## FAQ（よくある質問）

### Q1: Aspose.Zip for .NET はすべての .NET バージョンに対応していますか？

A1: はい、Aspose.Zip for .NET はすべての .NET フレームワーク バージョンとシームレスに統合できるよう設計されています。

### Q2: 商用プロジェクトで Aspose.Zip for .NET を使用できますか？

A2: もちろんです！Aspose.Zip for .NET には商用ライセンスがあり、購入方法は[こちら](https://purchase.aspose.com/buy)でご確認いただけます。

### Q3: 無料トライアルはありますか？

A3: はい、無料トライアルで Aspose.Zip for .NET の機能を体験できます。[こちら](https://releases.aspose.com/)から開始してください。

### Q4: Aspose.Zip for .NET のサポートはどこで受けられますか？

A4: ご質問やサポートが必要な場合は、[Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37)をご利用ください。

### Q5: 永続的なライセンスがなくても Aspose.Zip for .NET を使用できますか？

A5: はい、短期利用向けに一時ライセンスを取得できます。詳細は[こちら](https://purchase.aspose.com/temporary-license/)をご覧ください。

## 結論

Aspose.Zip for .NET を使って、エントリごとに異なるパスワードで **ZIP を暗号化する方法** を習得しました。この手法により、ファイルごとに個別の保護を実現でき、厳格なセキュリティ要件やユーザー別配布をシンプルに行えます。圧縮設定やファイル数を増やしたり、Web サービスに組み込んでオンデマンドで安全なアーカイブを生成するなど、ぜひ色々試してみてください。

---

**最終更新日:** 2025-12-18  
**テスト環境:** Aspose.Zip for .NET 24.12（執筆時点での最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}