---
date: 2026-02-23
description: Aspose.Zip for .NET を使用して複数のファイルを tar 圧縮し、tar.lz アーカイブを効率的に作成する方法を学びましょう。
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET 用 Aspose.Zip で複数ファイルを tar 圧縮する方法
url: /ja/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用して複数ファイルを tar 形式で圧縮する方法

最新の .NET 開発では、ファイルを効率的にパッケージ化することで、デプロイサイズやネットワーク転送時間を大幅に改善できます。**Compress multiple files tar** は、バックアップ、配布、またはクラウドへのアップロードのために軽量な LZ 圧縮 TAR アーカイブが必要なときに頻繁に求められる要件です。このチュートリアルでは、Aspose.Zip ライブラリを使用した明確なステップバイステップの **tar.lz compression example** を解説し、独自のアプリケーションで **tar.lz archive** をすぐに作成できるようにします。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Zip for .NET.  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約 5〜10 分です。  
- **ライセンスは必要ですか？** テスト用には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **複数のファイルを同時に圧縮できますか？** はい、保存する前にエントリを追加するだけです。

## 複数ファイルを tar 形式で圧縮する方法
このセクションでは、主要キーワードに直接答え、Aspose.Zip を使用して **compress multiple files tar** を実行する正確な手順を示します。このアプローチはファイル数に関係なく機能し、独自のフォルダー構造に簡単に適応できます。

## tar.lz 圧縮とは？
`tar.lz` は LZMA アルゴリズム（一般的に **LZ** と呼ばれる）で圧縮された TAR アーカイブです。TAR のファイルグルーピングのシンプルさと LZ の高い圧縮率を組み合わせており、バックアップファイルやパッケージ配布、帯域幅が重要なシーンに最適です。

## .NET で Aspose.Zip を使用する理由
Aspose.Zip はアーカイブ作成の低レベルな詳細を抽象化し、クリーンでオブジェクト指向の API を提供します。得られるメリットは次のとおりです。

* **外部依存ゼロ** – 純粋な .NET 実装。  
* **クロスプラットフォーム対応** – Windows、Linux、macOS で動作します。  
* **組み込み LZ 圧縮** – 追加のネイティブツールをインストールする必要はありません。  
* **強力なエラーハンドリング** – 例外が詳細で、デバッグが容易になります。

## 前提条件
開始する前に、以下が揃っていることを確認してください。

- **Aspose.Zip for .NET** ライブラリ – [here](https://releases.aspose.com/zip/net/) からダウンロードしてください。  
- アーカイブしたいファイルが入っているフォルダー。フォルダーへのパスは `dataDir` 変数に格納されます（Step 3 で設定します）。

## 名前空間のインポート
使用するクラスがどこにあるかコンパイラに認識させるため、必要な名前空間を追加します。

```csharp
using System;
using Aspose.Zip.Tar;
```

## tar.lz アーカイブの作成方法 – ステップバイステップガイド

### ステップ 1: 単一ファイルを圧縮する
最初の例は最も基本的なシナリオを示します。1 つのファイルを TAR アーカイブに追加し、**tar.lz** ファイルとして保存します。

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**解説**

- `new TarArchive()` は空の TAR コンテナを作成します。  
- `CreateEntry` は `dataDir` から `alice29.txt` ファイルを追加します。  
- `SaveLzipped` はアーカイブをディスクに書き込み、LZ 圧縮を適用して `archive.tar.lz` を生成します。

### ステップ 2: 1 つのアーカイブに複数ファイルを圧縮する
多くの場合、複数のファイルをまとめる必要があります。保存する前に各ファイルに対して `CreateEntry` を呼び出すだけです。これにより **add files to tar lz** と効果的に **compress multiple files tar** を実演します。

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**解説**

- コードはステップ 1 と同じパターンですが、2 番目のエントリ (`lcet10.txt`) を追加します。  
- 必要に応じて `CreateEntry` を何度でも繰り返せます。ライブラリが内部の TAR 構造を自動的に処理します。

### ステップ 3: ドキュメントディレクトリを指定する
プレースホルダーを、ソースファイルが存在する実際のパスに置き換えます。このパスは上記の例で使用されます。

```csharp
string dataDir = "Your Document Directory";
```

**解説**

- `dataDir` を完全修飾フォルダーパス（例: `@"C:\\MyFiles\\"`）に設定します。  
- ディレクトリを変数に保持することで、コードの再利用性と保守性が向上します。

## よくある落とし穴とトラブルシューティング
| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| サンプル実行時の `FileNotFoundException` | `dataDir` が存在しないフォルダーを指している、またはファイル名が間違っている | パスとファイル名を確認し、安全のために `Path.Combine` を使用してください。 |
| 出力ファイルが **0 KB** | `archive.SaveLzipped` がエントリ追加前に呼び出された | `SaveLzipped` の前に少なくとも1つの `CreateEntry` 呼び出しがあることを確認してください。 |
| 圧縮が遅いように見える | デフォルトのバッファサイズで大きなファイルを処理している | パフォーマンスが重要な場合は、ファイルをチャンクで処理するか、非同期 I/O の使用を検討してください。 |

## 結論
これで、Aspose.Zip for .NET を使用して **how to compress tar.lz** ファイルを作成する方法が分かりました。単一ドキュメントでも複数ファイルのコレクションでも、この **tar.lz compression example** は、簡単に転送または保存できる **create tar lz archive** ファイルを作成するクリーンで本番環境向けの方法を示しています。

## よくある質問

**Q:** Aspose.Zip for .NET で任意のサイズのファイルを圧縮できますか？  
**A:** はい、ライブラリは小さなファイルから非常に大きなファイルまで対応します。テンポラリ TAR 構造に十分なメモリとディスク容量があることを確認してください。

**Q:** コードは最新の Aspose.Zip リリースと互換性がありますか？  
**A:** サンプルは現在のバージョンを対象としています。バグ修正や新機能のために、NuGet パッケージは常に最新に保ってください。

**Q:** ライセンスに関する考慮点はありますか？  
**A:** 本番利用には商用ライセンスが必要です。ライセンスの詳細は [Aspose website](https://purchase.aspose.com/buy) をご覧ください。

**Q:** 商用プロジェクトで使用できますか？  
**A:** もちろんです。有効なライセンスを取得すれば、任意の商用アプリケーションに組み込むことができます。

**Q:** 問題が発生した場合、どこでサポートを受けられますか？  
**A:** コミュニティサポートと公式支援のために、[Aspose.Zip forum](https://forum.aspose.com/c/zip/37) をご利用ください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-02-23  
**テスト環境:** Aspose.Zip for .NET (latest release)  
**作者:** Aspose