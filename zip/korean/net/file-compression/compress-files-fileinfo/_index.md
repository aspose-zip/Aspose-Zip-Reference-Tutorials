---
date: 2026-02-28
description: Aspose.Zip for .NET를 사용하여 폴더를 zip에 추가하고 파일을 zip에 추가하는 방법을 배웁니다. 이 단계별
  가이드는 ASP.NET 프로젝트에서 FileInfo를 사용하여 파일을 압축하는 방법을 보여줍니다.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET을 사용하여 폴더를 ZIP에 추가하는 방법 – FileInfo로 파일 압축
url: /ko/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET을 사용하여 폴더를 Zip에 추가하는 방법

## 소개

프로그램matically **zip 압축 파일을 생성**해야 할 경우, Aspose.Zip for .NET은 모든 .NET(ASP.NET 포함) 애플리케이션에서 작동하는 깔끔하고 고성능 API를 제공합니다. 이 튜토리얼에서는 `FileInfo` 클래스를 사용해 파일을 압축하는 과정을 단계별로 살펴보고, **zip에 파일을 추가**하는 방법을 보여주며, 이 접근 방식이 최신 .NET 프로젝트에 왜 이상적인지 설명합니다. 또한 **폴더를 zip에 추가**하는 방법도 다루어 한 번에 전체 디렉터리를 묶을 수 있습니다. 시작해 보겠습니다!

## 빠른 답변
- **zip 압축 파일을 가장 쉽게 만드는 방법은?** `Archive` 클래스와 `FileInfo` 객체를 함께 사용하세요.  
- **한 번에 여러 파일을 추가할 수 있나요?** 네 – 각 파일에 대해 `FileInfo`를 만들고 `CreateEntry`를 호출하면 됩니다.  
- **ASP.NET에 특별한 라이선스가 필요합니까?** 상용 Aspose.Zip 라이선스가 프로덕션에 필요합니다; 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API가 스레드‑안전한가요?** 각 스레드가 자체 `Archive` 인스턴스를 사용한다면 안전합니다.

## Zip 압축 파일이란? 그리고 왜 만들어야 할까요?
Zip 압축 파일은 하나 이상의 파일을 단일 압축 컨테이너에 묶는 방식입니다. 이를 통해 저장 공간을 절감하고 네트워크 전송 속도를 높이며 배포가 간편해집니다. 로그를 전달하거나 보고서를 내보내거나 클라이언트를 위한 에셋을 패키징하든, **프로그램matically zip 압축 파일을 만드는 방법**을 아는 것은 모든 .NET 개발자에게 유용한 스킬입니다.

## Aspose.Zip으로 파일을 Zip에 추가하는 이유
- **외부 종속성 제로** – 순수 .NET 구현.  
- **압축 수준 및 인코딩(ASCII, UTF‑8 등)에 대한 완전한 제어**.  
- **대용량 파일 지원** (> 4 GB) 및 비밀번호 보호.  
- **.NET Framework, .NET Core, .NET 5+ 전반에 걸친 일관된 API**.

## 사전 요구 사항

코드 작성을 시작하기 전에 다음을 준비하세요:

