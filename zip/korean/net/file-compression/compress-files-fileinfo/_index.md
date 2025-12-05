---
date: 2025-12-05
description: Aspose.Zip for .NET를 사용하여 zip 아카이브를 만들고 파일을 zip에 추가하는 방법을 배웁니다. 이 단계별
  가이드는 ASP.NET 프로젝트에서 FileInfo를 사용해 파일을 압축하는 방법을 보여줍니다.
language: ko
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET을 사용하여 Zip 아카이브 만들기 – FileInfo로 파일 압축
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET을 사용하여 Zip 아카이브 만드는 방법

## 소개

프로그램matically **zip 아카이브를 생성**해야 할 경우, Aspose.Zip for .NET은 모든 .NET(ASP.NET 포함) 애플리케이션에서 작동하는 깔끔하고 고성능 API를 제공합니다. 이 튜토리얼에서는 `FileInfo` 클래스를 사용해 파일을 압축하는 방법을 단계별로 살펴보고, **파일을 zip에 추가**하는 방법을 보여주며, 이 접근 방식이 최신 .NET 프로젝트에 왜 이상적인지 설명합니다. 시작해볼까요!

## 빠른 답변
- **zip 아카이브를 만드는 가장 쉬운 방법은?** `FileInfo` 객체와 함께 Aspose.Zip의 `Archive` 클래스를 사용하세요.  
- **한 번에 여러 파일을 추가할 수 있나요?** 네 – 각 파일에 대해 `FileInfo`를 만들고 `CreateEntry`를 호출하면 됩니다.  
- **ASP.NET용 특별 라이선스가 필요합니까?** 상용 Aspose.Zip 라이선스가 프로덕션에 필요합니다; 평가용 무료 체험판도 사용할 수 있습니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API가 스레드‑안전한가요?** 각 스레드가 자체 `Archive` 인스턴스를 사용한다면 안전합니다.

## Zip 아카이브란 무엇이며 왜 만들어야 할까요?
Zip 아카이브는 하나 이상의 파일을 단일 압축 컨테이너에 묶는 방식입니다. 이를 통해 저장 공간을 절감하고, 네트워크 전송 속도를 높이며, 배포를 단순화할 수 있습니다. 로그를 전달하거나 보고서를 내보내거나 클라이언트를 위한 에셋을 패키징하든, **프로그램matically zip 아카이브 파일을 만드는 방법**을 아는 것은 모든 .NET 개발자에게 유용한 스킬입니다.

## Aspose.Zip을 사용해 파일을 Zip에 추가하는 이유
- **외부 종속성 전혀 없음** – 순수 .NET 구현.  
- **압축 수준 및 인코딩에 대한 완전한 제어** (ASCII, UTF‑8 등).  
- **대용량 파일 지원** (> 4 GB) 및 비밀번호 보호.  
- **.NET Framework, .NET Core, .NET 5+ 전반에 걸친 일관된 API**.

## 사전 요구 사항

코드를 살펴보기 전에 다음을 준비하세요:

1. **Aspose.Zip for .NET**이 설치되어 있어야 합니다. 최신 패키지는 [Aspose.Zip 다운로드 페이지](https://releases.aspose.com/zip/net/)에서 받으세요.  
2. 압축하려는 파일이 들어 있는 폴더가 필요합니다(예: `alice29.txt`와 `fields.c`).  

## 네임스페이스 가져오기

zip 아카이브를 다룰 C# 파일에 다음 `using` 문을 추가합니다:

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

> **팁:** `Path.Combine`을 사용하면 플랫폼에 관계없이 경로를 안전하게 만들 수 있습니다.

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

> **왜 `FileInfo`를 사용하나요?** 전체 파일을 메모리로 로드하지 않으므로 대용량 파일을 다룰 때 특히 유용합니다.

### 단계 4: 아카이브 생성 및 엔트리 추가

`Archive` 객체를 인스턴스화한 뒤, 각 `FileInfo`에 대해 `CreateEntry`를 호출합니다. 첫 번째 인자는 zip 내부에서 파일이 가질 이름이고, 두 번째 인자는 원본 `FileInfo`입니다:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 단계 5: 원하는 인코딩으로 Zip 아카이브 저장

마지막으로 앞서 연 `FileStream`에 아카이브를 저장합니다. 여기서는 엔트리 이름에 ASCII 인코딩을 사용했지만, 파일명이 비 ASCII 문자일 경우 UTF‑8로 전환할 수 있습니다:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` 블록이 종료되면 스트림이 자동으로 닫히고 zip 파일이 사용 준비됩니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| **빈 zip 파일** | `FileInfo`가 존재하지 않는 경로를 가리킴 | `dataDir`와 파일명을 확인하고, `File.Exists`로 존재 여부를 체크하세요. |
| **잘못된 파일명 인코딩** | 비 ASCII 이름에 기본 인코딩 사용 | `ArchiveSaveOptions`에서 `Encoding = Encoding.UTF8`으로 설정하세요. |
| **대용량 파일에서 OutOfMemoryException** | 파일 전체를 메모리로 로드 | `FileInfo`는 스트리밍을 사용합니다; 다른 곳에서 바이트 배열로 읽지 않도록 하세요. |
| **권한 거부** | 출력 폴더에 쓰기 권한이 없음 | 적절한 권한으로 실행하거나 쓰기 가능한 디렉터리를 선택하세요. |

## 자주 묻는 질문

**Q: zip 아카이브에 비밀번호 보호를 추가할 수 있나요?**  
A: 가능합니다. `Archive`를 만든 뒤 `archive.Password = "yourPassword"`를 설정하고 `Save`를 호출하면 됩니다.

**Q: 기존 zip 파일을 업데이트할 수 있나요?**  
A: 네. `Archive.Open`으로 기존 아카이브를 연 뒤 새로운 엔트리를 추가할 수 있습니다.

**Q: ASP.NET MVC 컨트롤러에서 파일을 압축하려면 어떻게 해야 하나요?**  
A: 동일한 코드를 사용하면 됩니다. 단, 출력 스트림을 `FileResult`로 클라이언트에 반환하도록 하면 됩니다.

**Q: Aspose.Zip이 지원하는 암호화 알고리즘은 무엇인가요?**  
A: 표준 ZipCrypto와 AES‑256 암호화를 지원합니다.

**Q: 폴더를 재귀적으로 압축하려면 어떻게 해야 하나요?**  
A: `Directory.GetFiles`(및 하위 폴더)를 순회하면서 각 파일에 대해 `FileInfo`를 만들고 아카이브에 추가하면 됩니다.

## 기존 FAQ 섹션 (변경 없음)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## 결론

이제 **Aspose.Zip for .NET을 사용해 zip 아카이브 파일을 만드는 방법**, **파일을 zip에 추가하는 방법**, 그리고 이 방법이 ASP.NET 및 기타 .NET 애플리케이션에 왜 최적화된 방법인지 알게 되었습니다. 다양한 압축 수준, 인코딩, 암호화 옵션을 실험해 보면서 필요에 맞는 아카이브를 만들어 보세요. 즐거운 압축 작업 되시길!

---

**마지막 업데이트:** 2025-12-05  
**테스트 환경:** Aspose.Zip for .NET 24.12 (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}