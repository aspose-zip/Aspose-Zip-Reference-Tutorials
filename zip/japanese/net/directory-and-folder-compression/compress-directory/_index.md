---
date: 2026-05-30
description: Aspose.Zip for .NET を使用してフォルダーを zip する方法、.NET で zip アーカイブを効率的に作成し、.NET
  アプリケーションのストレージ容量を削減する方法を学びます。
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: フォルダーを Zip する方法
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用したフォルダーの Zip 方法
url: /ja/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用したフォルダーの圧縮方法

このチュートリアルでは、Aspose.Zip for .NET を使用して **フォルダーを圧縮する方法** を迅速かつ確実に学びます。デスクトップユーティリティ、クラウドベースのサービス、または自動バックアップスクリプトを構築する場合でも、フォルダーを ZIP アーカイブに圧縮することで、ストレージ要件を大幅に削減し、ネットワーク転送を高速化できます。すべての手順を順に解説し、各行の重要性を説明し、一般的な落とし穴をハイライトするので、自信を持ってこの手法を適用できます。

## 簡単な回答
- **Aspose.Zip は何をしますか？** 外部依存関係なしで ZIP アーカイブの作成と抽出を行うシンプルな .NET API を提供します。  
- **実装にどれくらい時間がかかりますか？** 基本的なフォルダー圧縮で通常 10 分未満です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 2.0‑4.8.1、.NET Core 2.0‑3.1、そして .NET 5‑10。  
- **本番環境でライセンスが必要ですか？** はい、本番使用には商用ライセンスが必要です。  
- **複数のフォルダーを同時に圧縮できますか？** もちろんです。任意の `DirectoryInfo` コレクションで `CreateEntries` メソッドを使用して、**複数のフォルダーを一度に圧縮** できます。  

`CreateEntries` はディレクトリ内のすべてのファイルをアーカイブに追加します。

## 「フォルダーを圧縮する方法」とは何ですか？

フォルダーを圧縮するとは、指定されたディレクトリ内のすべてのファイルとサブフォルダーを取り出し、単一の ZIP アーカイブにまとめることを意味します。これにより全体のサイズが削減され、元の階層構造が保持され、データの転送や保存が容易になります。生成された ZIP は特別なソフトウェアなしで任意のプラットフォームで開くことができ、フォルダー構造を保持するため、展開時に元のレイアウトが正確に復元されます。

## このタスクに Aspose.Zip を使用する理由

Aspose.Zip を使用すると、サポートされているすべてのランタイムで一貫した API を通じて、.NET コードから直接 **ZIP アーカイブ** ファイルを作成できます。`Archive` クラスをロードし、エントリを追加し、`CompressionLevel` を設定し、必要に応じてパスワードを割り当て、`Save` を呼び出します。このライブラリは、典型的なハードウェア上で数千ファイルを含むフォルダーを 1 秒未満で処理し、50 種類以上の圧縮形式と暗号化アルゴリズムをサポートしています。

## 前提条件