1. **Aspose.Zip for .NET**이 설치되어 있어야 합니다. 최신 패키지는 [Aspose.Zip 다운로드 페이지](https://releases.aspose.com/zip/net/)에서 받을 수 있습니다.  
2. 압축하려는 파일이 들어 있는 폴더가 필요합니다(예: `alice29.txt` 및 `fields.c`).  

## 네임스페이스 가져오기

zip 압축 파일을 다룰 C# 파일에 다음 `using` 문을 추가합니다:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

이 네임스페이스들을 통해 `Archive` 클래스, 저장 옵션, 표준 I/O 유틸리티에 접근할 수 있습니다.

## 단계별 가이드

### 단계 1: 문서 디렉터리 설정

먼저 소스 파일이 들어 있는 폴더를 정의합니다. 시스템에 맞는 절대 경로나 상대 경로로 플레이스홀더를 교체하세요:

```csharp
string dataDir = "Your Document Directory";
```

> **팁:** `Path.Combine`을 사용하면 플랫폼에 독립적인 경로를 만들 수 있습니다.

### 단계 2: 쓰기용 Zip 파일 열기

출력 zip 파일을 가리키는 `FileStream`을 생성합니다. 스트림은 **Create** 모드로 열리며, 동일한 이름의 기존 파일을 덮어씁니다:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 단계 3: 각 소스 파일에 대한 `FileInfo` 객체 준비

`FileInfo`는 Aspose.Zip이 디스크에 있는 실제 파일에 직접 접근하도록 해줍니다. 압축하려는 파일마다 하나씩 인스턴스를 만들세요:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **왜 `FileInfo`를 사용하나요?** 전체 파일을 메모리로 로드하지 않으므로, 특히 대용량 파일을 다룰 때 유리합니다.

### 단계 4: Archive 생성 및 엔트리 추가

`Archive` 객체를 인스턴스화한 뒤, 각 `FileInfo`에 대해 `CreateEntry`를 호출합니다. 첫 번째 인자는 zip 내부에서 파일이 가질 이름이고, 두 번째 인자는 원본 `FileInfo`입니다:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 단계 5: 원하는 인코딩으로 Zip 압축 파일 저장

마지막으로 앞서 연 `FileStream`에 아카이브를 저장합니다. 여기서는 엔트리 이름에 ASCII 인코딩을 사용했지만, 파일명이 비ASCII 문자일 경우 UTF‑8로 전환할 수 있습니다:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` 블록이 종료되면 스트림이 자동으로 닫히고 zip 파일이 사용 준비됩니다.

## Aspose.Zip을 사용하여 폴더를 Zip에 추가하는 방법

**폴더를 zip에 추가**해야 할 경우 절차는 간단합니다:

1. `DirectoryInfo.GetFiles`(재귀가 필요하면 `GetDirectories`도)로 폴더를 열거합니다.  
2. 발견된 각 파일에 대해 `FileInfo`를 생성합니다.  
3. 폴더 이름을 포함한 상대 경로(예: `"MyFolder/Report.pdf"`)와 함께 `CreateEntry`를 호출합니다.  

API가 `FileInfo`와 함께 작동하므로 전체 파일을 메모리로 로드할 필요가 없으며, 대용량 디렉터리에도 안전합니다. 이 기법은 **zip multiple files asp.net** 시나리오에서도 유용합니다—예를 들어, 실행 중에 보고서 세트를 생성하고 이를 단일 아카이브로 전달해야 할 때 활용할 수 있습니다.

## 일반적인 문제 및 해결책

| Issue | Cause | Fix |
|-------|-------|-----|
| **Empty zip file** | `FileInfo`가 존재하지 않는 경로를 가리킴 | `dataDir`와 파일명을 확인하고, `File.Exists`로 존재 여부를 체크하세요. |
| **Incorrect filename encoding** | 비ASCII 이름에 기본 인코딩 사용 | `ArchiveSaveOptions`에서 `Encoding = Encoding.UTF8`을 설정하세요. |
| **OutOfMemoryException on large files** | 파일을 전체 메모리로 로드 | `FileInfo`는 스트리밍을 사용합니다; 다른 곳에서 파일을 바이트 배열로 읽지 않도록 하세요. |
| **Permission denied** | 출력 폴더에 대한 쓰기 권한 부족 | 적절한 권한으로 실행하거나 쓰기 가능한 디렉터리를 선택하세요. |

## 자주 묻는 질문

**Q: zip 압축 파일에 비밀번호 보호를 추가할 수 있나요?**  
A: 가능합니다. `Archive`를 만든 뒤 `archive.Password = "yourPassword"`를 설정하고 `Save`를 호출하면 됩니다.

**Q: 기존 zip 파일을 업데이트할 수 있나요?**  
A: `Archive.Open`으로 기존 아카이브를 연 뒤 새 엔트리를 추가하면 됩니다.

**Q: ASP.NET MVC 컨트롤러에서 파일을 압축하려면 어떻게 해야 하나요?**  
A: 동일한 코드를 사용하면 되며, 출력 스트림을 `FileResult`로 반환하면 클라이언트에 전달됩니다.

**Q: Aspose.Zip이 지원하는 암호화 알고리즘은 무엇인가요?**  
A: 표준 ZipCrypto와 AES‑256 암호화를 지원합니다.

**Q: 폴더를 재귀적으로 압축하려면 어떻게 해야 하나요?**  
A: `Directory.GetFiles`와 하위 폴더를 순회하면서 각 파일에 대해 `FileInfo`를 만들고 아카이브에 추가하면 됩니다.

## 추가 FAQ

**Q: 대용량 데이터 세트를 위해 zip 압축 파일을 만들려면?**  
A: `FileInfo` 객체로 스트리밍하고 `ArchiveSaveOptions`에서 `CompressionLevel`을 설정해 최적의 성능을 얻으세요.

**Q: .NET Core 웹 API에서 Aspose.Zip을 사용할 수 있나요 (zip files asp.net core)?**  
A: 물론입니다 – 라이브러리는 .NET Core 3.1 이상과 완벽히 호환됩니다.

**Q: 커스텀 루프 없이 폴더를 zip에 추가할 방법이 있나요?**  
A: Aspose.Zip에 단일 “add folder” 메서드는 없지만, `DirectoryInfo`를 이용한 반복은 가볍고 엔트리 이름을 자유롭게 제어할 수 있습니다.

**Q: zip 압축 파일에 비밀번호 보호를 하면 압축 속도에 영향을 주나요?**  
A: 암호화를 활성화하면 약간의 오버헤드가 발생하지만, 대부분의 사용 사례에서는 영향이 미미합니다.

**Q: 상용 배포에 필요한 라이선스는?**  
A: 프로덕션에서는 유료 Aspose.Zip 라이선스가 필요합니다; 개발 및 테스트용으로는 무료 체험판을 사용할 수 있습니다.

## 기존 FAQ 섹션 (변경 없음)

### FAQ's

#### Q1: Aspose.Zip이 모든 파일 형식을 지원하나요?

A1: Aspose.Zip은 다양한 파일 형식을 지원하여 압축 작업의 범용성을 보장합니다.

#### Q2: Aspose.Zip을 상업 프로젝트에 사용할 수 있나요?

A2: 물론입니다! 라이선스 옵션은 [구매 페이지](https://purchase.aspose.com/buy)에서 확인하세요.

#### Q3: Aspose.Zip에 대한 지원을 받으려면 어떻게 해야 하나요?

A3: [Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37)에서 커뮤니티에 참여하면 도움을 받을 수 있습니다.

#### Q4: 무료 체험판이 있나요?

A4: 네, [여기서 무료 체험판을 받을 수 있습니다](https://releases.aspose.com/).

#### Q5: Aspose.Zip 임시 라이선스를 얻으려면?

A5: 임시 라이선스에 대한 정보는 [이 링크](https://purchase.aspose.com/temporary-license/)를 참고하세요.

## 결론

이제 **폴더를 zip에 추가**하고 **zip 압축 파일을 만드는** 방법, **파일을 zip에 추가**하는 방법, 그리고 이 방법이 ASP.NET 및 기타 .NET 애플리케이션에 왜 최적화된 방법인지 알게 되었습니다. 다양한 압축 수준, 인코딩, 암호화 옵션을 실험해 보면서 필요에 맞는 아카이브를 만들 수 있습니다. 즐거운 압축 작업 되세요!

---

**마지막 업데이트:** 2026-02-28  
**테스트 환경:** Aspose.Zip for .NET 24.12 (최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}