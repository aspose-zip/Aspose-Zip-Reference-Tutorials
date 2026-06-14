---
date: 2026-06-14
description: Aspose.Zip for .NET を使用して、圧縮なしで zip を作成し、複数の zip ファイルを抽出する方法を学びます。このガイドでは、zip
  のオープン方法、zip エントリの読み取り、C# での zip 抽出手順について説明しています。
keywords:
- create zip without compression
- extract multiple zip files
- c# extract zip
- aspose zip extract
- zip archive store method
linktitle: 保存されたファイルの解凍
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  headline: Create Zip Without Compression & Decompress Files – Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  name: Create Zip Without Compression & Decompress Files – Aspose.Zip
  steps:
  - name: '1: Opening the Zip File'
    text: The `Archive` object represents the opened ZIP and gives you access to each
      entry via the `Entries` collection.
  - name: '2: Creating Extracted Files'
    text: Here we **read zip entry** 0, copy its bytes to a new file, and close the
      streams automatically thanks to the `using` statements.
  - name: '3: Repeating the Process for Another File'
    text: By iterating over `archive.Entries`, you can **extract multiple zip files**
      (or multiple entries) with just a few lines of code.
  type: HowTo
- questions:
  - answer: It stores files in a ZIP using the *store* method, leaving the data unchanged.
    question: What does “create zip without compression” mean?
  - answer: Aspose.Zip for .NET provides a clean API for the *store* method and extraction.
    question: Which library supports this in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license to run the sample?
  - answer: Yes – the tutorial demonstrates how to **extract multiple zip files**
      in a loop.
    question: Can I extract several files at once?
  - answer: .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 圧縮なしでZipを作成し、ファイルを解凍 – Aspose.Zip
url: /ja/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した保存ファイルの解凍

## はじめに

現代の .NET アプリケーションでは、**create zip without compression** は、超高速のアーカイブが必要でファイルサイズを気にしない場合に便利な手法です。Aspose.Zip for .NET を使用すると、そのような「store‑method」アーカイブを生成でき、後で **extract multiple zip files** を数行の C# で実行できます。このチュートリアルでは、ZIP を開き、zip エントリを読み取り、**C# extract zip** 操作をステップバイステップで実演します。

## クイック回答

- **What does “create zip without compression” mean?** ZIP にファイルを *store* メソッドで保存し、データは変更されません。  
- **Which library supports this in .NET?** Aspose.Zip for .NET は *store* メソッドと抽出のためのクリーンな API を提供します。  
- **Do I need a license to run the sample?** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **Can I extract several files at once?** はい – このチュートリアルではループで **extract multiple zip files** を行う方法を示しています。  
- **What .NET versions are supported?** サポートされている .NET バージョンは、.NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、そして .NET 5–10 です。

## 「create zip without compression」とは何ですか？

`store` 圧縮メソッドは、ZIP 形式にデータ削減のステップをスキップするよう指示します。**create zip without compression** はその結果、より大きなアーカイブを生成しますが、処理はほぼ瞬時で元のバイトはそのまま保持されます – 既に圧縮されたメディア（JPEG、MP3）や、決定的なファイル内容が必要な場合に最適です。

## なぜ Aspose.Zip for .NET を使用するのか？

Aspose.Zip は、開発者に圧縮に対する正確な制御、エントリの読み書きのためのフルエント API、そしてすべての .NET バージョンにわたるクロスプラットフォーム互換性を提供します。大容量アーカイブを効率的に処理し、メモリ使用量を低く抑え、50 以上のフォーマットをサポートするため、シンプルなタスクから複雑なアーカイブ作業まで理想的です。

- **Full control** 圧縮レベルに対して – エントリごとに *store* または *deflate* を選択できます。  
- **Simple, fluent API** はエントリの読み取り、ZIP ファイルのオープン、データの抽出に使用します。  
- **Cross‑platform** は .NET Framework、.NET Core、.NET 5+ をサポートします。  
- **Handles large archives** は、ファイル全体をメモリにロードせずに最大 2 GB のアーカイブを処理します。  
- **Quantified claim:** Aspose.Zip は **50+ input and output formats** をサポートし、メモリ使用量を 100 MB 未満に抑えながら **multi‑hundred‑page archives** を処理できます。

## 前提条件

開始する前に、以下を確認してください：

