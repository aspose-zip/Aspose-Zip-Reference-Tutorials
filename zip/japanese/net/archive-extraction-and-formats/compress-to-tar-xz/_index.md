---
date: 2026-02-05
description: .NETでAspose.Zipを使用してファイルをtarに追加し、tarxzアーカイブを作成する方法を学びます。このガイドでは、ファイルを高効率でtarxzに圧縮する手順を示します。
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: ファイルを tar に追加し、Aspose.Zip を使用して .NET で tarxz アーカイブを作成
url: /ja/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tar にファイルを追加し、.NET で Aspise.Zip を使用して tarxz アーカイブを作成する方法

## はじめに

.NET を使用して **add files to tar** し、その後 tarxz アーカイブに圧縮したい場合、Aspose.Zip for .NET がプロセスをシンプルかつ信頼性のあるものにします。ログや設定ファイル、その他の資産を保存や転送のためにパッケージ化する場合でも、TarXz 形式で圧縮すれば高い圧縮率を得られ、慣れ親しんだ tar 構造を保持できます。本チュートリアルでは、コードスニペットを交えて正確な手順を順に解説し、.NET アプリケーションに tarxz 作成機能を自信を持って組み込めるようにします。

## クイック回答
- **主なクラスは何ですか？** `TarArchive` from `Aspose.Zip.Tar`
- **tarxz を圧縮する方法は？** エントリを追加した後に `SaveXzCompressed` を使用します
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6
- **ライセンスは必要ですか？** はい、製品版には有効な Aspose.Zip ライセンスが必要です
- **実装にかかる目安の時間は？** 約5〜10分

## TarXz アーカイブとは何ですか？

**TarXz アーカイブ** は、従来の Unix `tar` コンテナと XZ 圧縮を組み合わせたものです。tar 部分は複数のファイルを単一のストリームにまとめ、XZ は高いロスレス圧縮を提供します。この形式は、ディレクトリ構造を保持し、単純な tar や zip よりも小さなファイルサイズを実現できるため、ソースコード、バックアップ、巨大データセットの配布に人気があります。

## Aspose.Zip で tar にファイルを追加し tarxz に圧縮する理由は？

- **高い圧縮率** – XZ は gzip よりも 30〜50 % 小さく圧縮することが多いです。  
- **クロスプラットフォーム互換性** – TarXz ファイルは Linux、macOS、Windows で開くことができます。  
- **シンプルな API** – Aspose.Zip は低レベルの詳細を抽象化し、ビジネスロジックに集中できます。  
- **外部ツール不要** – すべてが .NET プロセス内で実行され、クラウドや CI パイプラインに最適です。  

## 前提条件

開始する前に、以下が揃っていることを確認してください：

- **Aspose.Zip for .NET** がインストール済み（公式の [Aspose.Zip documentation](https://reference.aspose.com/zip/net/) からダウンロード）。  
- アーカイブしたいファイルが入っているフォルダー。以下の例ではこのフォルダーは `dataDir` 変数で参照しています。  
- 有効な Aspose.Zip ライセンス（評価版はオプション、製品版は必須）。

## 名前空間のインポート

まず、TarXz 機能を提供する名前空間をインポートします。

```csharp
using System;
using Aspose.Zip.Tar;
```

## Aspose.Zip を使用して tar にファイルを追加する方法

### ステップ 1: `TarArchive` の初期化

`TarArchive` の新しいインスタンスを作成し、圧縮したいファイルを保持させます。

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tip:** `using` ステートメントはアーカイブが適切に破棄され、アンマネージドリソースが解放されることを保証します。

### ステップ 2: アーカイブにファイルを追加する

追加したい各ファイルをアーカイブに加えます。この例では 2 つのテキストファイルを追加していますが、必要に応じて任意の数のエントリを追加できます。

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Why this matters:** 圧縮前にエントリを追加することで、Aspose.Zip はまず tar コンテナを構築し、続いて単一ステップで XZ 圧縮を適用できます。

### ステップ 3: XZ 圧縮でアーカイブを保存する

最後に、XZ 圧縮を使用して tar アーカイブをディスクに書き込みます。生成されるファイルは `.tar.xz` 拡張子になります。

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Result:** これで、任意の TarXz 対応プラットフォームで転送、保存、または展開できる完全に圧縮された `archive.tar.xz` ファイルが作成されました。

## 一般的な問題と解決策

| Issue | Cause | Fix |
|-------|-------|-----|
| **“File not found” 例外** | `dataDir` パスが正しくない | ディレクトリパスがバックスラッシュ (`\`) で終わっているか確認するか、`Path.Combine` を使用してください。 |
| **メモリ使用量が大きい** | 非常に大きなファイルをメモリ内で圧縮している | `TarArchive` をストリーミングモードで使用する（`Stream` を受け取る `SaveXzCompressed` のオーバーロード）。 |
| **ライセンスが適用されていない** | ライセンスファイルが見つからない | アプリケーション開始時にライセンスをロードします：`new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## よくある質問

**Q: Aspose.Zip はすべての .NET 環境と互換性がありますか？**  
A: はい、Aspose.Zip は .NET Framework 4.5+、.NET Core 3.1+、および .NET 5/6+ で動作します。詳細は [documentation](https://reference.aspose.com/zip/net/) を参照してください。

**Q: Aspose.Zip の一時ライセンスはどのように取得できますか？**  
A: [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) から一時ライセンスをリクエストできます。

**Q: 他のアーカイブ形式の追加サンプルはありますか？**  
A: もちろんです。全サンプルは [Aspose.Zip API reference](https://reference.aspose.com/zip/net/) で確認できます。

**Q: サポートや問題の議論はどこでできますか？**  
A: コミュニティサポートや公式回答は [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) で参加してください。

**Q: 購入前に Aspose.Zip を無料で試せますか？**  
A: はい、無料トライアルは [Aspose.Zip download page](https://releases.aspose.com/zip/net) で利用可能です。

## 結論

上記の手順に従うことで、**how to add files to tar** と **create tarxz archives** を Aspose.Zip を使用して .NET で実行できるようになりました。この方法により、コンパクトでポータブルなパッケージが得られ、デスクトップユーティリティ、Web サービス、または自動化された CI/CD パイプラインなど、あらゆる .NET ワークフローにシームレスに統合できます。

---

**最終更新日:** 2026-02-05  
**テスト環境:** Aspose.Zip for .NET 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}