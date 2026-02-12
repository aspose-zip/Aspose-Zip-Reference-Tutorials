---
date: 2026-02-12
description: Aspose.Zip for .NET를 사용하여 폴더를 압축하는 방법을 배우고, .NET에서 효율적으로 zip 아카이브를 생성하며,
  .NET 애플리케이션의 저장 공간을 절감하세요.
linktitle: How to Zip a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET를 사용하여 폴더를 압축하는 방법
url: /ko/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET을 사용한 폴더 압축 방법

이 튜토리얼에서는 Aspose.Zip for .NET을 사용하여 **폴더 압축 방법**을 빠르고 안정적으로 배우게 됩니다. 데스크톱 유틸리티, 클라우드 기반 서비스, 자동 백업 스크립트 등 어떤 것을 만들든, 폴더를 ZIP 아카이브로 압축하면 저장 용량을 크게 줄이고 네트워크 전송 속도를 높일 수 있습니다. 모든 단계를 차례대로 안내하고, 각 코드 라인이 중요한 이유를 설명하며, 흔히 발생하는 함정을 강조하여 자신 있게 적용할 수 있도록 도와드립니다.

## 빠른 답변
- **Aspose.Zip은 무엇을 하나요?** 외부 종속성 없이 ZIP 아카이브를 생성하고 추출할 수 있는 간단한 .NET API를 제공합니다.  
- **구현에 얼마나 걸리나요?** 기본 폴더 압축의 경우 보통 10분 미만 소요됩니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **프로덕션에 라이선스가 필요합니까?** 예, 프로덕션 사용을 위해 상용 라이선스가 필요합니다.  
- **한 번에 여러 폴더를 압축할 수 있나요?** 물론입니다—任意의 `DirectoryInfo` 컬렉션에 `CreateEntries` 메서드를 사용하여 **여러 폴더를 한 번에 압축**할 수 있습니다.

## “폴더 압축 방법”이란?

폴더를 압축한다는 것은 지정된 디렉터리 안에 있는 모든 파일과 하위 폴더를 하나의 ZIP 아카이브로 묶는 것을 의미합니다. 이렇게 하면 전체 크기가 줄어들고 원래 계층 구조가 보존되며 데이터를 전송하거나 저장하기가 쉬워집니다.

## 이 작업에 Aspose.Zip을 사용하는 이유

- **속도 및 효율성:** 최적화된 알고리즘으로 대용량 폴더를 빠르게 처리합니다.  
- **Pure .NET:** 네이티브 바이너리나 서드파티 도구가 필요 없습니다.  
- **풍부한 기능 세트:** 비밀번호 보호(`add password zip`), 스트리밍, 사용자 지정 압축 레벨 설정(`set compression level`)을 지원합니다.  
- **일관된 API:** .NET Framework, .NET Core, .NET 5/6 모두에서 동일하게 동작하여 **create zip archive .net** 시나리오에 이상적입니다.  

## 사전 요구 사항

- **Aspose.Zip for .NET** – 다운로드는 [here](https://releases.aspose.com/zip/net/)에서 가능합니다.  
- **Development Environment** – Visual Studio, Rider 또는 C#을 지원하는 모든 IDE.  
- **Document Directory** – 코드에서 `"Your Document Directory"`를 압축하려는 폴더 경로로 교체합니다.  
- **Reference Documentation** – 공식 문서는 [here](https://reference.aspose.com/zip/net/)에서 확인하세요.  

## 네임스페이스 가져오기

필요한 네임스페이스를 가져와야 합니다. 이를 통해 핵심 압축 클래스를 사용할 수 있습니다.

```csharp
using Aspose.Zip;
using System.IO;
```

## Aspose.Zip으로 폴더 압축하기

아래 예제는 **폴더 압축 방법**을 보여주는 간단한 코드입니다. 동일한 패턴을 활용해 **zip multiple files .net**을 수행하거나 사용자 정의 아카이브 구조를 만들 수 있습니다.

### 단계 1: 문서 디렉터리 초기화

압축하려는 디렉터리 경로를 `dataDir` 변수에 설정합니다.

```csharp
string dataDir = "Your Document Directory";
```

### 단계 2: 출력 ZIP 파일 생성

두 개의 `FileStream` 객체를 열어 출력 ZIP 파일을 생성합니다. 이는 동일한 소스에서 여러 아카이브를 만들 수 있음을 보여주며, 버전 백업에 유용합니다.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### 단계 3: 디렉터리 압축

`Archive` 클래스를 사용해 대상 폴더의 모든 항목을 추가합니다. 예제에서는 **CanterburyCorpus**라는 샘플 폴더를 사용하지만, 원하는 어떤 디렉터리라도 지정할 수 있습니다.

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

> **Pro tip:** 특정 압축 레벨로 **create zip archive .net**을 만들고 싶다면 `Save` 호출 전에 `archive.CompressionLevel`을 설정하세요.

## 일반적인 문제 및 해결책

| 증상 | 가능 원인 | 해결 방법 |
|---------|--------------|-----|
| 빈 ZIP 파일 | `dataDir`가 잘못된 폴더를 가리키거나 끝 슬래시가 없음 | 경로를 확인하고 폴더에 파일이 있는지 확인 |
| `UnauthorizedAccessException` | 애플리케이션에 파일 시스템 권한이 없음 | Visual Studio를 관리자 권한으로 실행하거나 읽기/쓰기 권한을 부여 |
| 대용량 디렉터리에서 메모리 사용량이 많음 | 한 번에 모든 항목을 메모리로 로드 | `Archive.CreateEntryFromFile`을 루프에서 사용하여 파일을 개별적으로 스트리밍 |

## 자주 묻는 질문 (추가)

**Q: ZIP 아카이브에 비밀번호를 추가할 수 있나요?**  
A: 예. `Save` 호출 전에 `archive.Password = "yourPassword";` 로 설정합니다.

**Q: 특정 파일 유형만 포함하려면 어떻게 해야 하나요?**  
A: `CreateEntries` 호출 전에 `DirectoryInfo` 컬렉션을 `GetFiles("*.txt")` 등으로 필터링합니다.

**Q: 기존 ZIP을 다시 만들지 않고 업데이트할 방법이 있나요?**  
A: Aspose.Zip은 `Archive.UpdateEntry`를 통해 증분 업데이트를 지원합니다.

## FAQ's

### Q1: Aspose.Zip for .NET을 상업용 및 개인 프로젝트 모두에 사용할 수 있나요?

A1: 예, Aspose.Zip for .NET은 상업용 및 개인용 프로젝트 모두에 사용할 수 있는 라이선스가 제공됩니다.

### Q2: 무료 체험을 이용할 수 있나요?

A2: 예, 무료 체험을 [here](https://releases.aspose.com/zip/net)에서 확인할 수 있습니다.

### Q3: Aspose.Zip for .NET에 대한 지원은 어떻게 받나요?

A3: [Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37)에서 커뮤니티 지원을 받거나 전용 지원을 위해 [temporary license](https://purchase.aspose.com/temporary-license/)를 구매할 수 있습니다.

### Q4: 다른 예제와 튜토리얼이 있나요?

A4: 예, [documentation](https://reference.aspose.com/zip/net/)에 포괄적인 예제와 튜토리얼이 포함되어 있습니다.

### Q5: Aspose.Zip for .NET을 구매할 수 있나요?

A5: 물론입니다. [here](https://purchase.aspose.com/buy)에서 구매하실 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-02-12  
**테스트 환경:** Aspose.Zip 24.11 for .NET  
**작성자:** Aspose  

---