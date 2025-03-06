---
title: Aspose.Zip을 사용한 .NET의 마스터 보안 보관
linktitle: 암호화된 항목으로 보관
second_title: 파일 압축 및 보관을 위한 Aspose.Zip .NET API
description: Aspose.Zip을 사용하여 .NET의 보안 보관 세계를 탐험해 보세요. AES 암호화를 사용하여 손쉽게 Seven Zip 파일을 생성하세요. 지금 바로 개발 능력을 강화해보세요!
weight: 15
url: /ko/net/password-protection-and-encryption/archive-with-encrypted-entry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip을 사용한 .NET의 마스터 보안 보관


## 소개

끊임없이 진화하는 소프트웨어 개발 세계에서는 효율적인 압축 및 암호화 기술을 익히는 것이 중요합니다. .NET용 Aspose.Zip은 개발자가 암호화된 항목이 포함된 아카이브를 원활하게 관리할 수 있는 강력한 도구로 등장합니다. 이 포괄적인 튜토리얼에서는 Aspose.Zip for .NET을 사용하여 AES 암호화 설정으로 Seven Zip 파일을 생성하는 과정을 자세히 살펴보겠습니다.

## 전제 조건

이 여정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 개발 환경: 컴퓨터에 .NET 개발 환경을 설정합니다.
-  .NET용 Aspose.Zip: Aspose.Zip 라이브러리를 설치합니다. 필요한 서류를 찾으실 수 있습니다[여기](https://reference.aspose.com/zip/net/).
-  다운로드: 다음에서 .NET용 Aspose.Zip 라이브러리를 얻습니다.[다운로드 링크](https://releases.aspose.com/zip/net/).
- 기본 지식: C# 및 .NET 개발의 기본 개념을 숙지하세요.

## 네임스페이스 가져오기

C# 프로젝트에서 필수 네임스페이스를 가져오는 것부터 시작합니다.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## 1단계: 리소스 디렉터리 경로 설정

```csharp
// 리소스 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
```

## 2단계: AES 암호화를 사용하여 Seven Zip 파일 생성

```csharp
//ExStart: ArchiveWithEncryptedEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", 
            new MemoryStream(new byte[] { 0x00, 0xFF }), 
            new SevenZipEntrySettings(new SevenZipLZMACompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.Save(sevenZipFile);
    }
}
//ExEnd: ArchiveWithEncryptedEntry
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

설명: 이 단계에서는 "archive.7z"라는 Seven Zip 파일을 생성하고 샘플 데이터와 함께 암호화된 항목 "entry1.bin"을 추가합니다. 암호화 설정은 "test1" 키와 함께 AES 알고리즘을 활용합니다.

필요한 경우 추가 항목에 대해 위 단계를 반복합니다.

## 결론

축하해요! .NET용 Aspose.Zip을 사용하여 AES 암호화 설정으로 Seven Zip 파일을 성공적으로 만들었습니다. 이 자습서에서는 .NET 프로젝트에서 보안 보관을 구현하는 방법에 대한 기본적인 이해를 제공합니다.

## 자주 묻는 질문

### 비상업적 프로젝트에서 .NET용 Aspose.Zip을 사용할 수 있나요?
예, .NET용 Aspose.Zip은 상업용 및 비상업적 프로젝트 모두에서 사용할 수 있습니다.

### .NET용 Aspose.Zip의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/).

### .NET용 Aspose.Zip에 대한 커뮤니티 지원이 제공됩니까?
 네, 방문해 보세요[Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37) 지역 사회 지원을 위해.

### LZMA 외에 지원되는 다른 압축 알고리즘이 있습니까?
.NET용 Aspose.Zip은 다양한 압축 알고리즘을 지원합니다. 자세한 내용은 설명서를 참조하세요.

### 암호화 설정을 추가로 사용자 정의할 수 있나요?
전적으로! 고급 암호화 사용자 정의 옵션에 대한 설명서를 살펴보세요.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
