---
date: 2026-08-07
description: .NET で Aspose.Zip を使用してファイルを tar に追加し、TarBz2 アーカイブを生成する方法を学びます。ステップバイステップのガイドで
  tar の作成、Bzip2 圧縮、ベストプラクティスのヒントを紹介します。
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: TarBz2 への圧縮
og_description: .NET で Aspose.Zip を使用してファイルを tar に追加し、TarBz2 アーカイブを生成します。このガイドでは tar
  の作成、Bzip2 圧縮、トラブルシューティングのヒントを取り上げています。
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Aspose.Zip を使用してファイルを tar に追加し、TarBz2 アーカイブを作成する
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Aspose.Zip を使用してファイルを tar に追加し、TarBz2 アーカイブを作成する
url: /ja/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip を使用してファイルを tar に追加し、TarBz2 アーカイブを作成する

このチュートリアルでは、.NET 用 **Aspose.Zip** ライブラリを使用して **tar** アーカイブにファイルを追加し、コンパクトな **TarBz2** ファイルに変換する方法を紹介します。バックアップユーティリティの作成、デプロイパッケージの公開、配布用の軽量バンドルが必要な場合など、以下の手順で tar コンテナにファイルを追加し、Bzip2 圧縮を適用して、すぐに共有できるアーカイブを作成する方法を説明します。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Zip for .NET  
- **実装にどれくらい時間がかかりますか？** 約5〜10分  
- **ライセンスは必要ですか？** 本番環境では一時ライセンスが必要です。無料トライアルが利用可能です  
- **複数のファイルを圧縮できますか？** はい – tar アーカイブに好きなだけエントリを追加できます  
- **.NET 6+ と互換性がありますか？** はい、Aspose.Zip は .NET Framework と .NET Core/5/6 をサポートしています  

## TarBz2 アーカイブとは？

TarBz2 ファイルは、従来の **tar** コンテナ（ディレクトリ構造とファイルメタデータを保持）と **Bzip2** 圧縮を組み合わせたもので、非常に圧縮率の高い `.tar.bz2` パッケージになります。この形式は、圧縮率と解凍速度のバランスが良いため、Unix 系システムで広く利用されています。

## Aspose.Zip でファイルを TarBz2 に圧縮する理由

Aspose.Zip は、ストリームを効率的に処理しながら **2 つの API 呼び出し** で TarBz2 アーカイブを生成できます。**50 以上のアーカイブおよび圧縮形式** をサポートし、**2 GB** までのファイルをアーカイブ全体をメモリに読み込むことなく処理でき、Windows、Linux、macOS の .NET ランタイム上で動作します。また、エントリ名、タイムスタンプ、圧縮レベルを細かく制御できるため、コンソールユーティリティやウェブサービスの両方に最適です。

## 前提条件

- **Aspose.Zip for .NET** – 公式サイトから最新パッケージをダウンロードしてください: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – アーカイブしたいファイルを含むフォルダーです。例では変数 `dataDir` で参照しています。

> **プロのヒント:** ソースファイルは専用フォルダーに保存し、不要なファイルが誤って含まれないようにしてください。

## 名前空間のインポート

まず、必要な名前空間をインポートして、Aspose.Zip の Tar と Bzip2 クラスにアクセスできるようにします。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 手順 1: ドキュメントディレクトリの設定

アーカイブしたいファイルが格納されているフォルダーへのパスを定義します。

```csharp
string dataDir = "Your Document Directory";
```

> `"Your Document Directory"` を、ソースフォルダーへの絶対パスまたは相対パスに置き換えてください。

## 手順 2: ファイルを tar に追加し、TarBz2 アーカイブを作成する

`TarArchive` は、複数のファイルエントリを保持できるインメモリの tar コンテナを表します。  
`Bzip2Archive` は Bzip2 アルゴリズムを使用してストリームを圧縮します。  
`CreateEntry` メソッドは、ファイルを新しいエントリとして tar アーカイブに追加します。

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

- `CreateEntry` **tar にファイルを追加する** – アーカイブに必要なすべてのファイルに対してこのメソッドを呼び出すことができます。  
- `bz2.SetSource(archive)` は Bzip2 アーカイブに対し、tar ストリーム全体を圧縮するよう指示します。  
- `bz2.Save(...)` は最終的な **TarBz2** ファイルをディスクに書き込みます。

**ヒント:** **tar にファイルを一括追加** するには、`bz2.Save` を呼び出す前に各ファイルに対して `archive.CreateEntry` を繰り返し実行するだけです。

## tar にファイルを追加する方法は？

ソースディレクトリを読み込み、`TarArchive` インスタンスを作成し、`CreateEntry` で各ファイルを追加します。その後、tar ストリームを `Bzip2Archive` でラップし、`Save` を呼び出します。この 2 ステップのパターンにより、任意の数のファイルを追加して `.tar.bz2` ファイルを単一のフローで生成でき、テンポラリファイルや外部ツールが不要になります。

## よくある問題と解決策

| Issue | Reason | Fix |
|-------|--------|-----|
| **ファイルが見つかりません** エラー | `dataDir` パスが間違っているか、ファイル拡張子が欠落しています | フルパスを確認し、ファイルが存在することを確認してください。 |
| **空のアーカイブ** | `bz2.Save` の前にエントリが追加されていません | 少なくとも 1 つの `CreateEntry` 呼び出しを追加してください。 |
| **アクセスが拒否されました** | アプリケーションが出力フォルダーへの書き込み権限を持っていません | 適切な権限でアプリを実行するか、書き込み可能なディレクトリを選択してください。 |

## よくある質問

**Q: Aspose.Zip はすべての .NET アプリケーションと互換性がありますか？**  
A: はい。 .NET Framework、.NET Core、.NET 5/6 以降のランタイムで動作します。

**Q: 複数のファイルを同時に圧縮できますか？**  
A: もちろんです。アーカイブを保存する前に各ファイルに対して `CreateEntry` を呼び出してください。

**Q: 追加のドキュメントはどこで見つけられますか？**  
A: 詳細なドキュメントは **Aspose.Zip .NET API リファレンス** にあります: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Aspose.Zip の一時ライセンスはどのように取得できますか？**  
A: ここで **一時ライセンスをリクエスト** できます: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: 無料トライアルは利用可能ですか？**  
A: はい、**Aspose のリリースからトライアル版をダウンロード** できます: [download a trial version](https://releases.aspose.com/).

## 結論

これで **tar にファイルを追加する方法** が分かり、Bzip2 で tar ストリームを圧縮し、Aspose.Zip for .NET を使用して **TarBz2** アーカイブを生成できるようになりました。この手法は高速でメモリ効率が高く、最新の .NET プラットフォームすべてで動作します。より大きなファイルセットやカスタムエントリ名で試したり、コードを独自のバックアップやデプロイパイプラインに統合したりしてみてください。

問題が発生した場合は、Aspose.Zip コミュニティがサポートしますので、**Aspose.Zip サポートフォーラム** にアクセスしてください: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37)。

---

**最終更新日:** 2026-08-07  
**テスト環境:** Aspose.Zip for .NET (latest release)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Zip for .NET を使用して tar アーカイブを作成し、ファイルを tar に追加する](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip を使用してファイルを tar に追加し、tarxz アーカイブを作成する](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Aspose.Zip for .NET を使用してファイルを tar に追加し、TarZ に圧縮する](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}