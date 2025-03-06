---
title: .NET용 Aspose.Zip - 안전한 파일 저장 튜토리얼
linktitle: 비밀번호를 사용하여 압축하지 않고 여러 파일 저장
second_title: 파일 압축 및 보관을 위한 Aspose.Zip .NET API
description: .NET용 Aspose.Zip을 사용하여 압축 없이 여러 파일을 안전하게 저장하는 방법을 알아보세요. 비밀번호 보호를 위한 쉬운 단계. 파일 관리의 힘을 느껴보세요!
weight: 13
url: /ko/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Zip - 안전한 파일 저장 튜토리얼


.NET 개발 세계에서는 파일 관리 및 조작이 일반적인 작업입니다. Aspose.Zip for .NET은 개발자에게 zip 아카이브를 원활하게 압축, 압축 해제 및 조작할 수 있는 기능을 제공하는 강력한 라이브러리입니다. 이 튜토리얼에서는 압축하지 않고 여러 파일을 저장하고 비밀번호로 보호하는 특정 시나리오를 자세히 살펴보겠습니다. 이 가이드를 마치면 .NET용 Aspose.Zip을 사용하여 이 기능을 구현하는 데 필요한 지식을 갖추게 됩니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.Zip: .NET 라이브러리용 Aspose.Zip이 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/zip/net/).

-  문서 디렉터리: 소스 파일이 있는 디렉터리를 준비합니다. 제공된 예에서 변수는`dataDir` 문서 디렉토리를 나타냅니다.

## 네임스페이스 가져오기

시작하려면 코드에 필요한 네임스페이스를 가져오겠습니다.

```csharp
// 리소스 디렉터리의 경로입니다.
string dataDir = "Your Document Directory"

// Aspose.Zip 네임스페이스 가져오기
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## 1단계: Zip 파일 열기

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 이 단계에는 다음을 사용하여 새 zip 파일을 만드는 작업이 포함됩니다.`FileStream`. 파일 이름은 "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip"입니다.

## 2단계: 소스 파일 열기

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

여기서는 zip 아카이브에 저장될 첫 번째 소스 파일인 "alice29.txt"를 엽니다.

## 3단계: 아카이브 생성

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 이 단계에서는`Archive` 클래스, 압축 및 암호화 설정을 지정합니다. 우리는`StoreCompressionSettings` 압축하지 않고 파일을 저장하려면`AesEcryptionSettings` 비밀번호("p@s$")를 사용하여 AES 암호화를 적용합니다.

## 4단계: 아카이브 항목 생성 및 저장

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

이 마지막 단계에는 "alice29.txt"에 대한 항목을 아카이브에 생성하고 아카이브를 저장하며, 압축 없이 비밀번호로 보호하여 파일을 저장하는 프로세스를 완료하는 작업이 포함됩니다.

핵심 사항을 요약하고 독자들이 .NET용 Aspose.Zip을 사용하여 더 많은 가능성을 탐색하도록 독려하여 튜토리얼을 마무리하세요.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Zip을 사용하여 압축 없이 여러 파일을 저장하고 비밀번호로 보호하는 방법을 살펴보았습니다. .NET 개발을 계속하면서 Aspose.Zip의 기능을 활용하여 파일 관리 작업을 간소화하고 애플리케이션의 보안을 강화하세요.

---

### 자주 묻는 질문

### 다른 암호화 방법과 함께 .NET용 Aspose.Zip을 사용할 수 있나요?
 예, Aspose.Zip은 다양한 암호화 방법을 지원합니다. 문서를 확인하세요[여기](https://reference.aspose.com/zip/net/) 자세한 내용은.

### .NET용 Aspose.Zip에 대한 지원은 어디서 받을 수 있나요?
 방문하다[Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37) 커뮤니티 지원 및 토론을 위해.

### .NET용 Aspose.Zip에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).

### .NET용 Aspose.Zip의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스 요청[여기](https://purchase.aspose.com/temporary-license/).

### .NET용 Aspose.Zip을 어디서 구입할 수 있나요?
 .NET용 Aspose.Zip을 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
