---
date: 2026-06-09
description: Aspose.Zip for .NET を使用して zip にパスワードを追加し、LZMA zip アーカイブを作成する方法を学びます。このチュートリアルでは
  Bzip2、LZMA（辞書サイズ）、PPMd、Enhanced Deflate、Store 圧縮、および大容量ファイルの ASP.NET ファイル圧縮について解説します。
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: 圧縮設定の最適化
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET を使用して zip にパスワードを追加し、LZMA アーカイブを作成する
url: /ja/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# パスワードを zip に追加し、Aspose.Zip for .NET で LZMA アーカイブを作成する

モダンな .NET アプリケーションでは、**add password to zip** しながら高圧縮率の LZMA zip アーカイブを作成することで、機密データを保護しつつ最高の圧縮率を得ることができます。ASP.NET のファイル圧縮サービス、マルチギガバイトのファイルを扱うデスクトップユーティリティ、またはクラウドベースのワークフローを構築している場合でも、このチュートリアルでは Aspose.Zip for .NET を使用してファイルを安全に圧縮する手順を詳しく解説します。

## クイック回答
- **What is the primary benefit of LZMA compression?** LZMA 圧縮の主な利点は何ですか？  
  ほとんどのファイルタイプに対して、合理的な速度で最高の圧縮率を提供します。  
- **Which method stores files without compression?** どのメソッドが圧縮せずにファイルを保存しますか？  
  Store compression（「store compression zip」 とも呼ばれます）。  
- **Can I use these settings in an ASP.NET application?** これらの設定を ASP.NET アプリケーションで使用できますか？  
  はい — プロジェクトに Aspose.Zip を参照し、同じ API を呼び出すだけです。  
- **Do I need a license for production use?** 本番環境で使用するにはライセンスが必要ですか？  
  本番環境では商用ライセンスが必要です。無料トライアルが利用可能です。  
- **What .NET versions are supported?** .NET のどのバージョンがサポートされていますか？  
  .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、そして .NET 5–10。

## Aspose.Zip の「add password to zip」とは何ですか？
**add password to zip** は ZIP アーカイブ内のすべてのエントリを暗号化し、パスワードを知っているユーザーだけがファイルを抽出できるようにします。Aspose.Zip は従来の ZipCrypto 暗号化と AES 暗号化（128、192、または 256 ビット）の両方をサポートしています。暗号化設定は `Archive` を構築する際に `ArchiveEntrySettings` の第2引数として渡されます。`SetPassword` メソッドは別途用意されていません。

## なぜ .NET のファイル圧縮に Aspose.Zip を使用するのか？
Aspose.Zip は多数のアルゴリズムをカバーしつつ、高性能かつ低メモリ使用を実現する単一の一貫した API を提供します。開発者はシナリオに応じて最適な圧縮方式を選択し、暗号化をワンステップで適用できるため、コードがシンプルになり保守コストが削減されます。

- **Unified API** – Bzip2、LZMA、PPMd、Enhanced Deflate、Store のための一貫したインターフェイス。  
- **Performance‑tuned** – 最適化されたネイティブ実装は、ファイル全体をメモリに読み込まずに **最大 10 GB のファイル** を処理できます。  
- **ASP.NET friendly** – Web プロジェクト、バックグラウンドサービス、Azure Functions でシームレスに動作します。  
- **Fine‑grained control** – 辞書サイズ、圧縮レベル、暗号化を単一のコンストラクタ呼び出しで調整できます。  
- **Supports 10+ compression algorithms** – エンタープライズデータパイプラインで最も一般的なユースケースをカバーする 10 以上の圧縮アルゴリズムをサポートします。

