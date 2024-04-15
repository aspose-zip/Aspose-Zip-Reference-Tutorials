---
title: Aspose.Zip for .NET - 安全なファイル ストレージのチュートリアル
linktitle: パスワードを使用して複数のファイルを圧縮せずに保存
second_title: ファイルの圧縮とアーカイブのための Aspose.Zip .NET API
description: Aspose.Zip for .NET を使用して複数のファイルを圧縮せずに安全に保存する方法を説明します。パスワード保護のための簡単な手順。ファイル管理の能力を解放しましょう!
type: docs
weight: 13
url: /ja/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

.NET 開発の世界では、ファイルの管理と操作は一般的なタスクです。 Aspose.Zip for .NET は、開発者に zip アーカイブをシームレスに圧縮、解凍、操作する機能を提供する強力なライブラリです。このチュートリアルでは、複数のファイルを圧縮せずに保存し、パスワードで保護するという特定のシナリオについて詳しく説明します。このガイドを終えると、Aspose.Zip for .NET を使用してこの機能を実装するための知識が身につくでしょう。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Zip for .NET ライブラリ: Aspose.Zip for .NET ライブラリがインストールされていることを確認してください。ダウンロードできます[ここ](https://releases.aspose.com/zip/net/).

- ドキュメント ディレクトリ: ソース ファイルが配置されるディレクトリを準備します。提供された例では、変数`dataDir`はドキュメント ディレクトリを表します。

## 名前空間のインポート

まず、コードに必要な名前空間をインポートしましょう。

```csharp
//リソース ディレクトリへのパス。
string dataDir = "Your Document Directory"

// Aspose.Zip 名前空間をインポートする
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## ステップ 1: ZIP ファイルを開く

```csharp
//ExStart: 圧縮なしで複数のファイルをパスワード付きで保存
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

この手順では、次を使用して新しい zip ファイルを作成します。`FileStream`。ファイルの名前は「StoreMutlipleFilesWithoutCompressionWithPassword_out.zip」になります。

## ステップ 2: ソース ファイルを開く

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

ここでは、zip アーカイブに保存される最初のソース ファイル「alice29.txt」を開きます。

## ステップ 3: アーカイブを作成する

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

このステップでは、`Archive`クラスを使用して、圧縮と暗号化の設定を指定します。私たちが使用するのは、`StoreCompressionSettings`ファイルを圧縮せずに保存し、`AesEcryptionSettings`パスワード (「p@s$」) を使用して AES 暗号化を適用します。

## ステップ 4: アーカイブ エントリを作成して保存する

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

この最後のステップでは、アーカイブ内に「alice29.txt」のエントリを作成し、アーカイブを保存して、圧縮せずにパスワードで保護してファイルを保存するプロセスを完了します。

重要なポイントを要約し、読者に Aspose.Zip for .NET のさらなる可能性を探求するよう促して、チュートリアルを締めくくります。

## 結論

このチュートリアルでは、Aspose.Zip for .NET を使用して複数のファイルを圧縮せずに保存し、パスワードで保護する方法を検討しました。 .NET 開発を続ける際には、Aspose.Zip の機能を活用してファイル管理タスクを合理化し、アプリケーションのセキュリティを強化してください。

---

### よくある質問

### Aspose.Zip for .NET を他の暗号化方式で使用できますか?
はい、Aspose.Zip はさまざまな暗号化方式をサポートしています。ドキュメントを確認してください[ここ](https://reference.aspose.com/zip/net/)詳細については。

### Aspose.Zip for .NET のサポートはどこで入手できますか?
訪問[Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37)コミュニティのサポートとディスカッションのために。

### Aspose.Zip for .NET に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).

### Aspose.Zip for .NET の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスをリクエストする[ここ](https://purchase.aspose.com/temporary-license/).

### Aspose.Zip for .NET はどこで購入できますか?
 Aspose.Zip for .NET を購入できます[ここ](https://purchase.aspose.com/buy).