- **Aspose.Zip for .NET** – こちらからダウンロードしてください [here](https://releases.aspose.com/zip/net/) または [here](https://releases.aspose.com/zip/net)。  
- **開発環境** – Visual Studio、Rider、または C# をサポートする任意の IDE。  
- **ドキュメントディレクトリ** – コード内の `"Your Document Directory"` を、圧縮したいフォルダーへのパスに置き換えてください。  
- **リファレンスドキュメント** – 公式ドキュメントをご覧ください [here](https://reference.aspose.com/zip/net/)。  

## 名前空間のインポート

必要な名前空間をインポートします。これにより、コア圧縮クラスにアクセスできます。

```csharp
using Aspose.Zip;
using System.IO;
```

## Aspose.Zip を使用したフォルダーの圧縮方法

以下は、**フォルダーを圧縮する方法** の内容を示すシンプルな例です。同じパターンは **zip multiple files .net** に拡張したり、カスタムアーカイブ構造を作成したりすることができます。

### ステップ 1: ドキュメントディレクトリの初期化

圧縮したいディレクトリのパスを変数 `dataDir` に設定します。

```csharp
string dataDir = "Your Document Directory";
```

### ステップ 2: 出力 ZIP ファイルの作成

出力 ZIP ファイル用に 2 つの `FileStream` オブジェクトを開きます。これにより、同じソースから複数のアーカイブを生成できることが示されます（バージョンバックアップに便利です）。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### ステップ 3: ディレクトリの圧縮

`Archive` クラスは ZIP アーカイブを表し、エントリを追加してファイルを保存するメソッドを提供します。これを使用して対象フォルダーのすべてのエントリを追加します。例では **CanterburyCorpus** というサンプルフォルダーを使用していますが、任意のディレクトリを指定できます。

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **プロのコツ:** 特定の圧縮レベルで **create zip archive .net** が必要な場合は、`Save` を呼び出す前に `archive.CompressionLevel` を設定してください。

## 一般的な問題と解決策

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| 空の ZIP ファイル | `dataDir` が間違ったフォルダーを指している、または末尾のスラッシュが欠如している | パスを確認し、フォルダーにファイルが含まれていることを確認してください |
| `UnauthorizedAccessException` | アプリケーションにファイルシステムへの権限がない | Visual Studio を管理者として実行するか、読み書き権限を付与してください |
| 大規模ディレクトリでのメモリ使用量が大きい | すべてのエントリを一度にメモリに読み込んでいる | ループ内で `Archive.CreateEntryFromFile` を使用し、ファイルを個別にストリーミングしてください |

## よくある質問（追加）

**Q: ZIP アーカイブにパスワードを追加できますか？**  
A: はい。`Save` を呼び出す前に `archive.Password = "yourPassword";` を設定してください。

**Q: 特定のファイルタイプだけを含めるにはどうすればよいですか？**  
A: `CreateEntries` を呼び出す前に、`DirectoryInfo` コレクションを `GetFiles("*.txt")` などでフィルタリングします。

**Q: 既存の ZIP を再作成せずに更新する方法はありますか？**  
A: Aspose.Zip は `Archive.UpdateEntry` を使用したインクリメンタル更新をサポートしています。

## FAQ

### Q1: Aspose.Zip for .NET を商用および個人プロジェクトの両方で使用できますか？

A1: はい、Aspose.Zip for .NET は商用および個人利用の両方にライセンスされています。

### Q2: 無料トライアルは利用可能ですか？

A2: はい、無料トライアルは [here](https://releases.aspose.com/zip/net) でお試しできます。

### Q3: Aspose.Zip for .NET のサポートはどのように受けられますか？

A3: コミュニティサポートは [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) をご覧ください。または、専用サポートのために [temporary license](https://purchase.aspose.com/temporary-license/) の購入をご検討ください。

### Q4: 他の例やチュートリアルはありますか？

A4: はい、[documentation](https://reference.aspose.com/zip/net/) には包括的な例とチュートリアルが含まれています。

### Q5: Aspose.Zip for .NET を購入できますか？

A5: もちろん、[here](https://purchase.aspose.com/buy) から購入できます。

## 結論

これで、Aspose.Zip for .NET を使用した **フォルダーを圧縮する方法** の完全な本番対応パターンが手に入りました。ライブラリの `Archive` クラスを活用すれば、**ZIP アーカイブ** ファイルを作成し、カスタム `CompressionLevel` を設定し、パスワード保護を追加し、さらに **複数のフォルダーを一度に圧縮** することも可能です。これにより、フォルダーのバックアップタスクを自動化するのに最適です。API を試して暗号化やアーカイブ分割、クラウドストレージへの直接ストリーミングなどを追加すれば、あらゆる .NET ベースの圧縮ニーズに対応できる堅牢なソリューションが得られます。

---

**最終更新日:** 2026-05-30  
**テスト環境:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}