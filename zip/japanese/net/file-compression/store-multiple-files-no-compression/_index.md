---
date: 2025-12-10
description: Aspose.Zip for .NET を使用して圧縮せずにファイルを保存する方法を学びましょう。このガイドでは、圧縮されていない ZIP
  を作成し、ファイルを ZIP に保存し、アーカイブを効率的に管理する方法を示します。
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NETでファイルを非圧縮で保存する方法
url: /ja/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET でファイルを圧縮せずに保存する方法

最新の .NET 開発において、**ファイルの保存方法** を効率的に選択することは、パフォーマンスやストレージコストに大きな影響を与えます。ファイルをそのまま（圧縮せずに）保存したい場合、Aspose.Zip for .NET はシンプルで分かりやすい API を提供します。このチュートリアルでは、圧縮なしの ZIP アーカイブを作成し、ファイルを ZIP に保存し、アプリケーションに統合する手順を解説します。

## Quick Answers
- **“uncompressed zip” とは何ですか？** エントリが「store」メソッドで保存され、元のバイト列がそのまま保持される ZIP アーカイブです。  
- **圧縮しない理由は？** アーカイブ処理を高速化したり、下流処理のために元サイズを保持したり、データ変更を禁じる規制要件に対応するためです。  
- **どの Aspose.Zip クラスがこれを扱いますか？** `ArchiveEntrySettings` と `StoreCompressionSettings` の組み合わせです。  
- **ライセンスは必要ですか？** 無料トライアルでテストは可能ですが、本番環境では商用ライセンスが必要です。  
- **対応 .NET バージョンは？** .NET Framework、.NET Core、.NET 5/6/7 以降に対応しています。

## 圧縮せずに複数ファイルを保存するとは？
圧縮せずに複数ファイルを保存するとは、各ファイルを *store* 圧縮方式で ZIP コンテナに追加することです。ファイルは元のバイト列と完全に同一のままで保存されるため、迅速なアーカイブやデータの不変性が求められるシナリオに最適です。

## Aspose.Zip を使って圧縮なしアーカイブを作るメリット
- **速度:** CPU 集中型の圧縮アルゴリズムが実行されません。  
- **サイズ予測可能:** アーカイブサイズは元ファイルの合計サイズに最小限の ZIP オーバーヘッドを加えたものになります。  
- **互換性:** 生成された ZIP は標準的な解凍ユーティリティで問題なく扱えます。  
- **柔軟性:** 必要に応じて、同一アーカイブ内に圧縮エントリと非圧縮エントリを混在させることができます。

## 前提条件
- **Aspose.Zip for .NET** – プロジェクトに組み込んでください。インストール手順は公式 [documentation](https://reference.aspose.com/zip/net/) を参照。  
- **.NET 開発環境** – Visual Studio、VS Code、またはお好みの IDE。  
- **ドキュメントディレクトリ** – アーカイブしたいファイルが格納されたフォルダー（例: “Your Document Directory”）。

## 名前空間のインポート
コードを書く前に、必要な名前空間をインポートして Aspose クラスを使用できるようにします。

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 手順 1: ドキュメントディレクトリの設定
ソースファイルが存在するパスを定義します。プレースホルダーは実際のフォルダーに置き換えてください。

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: 圧縮なしで Zip アーカイブを作成
チュートリアルの核心です。`Archive` インスタンスを `StoreCompressionSettings` で構成します。これにより Aspose.Zip は各エントリを *store*（圧縮なし）で保存します。

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **プロのコツ:** 一部のファイルは圧縮し、他は圧縮せずに **save files to zip** したい場合は、ファイルごとに別々の `ArchiveEntrySettings` を作成し、同一 `Archive` に追加してください。

## よくある問題と解決策
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **File not found** | `dataDir` パスが間違っている、または拡張子が不足している。 | パスを確認し、ファイルが存在することを確認してください。`Path.Combine` を使うと安全です。 |
| **Access denied** | ソースファイルの読み取りまたは ZIP の書き込み権限が不足している。 | 適切な権限でアプリケーションを実行するか、書き込み可能なフォルダーを選択してください。 |
| **Unexpected file size in ZIP** | デフォルトの圧縮設定でアーカイブが作成された。 | `new StoreCompressionSettings()` が `ArchiveEntrySettings` に渡されているか確認してください。 |

## Frequently Asked Questions

**Q: 特定のファイルタイプだけ圧縮し、他は圧縮せずに保存できますか？**  
A: はい、ファイルごとに異なる `ArchiveEntrySettings` を作成すれば、同一アーカイブ内で圧縮エントリと非圧縮エントリを混在させられます。

**Q: Aspose.Zip for .NET は .NET Core や .NET 5/6 と互換性がありますか？**  
A: もちろんです。ライブラリは .NET Framework、.NET Core、.NET Standard、そして最新の .NET バージョンをサポートしています。

**Q: アーカイブ処理中の例外はどう扱うべきですか？**  
A: アーカイブコードを `try‑catch` ブロックで囲み、例外情報をログに記録してください。これにより、優雅な失敗とデバッグが容易になります。

**Q: Aspose.Zip はマルチスレッドでのアーカイブに対応していますか？**  
A: 対応しています。複数ファイルを並列処理して `Archive` に追加できますが、`Archive` オブジェクト自体はスレッドセーフではないため、エントリ追加時は同期を取ってください。

**Q: 既存プロジェクトに Aspose.Zip を大幅なコード変更なしで統合できますか？**  
A: 可能です。API はシンプルなドロップイン設計になっているので、公式 [documentation](https://reference.aspose.com/zip/net/) の移行ガイドをご参照ください。

---

**最終更新日:** 2025-12-10  
**テスト環境:** Aspose.Zip for .NET 24.12（執筆時点での最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}