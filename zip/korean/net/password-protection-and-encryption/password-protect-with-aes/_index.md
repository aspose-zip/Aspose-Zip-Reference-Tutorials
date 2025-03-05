---
title: 파일 보안 - Aspose.Zip을 사용한 AES 암호화
linktitle: AES로 비밀번호 보호
second_title: 파일 압축 및 보관을 위한 Aspose.Zip .NET API
description: AES 암호화가 포함된 .NET용 Aspose.Zip을 사용하여 파일 보안을 강화하는 방법을 알아보세요. 최적의 보호를 위해 단계별 가이드를 따르세요.
type: docs
weight: 11
url: /ko/net/password-protection-and-encryption/password-protect-with-aes/
---

## 소개

민감한 파일을 보호하는 것은 오늘날의 디지털 시대에 매우 중요하며 .NET용 Aspose.Zip은 AES(Advanced Encryption Standard)를 사용하여 아카이브를 비밀번호로 보호하는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 128비트, 192비트, 256비트의 세 가지 키 길이로 AES 암호화를 구현하여 압축 파일에 대해 최고 수준의 보안을 보장하는 방법을 살펴보겠습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Zip: Aspose.Zip 라이브러리가 .NET 프로젝트에 통합되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/zip/net/).

- 문서 디렉터리: 소스 파일이 있는 디렉터리가 있습니다.

## 네임스페이스 가져오기

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## 1단계: AES-128로 비밀번호 보호

```csharp
//ExStart:PasswordProtectWithAES128
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
//ExEnd: PasswordProtectWithAES128
```

이 단계에서는 zip 파일을 생성하고 AES-128 암호화로 보호합니다. 비밀번호 "p@s$"는 아카이브의 보안을 보장합니다.

## 2단계: AES-192로 비밀번호 보호

```csharp
//ExStart:PasswordProtectWithAES192
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
//ExEnd: PasswordProtectWithAES192
```

이 단계에서는 보안 강화를 위해 AES-192 암호화를 구현하는 방법을 보여줍니다. 일관성을 위해 동일한 비밀번호 "p@s$"가 사용됩니다.

## 3단계: AES-256으로 비밀번호 보호

```csharp
//ExStart:PasswordProtectWithAES256
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
// ExEnd: PasswordProtectWithAES256
```

이 마지막 단계에서는 최고 수준의 암호화인 AES-256을 구현하여 압축 파일에 대한 추가 보안 계층을 제공합니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Zip에서 AES 암호화를 사용하여 아카이브를 비밀번호로 보호하는 필수 단계를 다루었습니다. 128비트, 192비트 또는 256비트 암호화 중 무엇을 선택하든 파일은 무단 액세스로부터 보호됩니다.

## 자주 묻는 질문

### 다른 프로그래밍 언어와 함께 .NET용 Aspose.Zip을 사용할 수 있나요?
Aspose.Zip은 주로 .NET 애플리케이션용으로 설계되어 원활한 통합과 최적의 성능을 보장합니다.

### AES 암호화 방법은 민감한 데이터에 안전합니까?
예, AES 암호화는 민감한 정보를 보호하기 위한 안전하고 강력한 방법으로 널리 인식되고 있습니다.

### 이미 암호화된 아카이브의 비밀번호를 변경할 수 있나요?
아니요. 암호화된 아카이브의 비밀번호는 일단 설정되면 변경할 수 없습니다. 다른 비밀번호를 사용하여 암호화된 새 아카이브를 생성해야 합니다.

### Aspose.Zip을 사용하여 암호화할 수 있는 파일 형식에 제한이 있나요?
Aspose.Zip은 다양한 파일 형식의 암호화를 지원하여 다양한 종류의 데이터를 보호하는 유연성을 보장합니다.

### 암호화된 아카이브의 비밀번호를 잊어버리면 어떻게 되나요?
안타깝게도 암호화된 아카이브의 비밀번호를 복구할 수 있는 방법은 없습니다. 비밀번호를 안전한 곳에 보관하는 것이 중요합니다.
