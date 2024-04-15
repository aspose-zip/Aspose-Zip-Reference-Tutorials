---
title: ファイルを保護 - Aspose.Zip による AES 暗号化
linktitle: AES によるパスワード保護
second_title: ファイルの圧縮とアーカイブのための Aspose.Zip .NET API
description: AES 暗号化を備えた Aspose.Zip for .NET を使用してファイルのセキュリティを強化する方法を学びます。最適な保護を実現するには、段階的なガイドに従ってください。
type: docs
weight: 11
url: /ja/net/password-protection-and-encryption/password-protect-with-aes/
---

## 導入

今日のデジタル時代では、機密ファイルの保護は非常に重要です。Aspose.Zip for .NET は、Advanced Encryption Standard (AES) を使用してアーカイブをパスワードで保護するための堅牢なソリューションを提供します。このチュートリアルでは、128 ビット、192 ビット、256 ビットの 3 つのキー長で AES 暗号化を実装し、圧縮ファイルに最高レベルのセキュリティを確保する方法を説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Zip for .NET: Aspose.Zip ライブラリが .NET プロジェクトに統合されていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/zip/net/).

- ドキュメント ディレクトリ: ソース ファイルが配置されるディレクトリを用意します。

## 名前空間のインポート

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## ステップ 1: AES-128 によるパスワード保護

```csharp
//ExStart:AES128 によるパスワード保護
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd:PasswordProtectWithAES128
```

このステップでは、zip ファイルを作成し、AES-128 暗号化で保護します。パスワード「p@s$」により、アーカイブのセキュリティが確保されます。

## ステップ 2: AES-192 によるパスワード保護

```csharp
//ExStart:AES192 によるパスワード保護
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd:AES192 によるパスワード保護
```

このステップでは、セキュリティを強化するために AES-192 暗号化を実装する方法を示します。一貫性を保つために、同じパスワード「p@s$」が使用されます。

## ステップ 3: AES-256 によるパスワード保護

```csharp
//ExStart:AES256 によるパスワード保護
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd:AES256 によるパスワード保護
```

この最後のステップでは、最高レベルの暗号化である AES-256 を実装し、圧縮ファイルに追加のセキュリティ層を提供します。

## 結論

このチュートリアルでは、Aspose.Zip for .NET で AES 暗号化を使用してアーカイブをパスワード保護するための重要な手順を説明しました。 128 ビット、192 ビット、256 ビットのいずれの暗号化を選択しても、ファイルは不正アクセスから保護されます。

## よくある質問

### Aspose.Zip for .NET を他のプログラミング言語で使用できますか?
Aspose.Zip は主に .NET アプリケーション用に設計されており、シームレスな統合と最適なパフォーマンスを保証します。

### AES 暗号化方式は機密データに対して安全ですか?
はい、AES 暗号化は、機密情報を保護する安全かつ堅牢な方法として広く認識されています。

### すでに暗号化されているアーカイブのパスワードを変更できますか?
いいえ、暗号化されたアーカイブのパスワードは、一度設定すると変更できません。別のパスワードを使用して新しい暗号化アーカイブを作成する必要があります。

### Aspose.Zip を使用して暗号化できるファイルの種類に制限はありますか?
Aspose.Zip はさまざまな種類のファイルの暗号化をサポートし、さまざまな種類のデータを柔軟に保護します。

### 暗号化されたアーカイブのパスワードを忘れた場合はどうなりますか?
残念ながら、暗号化されたアーカイブのパスワードを回復する方法はありません。パスワードを安全な場所に保管することが重要です。
