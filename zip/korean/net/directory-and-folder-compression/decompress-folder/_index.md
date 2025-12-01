---
date: 2025-12-01
description: Aspose.Zip for .NET를 사용하여 디렉터리를 zip 파일로 압축하고 zip 파일을 디렉터리로 추출하는 방법을 배우세요
  – zip 압축 .NET에 대한 완전한 가이드와 zip 아카이브 .NET 생성.
language: ko
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 디렉터리를 Zip으로 압축 및 압축 해제 – Aspose.Zip for .NET
url: /net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 디렉터리를 Zip으로 압축 및 압축 해제 – Aspose.Zip for .NET

.NET 애플리케이션에서 **compress directory to zip**을 수행하고 해당 아카이브를 추출해야 한다면, 올바른 곳에 오셨습니다. 이 튜토리얼에서는 전체 워크플로를 단계별로 안내합니다—zip 아카이브 생성부터 시작하여 Aspose.Zip for .NET을 사용한 깔끔한 단계별 압축 해제까지. 끝까지 진행하면 zip 압축 .NET 프로젝트에 재사용 가능한 패턴과 .NET 스타일 압축 해제에 대한 확실한 이해를 얻을 수 있습니다.

## 빠른 답변
- **“compress directory to zip”이 의미하는 바는 무엇인가요?** 폴더의 내용을 단일 .zip 파일로 변환하는 것을 의미합니다.  
- **zip을 디렉터리로 추출하려면 어떻게 하나요?** 가이드에 표시된 대로 `Archive.ExtractToDirectory` 메서드를 사용합니다.  
- **.NET 버전 중 지원되는 것은?** 모든 최신 .NET Framework, .NET Core 및 .NET 5/6+ 버전을 지원합니다.  
- **프로덕션에 라이선스가 필요합니까?** 예, 비시험용으로는 상업용 Aspose.Zip 라이선스가 필요합니다.  
- **CI/CD 파이프라인에서 자동화할 수 있나요?** 물론입니다—동일한 코드를 빌드 스크립트에 추가하면 됩니다.

## “compress directory to zip”이란 무엇인가요?
디렉터리를 zip으로 압축하면 모든 파일과 하위 폴더가 하나의 압축된 아카이브로 묶입니다. 이는 저장 용량을 줄이고 전송을 간소화하며, 배포용 리소스를 패키징하는 표준 방법입니다.

## 왜 Aspose.Zip for .NET를 사용하나요?
Aspose.Zip는 네이티브 종속성이 필요 없는 **pure‑managed** API를 제공하며, 대용량 파일을 지원하고 고성능 zip 압축 .NET 기능을 제공합니다. 또한 비밀번호로 보호된 아카이브와 유니코드 파일 이름과 같은 특수 상황도 기본적으로 처리합니다.

## 전제 조건
- **Aspose.Zip for .NET** 라이브러리가 설치되어 있어야 합니다 (여기서 다운로드하세요 [here](https://releases.aspose.com/zip/net/)).  
- 아카이브하려는 디스크상의 폴더 – `dataDir` 변수에 경로를 설정합니다.  
- .NET 개발 환경 (Visual Studio, VS Code, 또는 선호하는 IDE).

## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 범위에 가져옵니다:

```csharp
using Aspose.Zip;
using System.IO;
```

## 1단계: 디렉터리를 Zip으로 압축
나중에 압축 해제할 디렉터리에서 zip 파일을 생성합니다. `CompressDirectory.Run()` 헬퍼가 주요 작업을 수행합니다.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** `CompressDirectory` 샘플은 `dataDir`의 모든 파일을 `CompressDirectory_out.zip`에 압축합니다. 필요에 따라 출력 파일 이름을 원하는 명명 규칙에 맞게 변경해도 됩니다.

## 2단계: 폴더 압축 해제 (How to unzip .NET)

### 2.1단계: Zip 파일 열기
`FileStream`을 사용하여 생성된 아카이브를 엽니다. 이는 파일을 읽기 위해 준비하는 단계입니다.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### 2.2단계: Archive 인스턴스 생성
zip 컨테이너를 나타내는 `Archive` 객체를 인스턴스화합니다.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### 2.3단계: 디렉터리로 추출
마지막으로, 내용을 새 폴더로 추출합니다. 이것이 **extract zip to directory** 단계입니다.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

축하합니다! Aspose.Zip for .NET을 사용하여 **compressed a directory to zip**을 성공적으로 수행하고 **extracted the zip to a directory**을 완료했습니다. 이 접근 방식은 데이터 무결성을 보장하면서 코드를 간결하고 읽기 쉽게 유지합니다.

## 일반적인 문제 및 해결책
| 증상 | 가능한 원인 | 해결 방법 |
|------|------------|----------|
| `UnauthorizedAccessException` 발생 시 추출 | 대상 폴더가 읽기 전용이거나 사용 중 | 대상 경로가 쓰기 가능하고 잠겨 있지 않은지 확인하세요 |
| 추출 후 출력 폴더가 비어 있음 | 잘못된 소스 zip 경로 | `dataDir + "CompressDirectory_out.zip"`가 올바른 파일을 가리키는지 다시 확인하세요 |
| 대용량 파일으로 OutOfMemoryException 발생 | 매우 큰 아카이브에서 기본 버퍼 크기 사용 | `ArchiveOptions`를 사용해 버퍼 크기를 늘리거나 파일을 청크 단위로 스트리밍하세요 |

## 자주 묻는 질문

**Q: Aspose.Zip for .NET를 모든 종류의 파일에 사용할 수 있나요?**  
A: 예, Aspose.Zip는 텍스트, 바이너리, 이미지, PDF 등 모든 파일 유형을 지원합니다.

**Q: Aspose.Zip가 대규모 애플리케이션에 적합한가요?**  
A: 물론입니다. Aspose.Zip는 고성능 zip 압축 .NET 시나리오를 위해 설계되었으며, 멀티 기가바이트 아카이브를 낮은 메모리 오버헤드로 처리합니다.

**Q: Aspose.Zip for .NET에 대한 포괄적인 문서는 어디에서 찾을 수 있나요?**  
A: 자세한 문서는 [here](https://reference.aspose.com/zip/net/)에서 확인하세요.

**Q: 구매 전에 Aspose.Zip를 체험해볼 수 있나요?**  
A: 예, 무료 체험판은 [Aspose.Zip download page](https://releases.aspose.com/)에서 제공됩니다.

**Q: Aspose.Zip for .NET에 대한 지원을 어떻게 받을 수 있나요?**  
A: 커뮤니티 도움과 공식 지원을 위해 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)을 방문하세요.

---

**마지막 업데이트:** 2025-12-01  
**테스트 환경:** Aspose.Zip 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}