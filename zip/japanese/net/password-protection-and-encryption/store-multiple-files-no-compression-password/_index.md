---
date: 2025-12-23
description: .NET 用 Aspose.Zip を使用して、zip ファイルにパスワードを設定する方法と zip アーカイブを暗号化する方法を学びましょう。安全なパスワードで圧縮せずに複数のファイルを保存できます。
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NETでZIPにパスワード保護を設定する方法
url: /ja/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET を使用した ZIP のパスワード保護方法

最新の .NET 開発では、アーカイブの保護は圧縮と同様に重要です。このチュートリアルでは、Aspose.Zip for .NET を使用して **ZIP にパスワードを設定する方法** ファイルを示すとともに、**圧縮なしで zip アーカイブを作成する方法** と **AES 暗号化で zip アーカイブを暗号化する方法** もデモします。本ガイドを読めば、任意の C# プロジェクトに組み込める明確なステップバイステップのソリューションが得られます。

## クイック回答
- **主要なライブラリは何ですか？** Aspose.Zip for .NET  
- **圧縮せずにファイルを保存できますか？** はい – `StoreCompressionSettings` を使用します。  
- **パスワードはどうやって設定しますか？** パスワードを指定した `AesEcryptionSettings` インスタンスを提供します。  
- **AES‑256 はサポートされていますか？** もちろんです – `EncryptionMethod.AES256` を設定します。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。

## 「ZIP にパスワードを設定する方法」とは？

パスワード保護は ZIP アーカイブに暗号化層を追加し、パスワードを知っているユーザーだけが内容を抽出できるようにします。Aspose.Zip を使用すると、アーカイブ作成時に暗号化設定を定義するだけでこのプロセスを簡単に行えます。

## Aspose.Zip for .NET を使用する理由

- **外部依存なし** – 純粋な .NET ライブラリ。  
- **圧縮、暗号化、アーカイブ構造を完全に制御**。  
- **AES‑256 などの最新暗号化方式に対応**。  
- **ストリーミング API により大容量ファイルを効率的に処理**。

## 前提条件

本題に入る前に、以下が揃っていることを確認してください：

- **Aspose.Zip for .NET ライブラリ** – **[こちら](https://releases.aspose.com/zip/net/)** からダウンロードしてください。  
- **ドキュメントディレクトリ** – アーカイブしたいファイルが入っているフォルダです。例では変数 `dataDir` がこの場所を指します。

## 名前空間のインポート

まず、Aspose.Zip を使用するために必要な名前空間をインポートします：

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 圧縮なしで .NET の Zip アーカイブを作成する方法

### 手順 1: Zip ファイルを開く

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

ここでは、エントリを格納する新しいアーカイブファイルを作成します。`FileMode.Create` フラグにより、実行ごとに新しいファイルが生成されます。

### 手順 2: ソースファイルを開く

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

最初のソースファイル（`alice29.txt`）を開きます。保存したい追加のファイルがある場合は、このブロックを繰り返してください。

### 手順 3: “圧縮なしの zip アーカイブ” を作成する

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

- `StoreCompressionSettings()` は Aspose.Zip に対しファイルを **圧縮しない**ことを指示し、**圧縮なしの zip アーカイブ** を作成します。  
- `AesEcryptionSettings("p@s$", EncryptionMethod.AES256)` は **zip アーカイブを暗号化する方法** を示し、パスワードは `"p@s$"`、暗号化方式は AES‑256 です。

### 手順 4: アーカイブエントリを追加して保存

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

ファイルがアーカイブに追加され、ディスクに保存されます。これで **ZIP にパスワードを設定する方法** のプロセスが完了します。

## よくある落とし穴とヒント

- **パスワードの複雑さ** – 強力なパスワードを使用してください。単純な文字列は総当たり攻撃で容易に破られます。  
- **ストリームの破棄** – `using` 文によりストリームが自動的に閉じられ、ファイルロックを防止します。  
- **複数ファイル** – さらにファイルを追加する場合は、追加の `FileStream` オブジェクトを開き、各々に対して `CreateEntry` を呼び出すだけです。  
- **互換性** – AES‑256 で暗号化された ZIP は、ほとんどの最新アーカイブツール（WinRAR、7‑Zip など）でサポートされています。

## よくある質問

**Q: AES‑256 以外の暗号化方式は使用できますか？**  
A: はい、Aspose.Zip は ZipCrypto や他の AES レベルをサポートしています。`EncryptionMethod` 列挙体を適宜変更してください。

**Q: 既存のアーカイブを暗号化することは可能ですか？**  
A: 必要な暗号化設定でアーカイブを再作成する必要があります。Aspose.Zip はリアルタイムで暗号化を変更できません。

**Q: 圧縮せずにファイルを保存するとアーカイブサイズは増えますか？**  
A: わずかに増加します。元のバイト列がそのまま保存されるためです。高速な展開が必要な場合や元ファイルの完全性を保持したい場合に有用です。

**Q: パスワード保護されたファイルを取得するには？**  
A: 作成時に使用した同じ `AesEcryptionSettings`（パスワード）を指定して `Archive` インスタンスでアーカイブを開きます。

**Q: ファイルサイズやエントリ数に制限はありますか？**  
A: Aspose.Zip は大容量ファイルや数千件のエントリを処理できます。制限はシステムのメモリとストレージに依存します。

## 追加リソース

- **Aspose.Zip ドキュメント** – 詳細な API リファレンスは **[こちら](https://reference.aspose.com/zip/net/)**。  
- **コミュニティサポート** – **[Aspose.Zip フォーラム](https://forum.aspose.com/c/zip/37)** で質問してください。  
- **無料トライアル** – 試用版は **[こちら](https://releases.aspose.com/)**。  
- **一時ライセンス** – **[こちら](https://purchase.aspose.com/temporary-license/)** からリクエストできます。  
- **購入オプション** – 正規ライセンスは **[こちら](https://purchase.aspose.com/buy)** から購入できます。

---

**最終更新日:** 2025-12-23  
**テスト環境:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}