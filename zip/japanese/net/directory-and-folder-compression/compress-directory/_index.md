---
date: 2025-12-09
description: Aspose.Zip for .NET を使用してディレクトリを圧縮し、効率的に ZIP アーカイブを作成する方法を学びましょう。.NET
  アプリケーションでのストレージ容量を最適化します。
linktitle: How to Compress a Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET 用 Aspose.Zip を使用してディレクトリを圧縮する方法
url: /ja/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した手軽なディレクトリ圧縮

このチュートリアルでは、Aspose.Zip for .NET を使用して **ディレクトリの圧縮方法** をご紹介します。これは大規模データセットを管理し、ストレージ容量を節約する強力な方法です。デスクトップユーティリティを構築する場合でも、クラウドベースのサービスを構築する場合でも、フォルダーを効率的に圧縮することでパフォーマンスが大幅に向上し、コストを削減できます。各ステップを順に解説し、コードの背後にある考え方を説明し、一般的な落とし穴を指摘しますので、自信を持ってこの手法を適用できます。

## クイック回答

- **Aspose.Zip は何をしますか？** 外部依存関係なしで ZIP アーカイブの作成と抽出を行うシンプルな .NET API を提供します。  
- **実装にどれくらい時間がかかりますか？** 基本的なディレクトリ圧縮であれば、通常 10 分未満です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、そして .NET 5/6 以上をサポートしています。  
- **本番環境でライセンスが必要ですか？** はい、本番利用には商用ライセンスが必要です。  
- **複数のフォルダーを同時に圧縮できますか？** もちろんです。任意の `DirectoryInfo` コレクションに対して `CreateEntries` メソッドを使用してください。

## イントロダクション

Aspose.Zip for .NET は、.NET 開発者が圧縮ファイルやディレクトリをシームレスに扱える強力なライブラリです。大規模データセットを扱う場合でも、**generate zip file c#** スタイルのアーカイブを作成する必要がある場合でも、Aspose.Zip は圧縮・解凍タスク向けの堅牢な機能セットを提供します。

## 「how to compress directory」とは何ですか？

ディレクトリを圧縮するとは、指定されたフォルダー内のすべてのファイルとサブフォルダーを取得し、単一の ZIP アーカイブにまとめることを意味します。これにより全体のサイズが削減され、転送が簡素化され、元のフォルダー階層が保持されます。

## このタスクに Aspose.Zip を使用する理由

- **高速性と効率性:** 最適化されたアルゴリズムが大規模フォルダーを迅速に処理します。  
- **Pure .NET:** ネイティブバイナリやサードパーティツールは不要です。  
- **Rich Feature Set:** パスワード保護、ストリーミング、エントリのオンザフライ追加をサポートし、**zip multiple files .net** シナリオに最適です。  
- **Consistent API:** .NET Framework、.NET Core、.NET 5/6 すべてで同じように動作します。

## 前提条件

- **Aspose.Zip for .NET** – こちらからダウンロードしてください [here](https://releases.aspose.com/zip/net/)。  
- **Development Environment** – Visual Studio、Rider、または C# をサポートする任意の IDE。  
- **Document Directory** – コード内の `"Your Document Directory"` を、圧縮したいフォルダーのパスに置き換えてください。  
- **Reference Documentation** – 公式ドキュメントをご参照ください [here](https://reference.aspose.com/zip/net/)。

## 名前空間のインポート

必要な名前空間をインポートします。これにより、コア圧縮クラスにアクセスできます。

```csharp
using Aspose.Zip;
using System.IO;
```

## Aspose.Zip を使用したフォルダーの ZIP 圧縮方法

以下は、**how to zip folder** の内容を示すシンプルな例です。同じパターンは **zip multiple files .net** に拡張したり、カスタムアーカイブ構造を作成したりすることができます。

### ステップ 1: ドキュメントディレクトリの初期化

`dataDir` 変数に、圧縮したいディレクトリのパスを設定します。

```csharp
string dataDir = "Your Document Directory";
```

### ステップ 2: 出力 ZIP ファイルの作成

出力 ZIP ファイル用に 2 つの `FileStream` オブジェクトを開きます。これにより、同じソースから複数のアーカイブを生成できることが示されます—バージョンバックアップに便利です。

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### ステップ 3: ディレクトリの圧縮

`Archive` クラスを使用して、対象フォルダーのすべてのエントリを追加します。例では **CanterburyCorpus** というサンプルフォルダーを使用していますが、任意のディレクトリを指定できます。

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

> **Pro tip:** 特定の圧縮レベルで **create zip archive .net** が必要な場合は、`Save` を呼び出す前に `archive.CompressionLevel` を設定してください。

## 一般的な問題と解決策

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| 空の ZIP ファイル | `dataDir` が間違ったフォルダーを指している、または末尾のスラッシュが欠如している | パスを確認し、フォルダーにファイルが含まれていることを確認してください |
| `UnauthorizedAccessException` | アプリケーションにファイルシステムへの権限がありません | Visual Studio を管理者として実行するか、読み書き権限を付与してください |
| 巨大ディレクトリでのメモリ使用量が大きい | すべてのエントリを一度にメモリにロードしている | ループ内で `Archive.CreateEntryFromFile` を使用し、個別にファイルをストリーミングしてください |

## よくある質問（追加）

**Q: ZIP アーカイブにパスワードを追加できますか？**  
A: はい。`Save` を呼び出す前に `archive.Password = "yourPassword";` を設定してください。

**Q: 特定のファイルタイプだけを含めるにはどうすればよいですか？**  
A: `CreateEntries` を呼び出す前に、`DirectoryInfo` コレクションを `GetFiles("*.txt")` などでフィルタリングしてください。

**Q: 既存の ZIP を再作成せずに更新する方法はありますか？**  
A: Aspose.Zip は `Archive.UpdateEntry` によるインクリメンタル更新をサポートしています。

## FAQ

### Q1: Aspose.Zip for .NET を商用および個人プロジェクトの両方で使用できますか？

A1: はい、Aspose.Zip for .NET は商用・個人利用の両方にライセンスされています。

### Q2: 無料トライアルは利用可能ですか？

A2: はい、無料トライアルをご利用いただけます [here](https://releases.aspose.com/zip/net)。

### Q3: Aspose.Zip for .NET のサポートはどのように受けられますか？

A3: コミュニティサポートは [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) をご覧ください。または、専用サポートのために [temporary license](https://purchase.aspose.com/temporary-license/) の購入をご検討ください。

### Q4: 他の例やチュートリアルはありますか？

A4: はい、[documentation](https://reference.aspose.com/zip/net/) に包括的な例とチュートリアルが含まれています。

### Q5: Aspose.Zip for .NET を購入できますか？

A5: もちろん、[here](https://purchase.aspose.com/buy) から購入できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-09  
**テスト環境:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose