---
date: 2026-05-30
description: Aspose.Zip for .NET를 사용하여 폴더를 압축하는 방법을 배우고, .NET에서 zip 아카이브를 효율적으로 생성하며,
  .NET 애플리케이션의 저장 공간을 절감하세요.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: 폴더 압축하기
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET를 사용하여 폴더 압축하는 방법
url: /ko/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET을 사용하여 폴더 압축하는 방법

이 튜토리얼에서는 Aspose.Zip for .NET을 사용하여 **폴더 압축 방법**을 빠르고 안정적으로 배우게 됩니다. 데스크톱 유틸리티, 클라우드 기반 서비스, 자동 백업 스크립트를 구축하든, 폴더를 ZIP 아카이브로 압축하면 저장 용량을 크게 줄이고 네트워크 전송 속도를 높일 수 있습니다. 모든 단계를 차례대로 안내하고, 각 코드 라인의 의미를 설명하며, 흔히 발생하는 함정을 강조하여 자신 있게 적용할 수 있도록 도와드립니다.

## 빠른 답변
- **Aspose.Zip은 무엇을 하나요?** 외부 종속성 없이 ZIP 아카이브를 생성하고 추출할 수 있는 간단한 .NET API를 제공합니다.  
- **구현에 얼마나 걸리나요?** 기본 폴더 압축의 경우 일반적으로 10분 미만 소요됩니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1, 그리고 .NET 5‑10.  
- **프로덕션에 라이선스가 필요합니까?** 예, 프로덕션 사용을 위해서는 상업용 라이선스가 필요합니다.  
- **한 번에 여러 폴더를 압축할 수 있나요?** 물론입니다—任意의 `DirectoryInfo` 컬렉션에 `CreateEntries` 메서드를 사용하여 한 번에 **여러 폴더를 압축**할 수 있습니다.  

`CreateEntries`는 디렉터리의 모든 파일을 아카이브에 추가합니다.

## “폴더 압축 방법”이란?

폴더를 압축한다는 것은 지정된 디렉터리 안의 모든 파일과 하위 폴더를 하나의 ZIP 아카이브로 묶는 것을 의미합니다. 이렇게 하면 전체 크기가 감소하고 원래 계층 구조가 보존되며 데이터를 전송하거나 저장하기가 쉬워집니다. 생성된 ZIP은 특수 소프트웨어 없이도 모든 플랫폼에서 열 수 있으며, 폴더 구조를 유지하므로 압축을 풀면 원래 레이아웃이 정확히 복원됩니다.

## 이 작업에 Aspose.Zip을 사용하는 이유

Aspose.Zip을 사용하면 지원되는 모든 런타임에서 일관된 API로 .NET 코드에서 직접 **ZIP 아카이브** 파일을 생성할 수 있습니다. `Archive` 클래스를 로드하고, 엔트리를 추가하고, `CompressionLevel`을 설정하며, 필요에 따라 비밀번호를 지정하고 `Save`를 호출합니다. 이 라이브러리는 일반 하드웨어에서 수천 개 파일이 포함된 폴더를 1초 미만에 처리하며, 50가지가 넘는 다양한 압축 형식 및 암호화 알고리즘을 지원합니다.

## 사전 요구 사항

- **Aspose.Zip for .NET** – [여기](https://releases.aspose.com/zip/net/) 또는 [여기](https://releases.aspose.com/zip/net)에서 다운로드하세요.  
- **개발 환경** – Visual Studio, Rider 또는 C#을 지원하는 모든 IDE.  
- **문서 디렉터리** – 코드에서 `"Your Document Directory"`를 압축하려는 폴더 경로로 교체하세요.  
- **참조 문서** – 공식 문서는 [여기](https://reference.aspose.com/zip/net/)에서 확인하세요.

## 네임스페이스 가져오기

필요한 네임스페이스를 가져오는 것으로 시작합니다. 이를 통해 핵심 압축 클래스를 사용할 수 있습니다.

```csharp
using Aspose.Zip;
using System.IO;
```

## Aspose.Zip을 사용하여 폴더 압축하는 방법

다음은 **폴더 압축 방법**을 보여주는 간단한 예제입니다. 동일한 패턴을 사용하여 **여러 파일을 .net에서 압축**하거나 사용자 정의 아카이브 구조를 만들 수도 있습니다.

### 단계 1: 문서 디렉터리 초기화

`dataDir` 변수를 압축하려는 디렉터리 경로로 설정합니다.

```csharp
string dataDir = "Your Document Directory";
```

### 단계 2: 출력 ZIP 파일 생성

출력 ZIP 파일을 위해 두 개의 `FileStream` 객체를 엽니다. 이는 동일한 소스에서 여러 아카이브를 생성할 수 있음을 보여주며, 버전 백업에 유용합니다.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### 단계 3: 디렉터리 압축

`Archive` 클래스는 ZIP 아카이브를 나타내며 엔트리를 추가하고 파일을 저장하는 메서드를 제공합니다. 이를 사용하여 대상 폴더의 모든 엔트리를 추가합니다. 예제에서는 **CanterburyCorpus**라는 샘플 폴더를 사용하지만, 원하는 어떤 디렉터리에도 지정할 수 있습니다.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **팁:** 특정 압축 수준으로 **.net에서 zip 아카이브 생성**이 필요하면 `Save`를 호출하기 전에 `archive.CompressionLevel`을 설정하세요.

## 일반적인 문제 및 해결책

| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| 빈 ZIP 파일 | `dataDir`가 잘못된 폴더를 가리키거나 끝 슬래시가 없습니다 | 경로를 확인하고 폴더에 파일이 있는지 확인하세요 |
| `UnauthorizedAccessException` | 애플리케이션에 파일 시스템 권한이 없습니다 | Visual Studio를 관리자 권한으로 실행하거나 읽기/쓰기 권한을 부여하세요 |
| 대용량 디렉터리에서 메모리 사용량이 많음 | 모든 엔트리를 한 번에 메모리로 로드 | `Archive.CreateEntryFromFile`을 루프에서 사용하여 파일을 개별적으로 스트리밍하세요 |

## 자주 묻는 질문 (추가)

**Q: ZIP 아카이브에 비밀번호를 추가할 수 있나요?**  
A: 예. `Save`를 호출하기 전에 `archive.Password = "yourPassword";`를 설정합니다.

**Q: 특정 파일 유형만 포함하려면 어떻게 해야 하나요?**  
A: `CreateEntries`를 호출하기 전에 `GetFiles("*.txt")`와 같은 방식으로 `DirectoryInfo` 컬렉션을 필터링합니다.

**Q: 기존 ZIP을 다시 만들지 않고 업데이트할 방법이 있나요?**  
A: Aspose.Zip은 `Archive.UpdateEntry`를 통해 증분 업데이트를 지원합니다.

## FAQ

### Q1: Aspose.Zip for .NET을 상업 및 개인 프로젝트 모두에서 사용할 수 있나요?
A1: 예, Aspose.Zip for .NET은 상업 및 개인 용도로 모두 라이선스가 부여됩니다.

### Q2: 무료 체험판이 있나요?
A2: 예, 무료 체험판을 [여기](https://releases.aspose.com/zip/net)에서 확인할 수 있습니다.

### Q3: Aspose.Zip for .NET에 대한 지원을 어떻게 받나요?
A3: 커뮤니티 지원을 위해 [Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37)을 방문하거나 전용 지원을 위해 [임시 라이선스](https://purchase.aspose.com/temporary-license/) 구매를 고려하세요.

### Q4: 다른 예제와 튜토리얼이 있나요?
A4: 예, [문서](https://reference.aspose.com/zip/net/)에 포괄적인 예제와 튜토리얼이 포함되어 있습니다.

### Q5: Aspose.Zip for .NET을 구매할 수 있나요?
A5: 물론입니다. 구매는 [여기](https://purchase.aspose.com/buy)에서 할 수 있습니다.

## 결론

이제 Aspose.Zip for .NET을 사용하여 **폴더 압축 방법**에 대한 완전하고 프로덕션 준비된 패턴을 갖추었습니다. 라이브러리의 `Archive` 클래스를 활용하면 **ZIP 아카이브** 파일을 생성하고, 사용자 정의 `CompressionLevel`을 설정하고, 비밀번호 보호를 추가하며, 한 번에 **여러 폴더를 압축**할 수 있어 폴더 백업 작업을 자동화하는 데 최적입니다. API를 활용해 암호화, 아카이브 분할, 클라우드 스토리지 직접 스트리밍 등을 실험해 보세요. 그러면 .NET 기반 압축 요구 사항에 대한 강력한 솔루션을 얻게 됩니다.

---

**마지막 업데이트:** 2026-05-30  
**테스트 환경:** Aspose.Zip 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [여러 파일 zip c# – Aspose.Zip for .NET으로 손쉬운 압축](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip for .NET - 비밀번호로 ZIP 아카이브 보호 및 압축 없이 여러 파일 저장](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [폴더 압축 방법 – Aspose.Zip으로 디렉터리 압축](/zip/net/directory-and-folder-compression/decompress-folder/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}