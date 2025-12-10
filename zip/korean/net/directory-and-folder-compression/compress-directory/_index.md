---
date: 2025-12-09
description: Aspose.Zip for .NET를 사용하여 디렉터리를 압축하고 zip 아카이브를 효율적으로 만드는 방법을 배워보세요. .NET
  애플리케이션에서 저장 공간을 최적화하세요.
linktitle: How to Compress a Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET을 사용하여 디렉터리 압축하는 방법
url: /ko/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET를 사용한 손쉬운 디렉터리 압축

이 튜토리얼에서는 Aspose.Zip for .NET를 사용하여 **디렉터리를 압축하는 방법**을 보여드립니다. 이는 대용량 데이터 세트를 관리하고 저장 공간을 절약하는 강력한 방법입니다. 데스크톱 유틸리티를 만들든 클라우드 기반 서비스를 구축하든, 폴더를 효율적으로 압축하면 성능이 크게 향상되고 비용이 절감됩니다. 각 단계를 차례대로 진행하면서 코드의 논리를 설명하고 일반적인 함정들을 짚어드리므로 자신 있게 기술을 적용할 수 있습니다.

## 빠른 답변
- **Aspose.Zip는 무엇을 하나요?** 외부 종속성 없이 ZIP 아카이브를 생성하고 추출할 수 있는 간단한 .NET API를 제공합니다.  
- **구현에 걸리는 시간은?** 기본 디렉터리 압축의 경우 일반적으로 10분 미만이 소요됩니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, 및 .NET 5/6+.  
- **프로덕션에 라이선스가 필요한가요?** 예, 프로덕션 사용을 위해서는 상용 라이선스가 필요합니다.  
- **여러 폴더를 한 번에 압축할 수 있나요?** 물론입니다—어떤 `DirectoryInfo` 컬렉션에도 `CreateEntries` 메서드를 사용할 수 있습니다.

## 소개

Aspose.Zip for .NET는 .NET 개발자가 압축 파일 및 디렉터리를 원활하게 작업할 수 있게 해주는 강력한 라이브러리입니다. 대용량 데이터 세트를 다루거나 **generate zip file c#** 스타일의 아카이브를 생성해야 할 때, Aspose.Zip는 압축 및 해제 작업을 위한 강력한 기능 세트를 제공합니다.

## “디렉터리를 압축하는 방법”이란?

디렉터리를 압축한다는 것은 지정된 폴더 내의 모든 파일과 하위 폴더를 하나의 ZIP 아카이브로 묶는 것을 의미합니다. 이렇게 하면 전체 크기가 줄어들고 전송이 간편해지며 원래 폴더 구조가 보존됩니다.

## 이 작업에 Aspose.Zip를 사용하는 이유

- **Speed & Efficiency:** 최적화된 알고리즘이 대용량 폴더를 빠르게 처리합니다.  
- **Pure .NET:** 네이티브 바이너리나 서드파티 도구가 필요 없습니다.  
- **Rich Feature Set:** 비밀번호 보호, 스트리밍, 실시간 항목 추가를 지원—**zip multiple files .net** 시나리오에 최적입니다.  
- **Consistent API:** .NET Framework, .NET Core, 및 .NET 5/6 전반에 걸쳐 동일하게 동작합니다.

## 사전 요구 사항

