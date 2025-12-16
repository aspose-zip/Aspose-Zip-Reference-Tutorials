---
date: 2025-12-16
description: .NET 用 Aspose.Zip を使用して、圧縮なしで ZIP を作成し、複数の ZIP ファイルを抽出する方法を学びます。このガイドでは、ZIP
  の開き方、ZIP エントリの読み取り方法、C# での ZIP 抽出手順について説明します。
linktitle: Decompressing a Stored File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 圧縮せずにZIPを作成し、ファイルを解凍 – Aspose.Zip
url: /ja/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した保存ファイルの解凍

## Introduction

最新の .NET アプリケーションでは、**create zip without compression** はデータ削減のオーバーヘッドなしで高速にアーカイブする必要がある場合に便利な手法です。Aspose.Zip for .NET を使用すると、このようなアーカイブの作成と、後で **extract multiple zip files** を簡単に行えます。このチュートリアルでは、zip を開き、zip エントリのデータを読み取り、**C# extract zip** 操作をステップバイステップで実行する方法を紹介します。

## Quick Answers
- **What is “create zip without compression”?** とは、データを変更せずに「store」方式でファイルを ZIP アーカイブに追加することを意味します。
- **Which library handles this in .NET?** Aspose.Zip for .NET.
- **Do I need a license to run the sample?** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。
- **Can I extract several files at once?** はい – 本チュートリアルではループで **extract multiple zip files** を行う方法を示しています。
- **What .NET versions are supported?** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## What is “create zip without compression”?
**store** 圧縮方式で ZIP アーカイブを作成すると、各ファイルはそのまま追加されます。圧縮された ZIP と比べてアーカイブは大きくなりますが、処理ははるかに高速で、元のファイルバイトは変更されません – サイズよりも速度やデータ完全性が重要なシナリオに最適です。

## Why use Aspose.Zip for .NET?
- **Full control** 圧縮レベル（store と deflate）を完全に制御できます。  
- **Simple API** エントリの読み取り、zip ファイルのオープン、データの抽出が簡単です。  
- **Cross‑platform** .NET Framework、.NET Core、.NET 5+ をサポートします。

## Prerequisites

このチュートリアルを始める前に、以下の前提条件が揃っていることを確認してください。

- Aspose.Zip for .NET ライブラリ: Aspose.Zip for .NET ライブラリをダウンロードしてインストールします。ライブラリは[here](https://releases.aspose.com/zip/net/)で入手できます。

- Document Directory: このチュートリアルに必要なファイルを保存するディレクトリをシステム上に作成してください。

## Import Namespaces

まずは、プロジェクトで必要な名前空間をインポートしましょう。

```csharp
using Aspose.Zip;
using System.IO;
```

## How to Create Zip Without Compression

まず、**store** メソッド（圧縮なし）を使用した ZIP アーカイブが必要です。以下のサンプルコードはそのようなアーカイブを作成し、Aspose.Zip が提供するヘルパーメソッドです。実行すると、ドキュメントディレクトリに `StoreMultipleFilesWithoutCompression_out.zip` が生成されます。

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** ヘルパーメソッドは内部で各エントリに `CompressionMethod.Store` を設定し、データ圧縮なしでアーカイブが作成されることを保証します。

## How to Open Zip and Extract Multiple Files

保存された ZIP ができたので、**how to open zip** を確認し、ファイルを取り出してみましょう。

### Step 2.1: Opening the Zip File

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

`Archive` オブジェクトは開かれた ZIP を表し、`Entries` コレクションを通じて各エントリにアクセスできます。

### Step 2.2: Creating Extracted Files

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

ここでは **read zip entry** 0 を読み取り、そのバイトを新しいファイルにコピーし、`using` 文のおかげでストリームが自動的に閉じられます。

### Step 2.3: Repeating the Process for Another File

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

`archive.Entries` を反復処理することで、数行のコードだけで **extract multiple zip files**（または複数エントリ）を抽出できます。

## Common Issues and Solutions

| 問題 | 原因 | 対策 |
|------|------|------|
| `FileNotFoundException` が ZIP を開くときに発生 | `dataDir` パスが間違っている | `dataDir` が末尾にスラッシュで終わっているか確認するか、`Path.Combine` を使用してください。 |
| 抽出されたファイルが空 | バッファがフラッシュされていない | `using` ブロックは自動的にフラッシュします。ストリームを `bytesRead` が 0 になるまで読み取っていることを確認してください（上記参照）。 |
| ライセンス例外 | 有効なライセンスなしで実行している | デプロイ前にトライアルまたは永続ライセンスを適用してください。 |

## Frequently Asked Questions

### Q1: Aspose.Zip for .NET はすべての .NET フレームワークと互換性がありますか？

**A:** はい、Aspose.Zip for .NET はさまざまな .NET フレームワークと互換性があるように設計されており、開発者に柔軟性を提供します。

### Q2: Aspose.Zip for .NET を商用プロジェクトと非商用プロジェクトの両方で使用できますか？

**A:** はい、Aspose.Zip for .NET は商用・非商用プロジェクトの両方で使用できます。ライセンスの詳細は [purchase page](https://purchase.aspose.com/buy) を参照してください。

### Q3: Aspose.Zip for .NET のサポートはどこで受けられますか？

**A:** サポートは [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) にて、開発者や専門家のコミュニティが支援します。

### Q4: Aspose.Zip for .NET の無料トライアルはありますか？

**A:** はい、[here](https://releases.aspose.com/) から無料トライアルを取得して、機能を試すことができます。

### Q5: テスト目的で一時ライセンスを取得できますか？

**A:** はい、[this link](https://purchase.aspose.com/temporary-license/) からテスト用の一時ライセンスを取得できます。

### Q6: アーカイブ全体を抽出せずに zip エントリを読むにはどうすればよいですか？

**A:** `archive.Entries[index].Open()` を使用して特定のエントリのストリームを取得し、必要なバイトを読み取ります。上記コードの例をご参照ください。

### Q7: ループで **extract multiple zip files** を行う最適な方法は何ですか？

**A:** `foreach` ループで `archive.Entries` を反復し、各エントリのストリームを開いて宛先ファイルに書き込む方法です。Step 2.2 と 2.3 のパターンと同様です。

## Conclusion

**create zip without compression** とその後の抽出プロセスをマスターすることは、高性能 .NET アプリケーションにとって重要です。Aspose.Zip for .NET は、**how to open zip**、各 **zip entry** の読み取り、そして最小限のコードで **C# extract zip** 操作を実行できる、クリーンで直感的な API を提供します。このガイドに従うことで、保存されたアーカイブの生成、オープン、そして効率的な内容の抽出方法を学びました。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-16  
**Tested With:** Aspose.Zip for .NET 24.12  
**Author:** Aspose