## 前提条件
- **Aspose.Zip for .NET Library** – [Aspose documentation](https://reference.aspose.com/zip/net/) からダウンロードしてインストールしてください。  
- **Sample Text File** – 圧縮対象となるサンプルファイル（例: `sample.txt`）を用意します。  
- **.NET development environment** – Visual Studio 2022 または互換性のある IDE を使用します。

## 名前空間のインポート
`Archive`、`ArchiveEntrySettings`、暗号化クラスは `Aspose.Zip` 名前空間にあります。ファイルの先頭でインポートしてください。

- `Archive` は ZIP アーカイブコンテナを表します。  
- `ArchiveEntrySettings` は各エントリの圧縮および暗号化オプションを保持します。  
- 暗号化クラス（例: `AesEncryptionSettings`）はデータの暗号化方法を定義します。

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは各圧縮設定を見ていき、適切な場所で **add password to zip** を行う方法を確認しましょう。

## Bzip2 圧縮設定の使用

### ステップ 1: 従来の暗号化を使用して Bzip2 圧縮を初期化する
`Bzip2CompressionSettings` は Bzip2 アルゴリズム（ブロックサイズ等）を設定します。  
`TraditionalEncryptionSettings` はエントリに従来の ZipCrypto 暗号化を適用します。

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*パスワード保護は `ArchiveEntrySettings` に直接渡される `TraditionalEncryptionSettings` によって適用されます。*

## Aspose.Zip for .NET を使用して zip にパスワードを追加する方法
ソースファイルを読み込み、エントリ設定で `Archive` を作成し、ファイルをアーカイブに追加します。暗号化は `ArchiveEntrySettings` インスタンス作成時に設定されているため自動的に適用されます。

**Direct answer (40‑70 words):**  
目的の圧縮設定と `TraditionalEncryptionSettings` または `AesEncryptionSettings` のいずれかを含む `ArchiveEntrySettings` オブジェクトを作成します。次にこのオブジェクトを `Archive` コンストラクタに渡し、`AddEntry` でファイルを追加します。アーカイブはパスワードが埋め込まれた状態で書き込まれるため、作成後に追加の手順は不要です。

`ArchiveEntrySettings` は、各エントリをどのように圧縮および暗号化するかを Aspose.Zip に指示する設定ホルダーです。

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Aspose.Zip を使用して LZMA zip アーカイブを作成する方法

### ステップ 1: AES256 暗号化を使用して LZMA 圧縮を初期化する
`LzmaCompressionSettings` は辞書サイズや fast bytes など、LZMA 固有のパラメータを制御します。  
`AesEncryptionSettings` はアーカイブエントリに対して AES‑256 暗号化を提供します。

**Direct answer (40‑70 words):**  
選択した `DictionarySize` で `LzmaCompressionSettings` をインスタンス化し、パスワードと `EncryptionMethod.AES256` を指定した `AesEncryptionSettings` オブジェクトを作成します。両者から `ArchiveEntrySettings` を構築し、これを `Archive` コンストラクタに渡してファイルを追加します。生成される zip は LZMA 圧縮かつ AES 保護が一度の操作で行われます。

`LzmaCompressionSettings` は辞書サイズや fast bytes など、LZMA 固有のパラメータを制御するクラスです。

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **Tip:** LZMA では、圧縮率とメモリ使用量の両方に影響を与える設定可能な **LZMA 辞書サイズ** が提供されています。非常に大きなファイル向けに微調整が必要な場合は、`new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` のように設定できます。

## PPMd 圧縮設定の使用

### ステップ 1: AES256 暗号化を使用して PPMd 圧縮を初期化する
`PpmdCompressionSettings` は PPMd アルゴリズムの順序とメモリ使用量を定義します。  
`AesEncryptionSettings` はアーカイブエントリに対して AES‑256 暗号化を提供します。

**Direct answer (40‑70 words):**  
`PpmdCompressionSettings` インスタンスを作成し、パスワードを含む `AesEncryptionSettings` オブジェクトと組み合わせて `ArchiveEntrySettings` に渡します。この設定オブジェクトを `Archive` 構築時に使用すると、生成される zip は PPMd 圧縮かつパスワード保護が適用され、追加の呼び出しは不要です。

`PpmdCompressionSettings` は PPMd アルゴリズムの順序とメモリ使用量を定義します。

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Enhanced Deflate 圧縮設定の使用

### ステップ 1: AES256 暗号化を使用して Enhanced Deflate 圧縮を初期化する
`EnhancedDeflateCompressionSettings` は速度とサイズのバランスを取る圧縮レベルを指定できます。  
`AesEncryptionSettings` はアーカイブエントリに対して AES‑256 暗号化を提供します。

**Direct answer (40‑70 words):**  
希望するレベル（0‑9）で `EnhancedDeflateCompressionSettings` をインスタンス化し、`AesEncryptionSettings` と組み合わせて `ArchiveEntrySettings` にラップします。これを `Archive` コンストラクタに渡してファイルを追加すれば、Enhanced Deflate 圧縮と AES‑256 パスワード保護が一度の処理で適用されたアーカイブが作成されます。

`EnhancedDeflateCompressionSettings` は速度とサイズのバランスを取る圧縮レベルを指定できます。

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Store 圧縮設定の使用（store compression zip）

### ステップ 1: 従来の暗号化を使用して Store 圧縮を初期化する
`StoreCompressionSettings` は Aspose.Zip に対し、圧縮を完全にスキップし、元のファイルをバイト単位でそのまま保持するよう指示します。  
`TraditionalEncryptionSettings` は従来の ZipCrypto 暗号化を適用します。

**Direct answer (40‑70 words):**  
圧縮を行わない `StoreCompressionSettings` インスタンスを作成し、パスワードを含む `TraditionalEncryptionSettings` と組み合わせて `ArchiveEntrySettings` にラップします。これを `Archive` コンストラクタに渡すと、元のファイルが圧縮されずに保持され、パスワード保護された zip が生成されます。

`StoreCompressionSettings` は Aspose.Zip に圧縮を完全にスキップさせ、ソースファイルをバイト単位でそのまま保持させます。

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro tip:** `dataDir` 変数を実際の作業ディレクトリに合わせて調整し、複数のファイルを単一のアーカイブに追加する必要がある場合は同じ `Archive` インスタンスを再利用してください。

## 一般的な問題と解決策
- **"File not found" errors** – `dataDir` がパス区切り文字（`\` または `/`）で終わっているか、`sample.txt` が存在するかを確認してください。  
- **Memory consumption with large files** – `ArchiveEntrySettings` を使用してストリーミングモードを有効にし、データを直接出力ストリームに書き込むようにします。  
- **Incompatible compression level** – 一部のアルゴリズム（例: LZMA）では `DictionarySize` などの追加プロパティが公開されています。より細かい制御が必要な場合は API ドキュメントを参照してください。  
- **Password not applied** – 暗号化設定オブジェクトがアーカイブ作成時に `ArchiveEntrySettings` の第2引数として渡されていることを確認し、アーカイブ作成後に設定しないでください。

## よくある質問

**Q: Aspose.Zip for .NET を他の圧縮ライブラリと併用できますか？**  
A: Aspose.Zip は組み込みのアルゴリズムで動作するよう設計されています。サードパーティのライブラリを統合することは可能ですが、Aspose API の外でカスタム処理が必要です。

**Q: Aspose.Zip で作成した zip にパスワード保護を追加するには？**  
A: `Archive` を構築する際に `ArchiveEntrySettings` の第2引数として `TraditionalEncryptionSettings` または `AesEncryptionSettings` を渡します。完全な例は [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/) を参照してください。

**Q: 試用版はありますか？**  
A: はい、[here](https://releases.aspose.com/) から試用版にアクセスできます。

**Q: コミュニティのサポートや質問はどこで得られますか？**  
A: サポートやコミュニティディスカッションは [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) をご利用ください。

**Q: 評価用の一時ライセンスは取得できますか？**  
A: はい、[here](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

**Q: これが ASP.NET のファイル圧縮にどのように役立ちますか？**  
A: ASP.NET コントローラやミドルウェアから同じ API を呼び出すことで、クライアントに送信する前にファイルをリアルタイムで圧縮でき、帯域幅を削減し、パフォーマンスの向上が期待できます。

**Q: 大容量ファイルを効率的に圧縮する最適な方法は？**  
A: ストリーミングモードと LZMA 圧縮、適切な `DictionarySize` を組み合わせます。これにより、巨大データセットに対してメモリ使用量と圧縮率のバランスが取れます。

---

**最終更新日:** 2026-06-09  
**テスト環境:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Zip for .NET - パスワードで Zip アーカイブを保護し、圧縮なしで複数ファイルを保存](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [.NET ディレクトリ用パスワード保護 zip の作成 – Aspose.Zip チュートリアル](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [複数ファイルの zip (c#) – Aspose.Zip for .NET で手軽に圧縮](/zip/net/file-compression/compress-multiple-files/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}