- **Aspose.Zip for .NET** – 다운로드는 [여기](https://releases.aspose.com/zip/net/)에서 가능합니다.  
- **Development Environment** – Visual Studio, Rider, 또는 C#을 지원하는 모든 IDE.  
- **Document Directory** – 코드에서 `"Your Document Directory"`를 압축하려는 폴더 경로로 교체합니다.  
- **Reference Documentation** – 공식 문서는 [여기](https://reference.aspose.com/zip/net/)에서 확인하세요.

## 네임스페이스 가져오기

필요한 네임스페이스를 가져오는 것으로 시작합니다. 이를 통해 핵심 압축 클래스를 사용할 수 있습니다.

```csharp
using Aspose.Zip;
using System.IO;
```

## Aspose.Zip로 폴더 압축하기

다음은 **폴더를 압축하는 방법**을 보여주는 간단한 예제입니다. 동일한 패턴을 **zip multiple files .net**에 확장하거나 사용자 정의 아카이브 구조를 만드는 데 사용할 수 있습니다.

### 단계 1: 문서 디렉터리 초기화

`dataDir` 변수를 압축하려는 디렉터리 경로로 설정합니다.

```csharp
string dataDir = "Your Document Directory";
```

### 단계 2: 출력 ZIP 파일 생성

출력 ZIP 파일을 위해 두 개의 `FileStream` 객체를 엽니다. 이를 통해 동일한 소스에서 두 개 이상의 아카이브를 생성할 수 있음을 보여줍니다—버전 백업에 유용합니다.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### 단계 3: 디렉터리 압축

`Archive` 클래스를 사용하여 대상 폴더의 모든 항목을 추가합니다. 예제에서는 **CanterburyCorpus**라는 샘플 폴더를 사용하지만, 원하는 어떤 디렉터리라도 지정할 수 있습니다.

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

> **Pro tip:** 특정 압축 수준으로 **create zip archive .net**을(를) 만들어야 할 경우, `Save`를 호출하기 전에 `archive.CompressionLevel`을 설정하세요.

## 일반적인 문제 및 해결책

| 증상 | 가능한 원인 | 해결 방법 |
|------|------------|----------|
| 빈 ZIP 파일 | `dataDir`가 잘못된 폴더를 가리키거나 끝 슬래시가 누락됨 | 경로를 확인하고 폴더에 파일이 있는지 확인하세요 |
| `UnauthorizedAccessException` | 애플리케이션에 파일 시스템 권한이 없음 | Visual Studio를 관리자 권한으로 실행하거나 읽기/쓰기 권한을 부여하세요 |
| 대용량 디렉터리에서 메모리 사용량이 많음 | 한 번에 모든 항목을 메모리에 로드함 | `Archive.CreateEntryFromFile`을 루프에서 사용하여 파일을 개별적으로 스트리밍하세요 |

## 자주 묻는 질문 (추가)

**Q: ZIP 아카이브에 비밀번호를 추가할 수 있나요?**  
A: 예. `Save`를 호출하기 전에 `archive.Password = "yourPassword";`를 설정합니다.

**Q: 특정 파일 유형만 포함하려면 어떻게 해야 하나요?**  
A: `CreateEntries`를 호출하기 전에 `GetFiles("*.txt")`와 같은 방식으로 `DirectoryInfo` 컬렉션을 필터링합니다.

**Q: 기존 ZIP을 다시 만들지 않고 업데이트할 방법이 있나요?**  
A: Aspose.Zip는 `Archive.UpdateEntry`를 통해 증분 업데이트를 지원합니다.

## FAQ

### Q1: Aspose.Zip for .NET를 상업 및 개인 프로젝트 모두에서 사용할 수 있나요?

A1: 예, Aspose.Zip for .NET는 상업 및 개인용 모두 라이선스가 허용됩니다.

### Q2: 무료 체험판이 있나요?

A2: 예, 무료 체험판을 [여기](https://releases.aspose.com/zip/net)에서 확인할 수 있습니다.

### Q3: Aspose.Zip for .NET에 대한 지원을 어떻게 받을 수 있나요?

A3: 커뮤니티 지원을 위해 [Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37)을 방문하거나 전용 지원을 위해 [임시 라이선스](https://purchase.aspose.com/temporary-license/) 구매를 고려하세요.

### Q4: 다른 예제와 튜토리얼이 있나요?

A4: 예, [문서](https://reference.aspose.com/zip/net/)에 포괄적인 예제와 튜토리얼이 포함되어 있습니다.

### Q5: Aspose.Zip for .NET를 구매할 수 있나요?

A5: 물론, [여기](https://purchase.aspose.com/buy)에서 구매하실 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

---