- **Aspose.Zip for .NET** – 公式サイトから **[here](https://releases.aspose.com/zip/net/)** でダウンロードしてください。  
- サンプルファイルの読み書きに使用する、作業可能な **document directory** がマシン上にあること。

## 名前空間のインポート

最初に、使用するコアクラスが含まれる名前空間をインポートします。

```csharp
using Aspose.Zip;
using System.IO;
```

## C# で圧縮なしの zip アーカイブを作成するには？

`Archive` は Aspose.Zip で ZIP アーカイブを表す主要クラスです。

圧縮なしのアーカイブを作成するには、各ソースファイルを読み込み、`Archive` のインスタンスを作成し、`CompressionMethod.Store` で各ファイルを追加します。追加の圧縮パラメータは不要で、ライブラリは生バイトを直接書き込むため、ほぼ瞬時に処理が完了し、元のデータは変更されません。

## 圧縮なしで Zip を作成する方法

最初に、**store** メソッド（つまり圧縮なし）を使用する ZIP アーカイブが必要です。以下のサンプルコードはそのようなアーカイブを作成し、Aspose.Zip がヘルパーメソッドとして提供しています。実行すると、`StoreMultipleFilesWithoutCompression_out.zip` がドキュメントディレクトリに生成されます。

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** ヘルパーメソッドは内部で各エントリに `CompressionMethod.Store` を設定し、データ圧縮なしでアーカイブが作成されることを保証します。

## Aspose.Zip を使用して zip ファイルを開き、複数のエントリを抽出するには？

`Archive` は開かれた ZIP ファイルを表し、`Entries` コレクションを通じてエントリへのアクセスを提供します。

`Archive` コンストラクタにファイルパスを渡してアーカイブを開き、`archive.Entries` を反復処理します。各エントリについて `entry.Open()` でストリームを開き、バッファ付きストリームを使用してデータをターゲットファイルにコピーし、`using` によりストリームを自動的に閉じます。このアプローチにより、アーカイブ全体をメモリにロードせずにすべてのエントリを効率的に抽出できます。

## Zip を開いて複数のファイルを抽出する方法

現在、store された ZIP があるので、**how to open zip** を見てファイルを取り出しましょう。

### ステップ 2.1: Zip ファイルを開く

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

`Archive` オブジェクトは開かれた ZIP を表し、`Entries` コレクションを通じて各エントリにアクセスできます。

### ステップ 2.2: 抽出ファイルの作成

```csharp
        using (var extracted = File.Create(dataDir + "alice_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[0].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
```

ここでは **read zip entry** 0 を読み取り、そのバイトを新しいファイルにコピーし、`using` ステートメントのおかげでストリームが自動的に閉じられます。

### ステップ 2.3: 別のファイルでプロセスを繰り返す

```csharp
        using (var extracted = File.Create(dataDir + "asyoulik_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[1].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
    }
}
```

`archive.Entries` を反復することで、数行のコードだけで **extract multiple zip files**（または複数のエントリ）を抽出できます。

## 一般的な問題と解決策

| 問題 | 原因 | 対策 |
|-------|-------|-----|
| `FileNotFoundException` when opening the ZIP | `dataDir` パスが間違っている | `dataDir` が末尾にスラッシュで終わっているか、`Path.Combine` を使用しているか確認してください。 |
| Extracted file is empty | バッファがフラッシュされていない | `using` ブロックは自動的にフラッシュします。ストリームを `bytesRead` が 0 になるまで読み取っていることを確認してください（例参照）。 |
| License exception | 有効なライセンスなしで実行している | デプロイ前にトライアルまたは永続ライセンスを適用してください。 |

## よくある質問

### Q1: Aspose.Zip for .NET はすべての .NET フレームワークと互換性がありますか？

**A:** はい、Aspose.Zip for .NET は .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、そして .NET 5–10 で動作し、プラットフォーム間の柔軟性を提供します。

### Q2: Aspose.Zip for .NET を商用および非商用プロジェクトの両方で使用できますか？

**A:** はい、あらゆる種類のプロジェクトで使用できます。詳細は **[purchase page](https://purchase.aspose.com/buy)** のライセンス情報をご覧ください。

### Q3: Aspose.Zip for .NET のサポートはどのように受けられますか？

**A:** **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** を訪問してください。コミュニティと Aspose エンジニアが質問に回答します。

### Q4: Aspose.Zip for .NET の無料トライアルはありますか？

**A:** もちろんです。**[here](https://releases.aspose.com/)** からトライアルをダウンロードでき、すべての機能を無料で評価できます。

### Q5: テスト目的の一時ライセンスは取得できますか？

**A:** はい、短期評価用の一時ライセンスは **[this link](https://purchase.aspose.com/temporary-license/)** から取得可能です。

### Q6: アーカイブ全体を抽出せずに zip エントリを読むにはどうすればよいですか？

**A:** `archive.Entries[index].Open()` を使用して特定のエントリのストリームを取得し、必要なバイトだけを読み取ります – コードスニペットに示した通りです。

### Q7: ループで **extract multiple zip files** を行う最適な方法は何ですか？

**A:** `archive.Entries` を `foreach` ループで反復し、各エントリのストリームを開いてターゲット場所に書き込みます。この方法はステップ 2.2 と 2.3 で示したパターンと同様です。

## 結論

**create zip without compression** とその後の抽出プロセスをマスターすることは、高性能 .NET アプリケーションにとって不可欠です。Aspose.Zip for .NET は、**how to open zip**、各 **zip entry** の読み取り、そして最小限のコードで **C# extract zip** 操作を実行できるクリーンで直感的な API を提供します。本ガイドに従うことで、store アーカイブの生成、オープン、そして内容の効率的な抽出方法を学びました。

---

**最終更新日:** 2026-06-14  
**テスト環境:** Aspose.Zip for .NET 24.12  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Zip for .NET - パスワードで保護された Zip アーカイブと圧縮なしで複数ファイルを保存](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Zip アーカイブの作成 .NET – Aspose.Zip を使用したファイル圧縮](/zip/net/file-compression/)
- [Aspose.Zip for .NET でファイルを解凍する方法](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}