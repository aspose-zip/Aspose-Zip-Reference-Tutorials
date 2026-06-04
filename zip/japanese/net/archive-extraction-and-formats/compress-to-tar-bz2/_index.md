---
date: 2026-04-24
description: .NET と Aspose.Zip を使用して tar を圧縮し、TarBz2 アーカイブを作成する方法を学びましょう。このステップバイステップガイドでは、ファイルを
  tar に追加し、tarbz2 ファイルを効率的に生成する方法を示します。
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: TarBz2 に圧縮
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET 用 Aspose.Zip で tar を圧縮し TarBz2 を作成する方法
url: /ja/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用して tar を圧縮し TarBz2 を作成する方法

## はじめに

このチュートリアルでは、**tar** アーカイブを圧縮し、**Aspose.Zip** ライブラリ for .NET を使用してコンパクトな **TarBz2** ファイルに変換する方法を学びます。バックアップユーティリティの作成、デプロイパッケージの公開、または単に配布用の軽量バンドルが必要な場合でも、以下の手順で tar にファイルを追加し、Bzip2 圧縮を適用し、共有可能なアーカイブを作成する方法をご案内します。

本格的に始める前に、このガイドの後半に記載されている前提条件を確認し、問題なく手順を進められるようにしてください。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Zip for .NET  
- **実装にどれくらい時間がかかりますか？** 約5〜10分  
- **ライセンスは必要ですか？** 本番環境では一時ライセンスが必要です。無料トライアルも利用可能です  
- **複数のファイルを圧縮できますか？** はい – tar アーカイブに好きなだけエントリを追加できます  
- **.NET 6+ と互換性がありますか？** 完全に対応しています。Aspose.Zip は .NET Framework と .NET Core/5/6 をサポートしています  

## TarBz2 アーカイブとは何ですか？

**TarBz2** ファイルは、従来の **tar** コンテナ（ディレクトリ構造とファイルメタデータを保持）と **Bzip2** 圧縮を組み合わせたもので、非常に圧縮率の高い `.tar.bz2` パッケージになります。この形式は、圧縮率と解凍速度のバランスが良いため、Unix 系システムで人気があります。

## Aspose.Zip でファイルを TarBz2 に圧縮する理由は？

- **速度とシンプルさ** – ワンラインの API 呼び出しで tar の作成と Bzip2 圧縮の両方を処理します。  
- **クロスプラットフォーム** – Windows、Linux、macOS の .NET ランタイムで動作します。  
- **細かな制御** – 含めるファイルを選択し、カスタムエントリ名を設定し、直接ディスクにストリームできます。  
- **堅牢な .NET サポート** – コンソールアプリから Web サービスまで、**tar archive .net** シナリオに最適です。  

## 前提条件

- **Aspose.Zip for .NET** – 公式サイトから最新パッケージをダウンロードしてください: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – アーカイブしたいファイルが入っているフォルダーです。例では変数 `dataDir` で参照しています。

> **プロのコツ:** ソースファイルは専用フォルダーに保管し、不要なファイルが誤って含まれないようにしましょう。

## 名前空間のインポート

まず、必要な名前空間をインポートして、Aspose.Zip の Tar と Bzip2 クラスにアクセスできるようにします。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## ステップ 1: Document Directory の設定

アーカイブしたいファイルが格納されているフォルダーへのパスを定義します。

```csharp
string dataDir = "Your Document Directory";
```

> `"Your Document Directory"` を、ソースフォルダーへの絶対パスまたは相対パスに置き換えてください。

## ステップ 2: ファイルを tar に追加し TarBz2 アーカイブを作成する

このプロセスの核心は `TarArchive` を作成し、エントリを追加した後、`Bzip2Archive` でラップすることです。以下のコードは、**tar の作成方法** とそれを **TarBz2** に圧縮する方法を、クリーンで disposable パターンのスタイルで示しています。

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **はファイルを tar に追加します** – アーカイブに必要な各ファイルに対してこのメソッドを呼び出すことができます。  
- `bz2.SetSource(archive)` は Bzip2 アーカイブに tar ストリーム全体を圧縮させます。  
- `bz2.Save(...)` は最終的な **TarBz2** ファイルをディスクに書き込みます。  

**ヒント:** 複数のファイルを一括で **tar に追加** するには、`bz2.Save` を呼び出す前に各ファイルに対して `archive.CreateEntry` を繰り返し実行するだけです。

## 一般的な問題と解決策

| 問題 | 原因 | 対策 |
|-------|--------|-----|
| **ファイルが見つかりません** エラー | `dataDir` のパスが間違っているか、ファイル拡張子が欠落しています | フルパスを確認し、ファイルが存在することを確認してください。 |
| **空のアーカイブ** | `bz2.Save` の前にエントリが追加されていません | 少なくとも1つの `CreateEntry` 呼び出しを追加してください。 |
| **アクセスが拒否されました** | アプリケーションに出力フォルダーへの書き込み権限がありません | 適切な権限でアプリを実行するか、書き込み可能なディレクトリを選択してください。 |

## よくある質問

**Q: Aspose.Zip はすべての .NET アプリケーションと互換性がありますか？**  
A: はい。 .NET Framework、.NET Core、.NET 5/6、そして新しいランタイムで動作します。

**Q: 同時に複数のファイルを圧縮できますか？**  
A: もちろんです。アーカイブを保存する前に各ファイルに対して `CreateEntry` を呼び出してください。

**Q: 追加のドキュメントはどこで見つけられますか？**  
A: 詳細なドキュメントは [here](https://reference.aspose.com/zip/net/) で入手できます。

**Q: Aspose.Zip の一時ライセンスはどう取得しますか？**  
A: [here](https://purchase.aspose.com/temporary-license/) からリクエストできます。

**Q: 無料トライアルは利用可能ですか？**  
A: はい、トライアル版は [here](https://releases.aspose.com/) からダウンロードできます。

## 結論

これで、**tar の圧縮方法** を学び、ファイルを追加し、結果を Bzip2 ストリームでラップして **TarBz2** アーカイブを Aspose.Zip for .NET で作成する方法が分かりました。この手法は高速で信頼性が高く、すべての最新 .NET プラットフォームで動作します。より大きなファイルセットやカスタムエントリ名で実験したり、コードを独自のバックアップやデプロイパイプラインに統合したりしてみてください。

問題が発生した場合は、Aspose.Zip コミュニティがサポートしますので、[Aspose.Zip サポートフォーラム](https://forum.aspose.com/c/zip/37) にアクセスしてください。

---

**最終更新日:** 2026-04-24  
**テスト対象:** Aspose.Zip for .NET (latest release)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}