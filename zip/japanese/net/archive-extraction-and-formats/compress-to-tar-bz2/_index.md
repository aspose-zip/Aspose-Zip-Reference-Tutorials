---
date: 2026-10-31
description: Aspose.Zip を使用して .NET で tar アーカイブを作成し、TarBz2 ファイルに圧縮する方法を学びます。ステップバイステップのガイドで
  tar の作成、Bzip2 圧縮、ベストプラクティスのヒントを紹介します。
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: TarBz2 への圧縮
og_description: Aspose.Zip for .NET を使用して tar アーカイブを作成し、TarBz2 ファイルに圧縮する方法を学びます。ステップバイステップのガイドで
  tar の作成、Bzip2 圧縮、ベストプラクティスのヒントをカバーします。
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: .NET で tar アーカイブを作成し、TarBz2 に圧縮する
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
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
title: .NET で tar アーカイブを作成し、TarBz2 に圧縮する方法
url: /ja/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NETでtarアーカイブを作成し、TarBz2に圧縮する方法

このチュートリアルでは、**tarアーカイブ**ファイルを作成し、**Aspose.Zip** ライブラリ for .NET を使用して **TarBz2** パッケージに圧縮する方法を学びます。バックアップユーティリティの作成、デプロイバンドルの準備、軽量な配布形式が必要な場合など、以下の手順でファイルをtarコンテナに追加し、Bzip2圧縮を適用して最終的な `.tar.bz2` ファイルを書き出す方法を説明します。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Zip for .NET  
- **実装にかかる時間は？** 約5〜10分  
- **ライセンスは必要ですか？** 本番環境では一時ライセンスが必要です。無料トライアルも利用可能です。  
- **複数ファイルを圧縮できますか？** はい – 任意の数のエントリをtarアーカイブに追加できます。  
- **.NET 6+ と互換性がありますか？** 完全に対応しています。Aspose.Zip は .NET Framework と .NET Core/5/6 をサポートしています。  

## TarBz2 アーカイブとは？

TarBz2 ファイルは、従来の **tar** コンテナ（ディレクトリ構造とファイルメタデータを保持）に **Bzip2** 圧縮を組み合わせたものです。その結果、`.tar.bz2` という高圧縮率のパッケージが生成されます。この形式は Unix 系システムで広く使われており、圧縮率と解凍速度のバランスが良いことが特徴です。

## Aspose.Zip で TarBz2 に圧縮するメリット

Aspose.Zip は **2 回の API 呼び出し** で TarBz2 アーカイブを生成し、ストリームを効率的に処理します。**50 以上のアーカイブ・圧縮形式**に対応し、**2 GB** までのファイルをメモリに全体をロードせずに処理できます。また、Windows、Linux、macOS の .NET ランタイム上で動作します。エントリ名、タイムスタンプ、圧縮レベルを細かく制御できるため、コンソールユーティリティでも Web サービスでも最適です。

## 前提条件

- **Aspose.Zip for .NET** – 公式サイトから最新パッケージをダウンロードしてください: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **ドキュメントディレクトリ** – アーカイブしたいファイルが入っているフォルダーです。サンプルでは変数 `dataDir` で参照します。

> **プロのヒント:** ソースファイルは専用フォルダーにまとめておくと、不要なファイルが誤って含まれるのを防げます。

## 名前空間のインポート

まず、必要な名前空間をインポートして Aspose.Zip の Tar と Bzip2 クラスにアクセスできるようにします。

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## 手順 1: ドキュメントディレクトリを設定

アーカイブ対象のフォルダーへのパスを定義します。

```csharp
string dataDir = "Your Document Directory";
```

> `"Your Document Directory"` を、ソースフォルダーへの絶対パスまたは相対パスに置き換えてください。

## 手順 2: ファイルを tar に追加し、TarBz2 アーカイブを作成

`TarArchive` クラスはメモリ上の tar コンテナを表し、`Bzip2Archive` が Bzip2 アルゴリズムでストリームを圧縮します。  
`CreateEntry` メソッドで新しいファイルエントリを tar アーカイブに追加します。

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

- `CreateEntry` **はファイルを tar に追加**します – 必要なファイルごとにこのメソッドを呼び出します。  
- `bz2.SetSource(archive)` は Bzip2 アーカイブに対し、全体の tar ストリームを圧縮対象として設定します。  
- `bz2.Save(...)` が最終的な **TarBz2** ファイルをディスクに書き出します。

**コツ:** 複数ファイルを一括で **tar に追加**したい場合は、`bz2.Save` を呼び出す前に各ファイルに対して `archive.CreateEntry` を繰り返し実行してください。

## tar にファイルを追加する方法は？

ソースディレクトリを読み込み、`TarArchive` インスタンスを作成し、`CreateEntry` で各ファイルを追加します。その後、tar ストリームを `Bzip2Archive` でラップし、`Save` を呼び出します。この 2 ステップのパターンにより、任意の数のファイルを追加しながら、テンポラリファイルや外部ツールを使用せずに `.tar.bz2` ファイルを一度のフローで生成できます。

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| **File not found** エラー | `dataDir` パスが間違っている、または拡張子が不足している | パスを完全に確認し、ファイルが存在することを確認してください。 |
| **Empty archive** | `bz2.Save` 前にエントリが追加されていない | 少なくとも1つの `CreateEntry` 呼び出しを行ってください。 |
| **Permission denied** | 出力フォルダーへの書き込み権限がない | 適切な権限でアプリを実行するか、書き込み可能なディレクトリを選択してください。 |

## FAQ（よくある質問）

**Q: Aspose.Zip はすべての .NET アプリケーションと互換性がありますか？**  
A: はい。.NET Framework、.NET Core、.NET 5/6 以降のランタイムで動作します。

**Q: 複数ファイルを同時に圧縮できますか？**  
A: もちろんです。アーカイブを保存する前に各ファイルに対して `CreateEntry` を呼び出してください。

**Q: 追加のドキュメントはどこで入手できますか？**  
A: 詳細なドキュメントは **Aspose.Zip .NET API リファレンス** にあります: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Aspose.Zip の一時ライセンスはどう取得しますか？**  
A: こちらから **一時ライセンスをリクエスト** できます: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: 無料トライアルはありますか？**  
A: はい、**Aspose リリースからトライアル版をダウンロード** できます: [download a trial version](https://releases.aspose.com/).

You can also [download a trial version](https://releases.aspose.com/).

## 結論

これで **tar アーカイブの作成方法**、tar ストリームの Bzip2 圧縮、そして Aspose.Zip for .NET を使用した **TarBz2** アーカイブの生成手順が理解できました。この手法は高速でメモリ効率が高く、最新の .NET プラットフォームすべてで動作します。より大規模なファイルセットやカスタムエントリ名での実験、あるいはバックアップやデプロイパイプラインへの組み込みなど、自由に活用してください。

問題が発生した場合は、**Aspose.Zip サポートフォーラム** でコミュニティに相談できます: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37)。

---

**最終更新日:** 2026-10-31  
**テスト環境:** Aspose.Zip for .NET (最新リリース)  
**作者:** Aspose  

## 関連チュートリアル

- [Aspose.Zip for .NET で tar アーカイブを作成し、ファイルを tar に追加する方法](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Aspose.Zip でファイルを tar に追加し、tarxz アーカイブを作成する方法](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Aspose.Zip for .NET でファイルを tar に追加し、TarZ に圧縮する方法](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}