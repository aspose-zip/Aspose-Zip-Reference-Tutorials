---
date: 2026-02-12
description: Aspose.Zip for .NET を使用してフォルダーを zip する方法を学び、.NET で効率的に zip アーカイブを作成し、.NET
  アプリケーションのストレージ容量を削減しましょう。
linktitle: How to Zip a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET 用 Aspose.Zip を使用してフォルダーを ZIP 圧縮する方法
url: /ja/net/directory-and-folder-compression/compress-directory/
weight: 10
---

 produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用したフォルダーの圧縮方法

このチュートリアルでは、Aspose.Zip for .NET を使用して **フォルダーを圧縮する方法** を迅速かつ確実に学びます。デスクトップユーティリティ、クラウドベースのサービス、または自動バックアップスクリプトを構築している場合でも、フォルダーを ZIP アーカイブに圧縮することで、ストレージ要件を大幅に削減し、ネットワーク転送を高速化できます。すべての手順を順に解説し、各行の重要性を説明し、一般的な落とし穴をハイライトするので、自信を持ってこの手法を適用できます。

## クイック回答
- **Aspose.Zip は何をしますか？** 外部依存関係なしで ZIP アーカイブの作成と抽出を行うシンプルな .NET API を提供します。  
- **実装にどれくらい時間がかかりますか？** 基本的なフォルダー圧縮で通常 10 分未満です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5+、.NET Core 3.1+、および .NET 5/6+。  
- **本番環境でライセンスが必要ですか？** はい、商用利用には商用ライセンスが必要です。  
- **複数のフォルダーを同時に圧縮できますか？** 絶対に可能です—任意の `DirectoryInfo` コレクションに対して `CreateEntries` メソッドを使用して **複数のフォルダーを圧縮** できます。

## 「フォルダーを圧縮する方法」とは何ですか？

フォルダーを圧縮するとは、指定されたディレクトリ内のすべてのファイルとサブフォルダーを取り出し、単一の ZIP アーカイブにまとめることです。これにより全体のサイズが削減され、元の階層構造が保持され、データの転送や保存が容易になります。

## このタスクに Aspose.Zip を使用する理由

- **速度と効率:** 最適化されたアルゴリズムが大規模フォルダーを迅速に処理します。  
- **Pure .NET:** ネイティブバイナリやサードパーティツールは不要です。  
- **豊富な機能セット:** パスワード保護 (`add password zip`)、ストリーミング、カスタム圧縮レベルの設定 (`set compression level`) をサポートします。  
- **一貫した API:** .NET Framework、.NET Core、.NET 5/6 で同じように動作し、**create zip archive .net** シナリオに最適です。  

## 前提条件

- **Aspose.Zip for .NET** – ダウンロードは [here](https://releases.aspose.com/zip/net/)。  
- **Development Environment** – Visual Studio、Rider、または C# をサポートする任意の IDE。  
- **Document Directory** – コード内の `"Your Document Directory"` を圧縮したいフォルダーのパスに置き換えてください。  
- **Reference Documentation** – 公式ドキュメントは [here](https://reference.aspose.com/zip/net/) を参照してください。

## 名前空間のインポート

まず、必要な名前空間をインポートします。これにより、コア圧縮クラスにアクセスできます。

```csharp
using Aspose.Zip;
using System.IO;
```

## Aspose.Zip を使用したフォルダーの圧縮方法

以下は、**フォルダーを圧縮する方法** の内容を示すシンプルな例です。同じパターンは **zip multiple files .net** に拡張したり、カスタムアーカイブ構造を作成したりすることができます。

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

> **プロのヒント:** 特定の圧縮レベルで **create zip archive .net** が必要な場合は、`Save` を呼び出す前に `archive.CompressionLevel` を設定してください。

## 一般的な問題と解決策

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| 空の ZIP ファイル | `dataDir` が間違ったフォルダーを指している、または末尾のスラッシュが欠如している | パスを確認し、フォルダーにファイルが含まれていることを確認してください |
| `UnauthorizedAccessException` | アプリケーションにファイルシステムへの権限がない | Visual Studio を管理者として実行するか、読み書き権限を付与してください |
| 巨大ディレクトリでのメモリ使用量が大きい | すべてのエントリを一度にメモリにロードしている | `Archive.CreateEntryFromFile` をループで使用し、ファイルを個別にストリーミングしてください |

## よくある質問（追加）

**Q: ZIP アーカイブにパスワードを追加できますか？**  
A: はい。`Save` を呼び出す前に `archive.Password = "yourPassword";` を設定します。

**Q: 特定のファイルタイプだけを含めるには？**  
A: `CreateEntries` を呼び出す前に、`DirectoryInfo` コレクションを `GetFiles("*.txt")` などでフィルタリングします。

**Q: 既存の ZIP を再作成せずに更新する方法はありますか？**  
A: Aspose.Zip は `Archive.UpdateEntry` を使用したインクリメンタル更新をサポートしています。

## FAQ

### Q1: Aspose.Zip for .NET を商用プロジェクトと個人プロジェクトの両方で使用できますか？

A1: はい、Aspose.Zip for .NET は商用・個人利用の両方にライセンスされています。

### Q2: 無料トライアルは利用可能ですか？

A2: はい、無料トライアルを [here](https://releases.aspose.com/zip/net) でご確認いただけます。

### Q3: Aspose.Zip for .NET のサポートはどのように受けられますか？

A3: コミュニティサポートは [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) をご覧ください。または、専用サポートのために [temporary license](https://purchase.aspose.com/temporary-license/) の購入をご検討ください。

### Q4: 他の例やチュートリアルはありますか？

A4: はい、[documentation](https://reference.aspose.com/zip/net/) に包括的な例とチュートリアルが含まれています。

### Q5: Aspose.Zip for .NET を購入できますか？

A5: もちろん、[here](https://purchase.aspose.com/buy) から購入できます。

---

**最終更新日:** 2026-02-12  
**テスト環境:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
