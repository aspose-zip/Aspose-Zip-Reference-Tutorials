---
date: 2026-07-18
description: Aspose.Zip for .NET를 사용하여 폴더를 Zip에 추가하고 파일을 Zip에 추가하는 방법을 배웁니다. 이 단계별
  가이드는 ASP.NET 프로젝트에서 FileInfo로 파일을 압축하는 방법을 보여줍니다.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: FileInfo를 사용한 파일 압축
og_description: Aspose.Zip for .NET를 사용하여 폴더를 Zip에 추가합니다. Zip 아카이브 생성, 파일을 Zip에 추가,
  그리고 ASP.NET에서 폴더를 효율적으로 압축하는 방법을 배웁니다.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: 폴더를 Zip에 추가 – Aspose.Zip for .NET로 파일 압축
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Aspose.Zip for .NET를 사용하여 폴더를 Zip에 추가 – FileInfo로 파일 압축
url: /ko/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET을 사용하여 폴더를 Zip에 추가하기

## 소개

프로그램matically **add folder to zip** 해야 할 경우, Aspose.Zip for .NET은 모든 .NET(ASP.NET 포함) 애플리케이션에서 작동하는 깔끔하고 고성능의 API를 제공합니다. 이 튜토리얼에서는 `FileInfo` 클래스를 사용해 파일을 압축하는 방법을 살펴보고, **add files to zip** 하는 방법을 보여드리며, 이 접근 방식이 최신 .NET 프로젝트에 왜 이상적인지 설명합니다. 또한 **add folder to zip** 하는 정확한 단계도 다루어 전체 디렉터리를 한 번에 번들링할 수 있게 합니다. 시작해볼까요!

## 빠른 답변
- **가장 쉬운 zip 아카이브 생성 방법은?** Aspose.Zip의 `Archive` 클래스를 `FileInfo` 객체와 함께 사용하세요.  
- **한 번에 여러 파일을 추가할 수 있나요?** 네 – 각 파일마다 `FileInfo`를 만들고 `CreateEntry`를 호출하면 됩니다.  
- **ASP.NET에 특별한 라이선스가 필요합니까?** 프로덕션에서는 상용 Aspose.Zip 라이선스가 필요하고, 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **지원되는 .NET 버전은?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, 그리고 .NET 5–10.  
- **API가 스레드‑안전합니까?** 네, 각 스레드가 자체 `Archive` 인스턴스를 사용하면 안전합니다.

## Zip 아카이브란 무엇이며 왜 생성해야 할까요?
Zip 아카이브는 하나 이상의 파일을 단일 압축 컨테이너에 묶는 방식입니다. 이를 통해 저장 공간을 절감하고, 네트워크 전송 속도를 높이며, 배포를 단순화할 수 있습니다. 로그를 전달하거나 보고서를 내보내거나 클라이언트를 위한 자산을 패키징하든, 프로그램matically **how to create zip archive** 파일을 만드는 기술은 모든 .NET 개발자에게 유용한 스킬입니다.

## 파일을 Zip에 추가하기 위해 Aspose.Zip을 사용하는 이유
Aspose.Zip은 외부 종속성을 제거하면서 압축, 인코딩, 보안에 대한 세밀한 제어를 제공하는 순수 .NET 솔루션입니다. 대용량 파일, 비밀번호 보호를 지원하고 모든 지원 .NET 버전에서 일관되게 동작하므로 레거시와 최신 애플리케이션 모두에 신뢰할 수 있는 선택입니다.  

- **외부 종속성 전혀 없음** – 순수 .NET 구현.  
- **압축 수준 및 인코딩에 대한 완전한 제어** (ASCII, UTF‑8 등).  
- **4 GB 초과 파일 및 비밀번호 보호 지원**.  
- **50개 이상의 .NET 버전에서 일관된 API** – .NET Framework 2.0부터 .NET 10까지.

## 사전 요구 사항

코드에 들어가기 전에 다음을 확인하세요:

1. **Aspose.Zip for .NET**이 설치되어 있어야 합니다. 최신 패키지는 [Aspose.Zip 다운로드 페이지](https://releases.aspose.com/zip/net/)에서 다운로드하세요.  
2. 압축하려는 파일이 들어 있는 폴더가 있어야 합니다(예: `alice29.txt` 및 `fields.c`).  

## 네임스페이스 가져오기

Zip 아카이브와 작업할 C# 파일에 다음 `using` 문을 추가합니다:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

이 네임스페이스들을 통해 `Archive` 클래스, 저장 옵션 및 표준 I/O 유틸리티에 접근할 수 있습니다.

## 단계별 가이드

### 단계 1: 문서 디렉터리 설정

먼저 소스 파일이 들어 있는 폴더를 정의합니다. 시스템에 맞는 절대 경로나 상대 경로로 플레이스홀더를 교체하세요:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** `Path.Combine`을 사용하면 크로스‑플랫폼 방식으로 경로를 구성할 수 있습니다.

### 단계 2: 쓰기용 Zip 파일 열기

출력 zip 파일을 가리키는 `FileStream`을 생성합니다. 스트림은 **Create** 모드로 열리며, 동일한 이름의 기존 파일을 덮어씁니다:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 단계 3: 각 소스 파일에 대한 `FileInfo` 객체 준비

`FileInfo`는 Aspose.Zip이 디스크에 있는 물리 파일에 직접 접근하도록 해줍니다. 압축하려는 파일마다 인스턴스를 하나씩 생성하세요:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** 전체 파일을 메모리로 로드하지 않으므로 대용량 파일을 다룰 때 특히 유용합니다.

### 단계 4: 아카이브 생성 및 엔트리 추가

`Archive` 클래스는 메모리 내에서 zip 컨테이너를 나타내는 Aspose.Zip의 핵심 객체입니다. `Archive` 객체를 인스턴스화한 뒤 각 `FileInfo`에 대해 `CreateEntry`를 호출합니다. 첫 번째 인자는 zip 내부에 저장될 파일 이름이며, 두 번째 인자는 원본 `FileInfo`입니다:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

`CreateEntry` 메서드는 새 파일 엔트리를 아카이브에 추가하고, 엔트리 이름을 원본 `FileInfo`와 연결하여 저장 시 디스크에서 직접 스트리밍됩니다.

### 단계 5: 원하는 인코딩으로 Zip 아카이브 저장

마지막으로 앞서 연 `FileStream`에 아카이브를 저장합니다. 여기서는 엔트리 이름에 ASCII 인코딩을 사용하지만, 파일명이 비ASCII 문자일 경우 UTF‑8로 전환할 수 있습니다:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

`using` 블록이 종료되면 스트림이 자동으로 닫히고 zip 파일이 사용 준비됩니다.

## Aspose.Zip을 사용하여 폴더를 Zip에 추가하는 방법

대상 디렉터리를 로드하고 모든 파일을 열거한 뒤, 폴더 이름을 포함한 상대 경로로 각각 추가합니다. 이 방법을 사용하면 **add folder to zip** 을 수동으로 파일을 일일이 나열하지 않아도 됩니다. 엔트리 이름에 폴더 구조를 보존하면 압축 해제 시 원본 디렉터리 구조가 그대로 유지되어 배포 시 매우 유용합니다.

1. `DirectoryInfo`를 사용해 압축하려는 폴더를 지정합니다.  
2. `GetFiles("*", SearchOption.AllDirectories)`를 호출해 모든 파일을 재귀적으로 가져옵니다.  
3. 각 파일에 대해 `FileInfo`를 만들고 `"MyFolder/Report.pdf"`와 같은 경로로 `CreateEntry`를 호출합니다.  

API가 `FileInfo`와 함께 작동하므로 파일을 직접 디스크에서 스트리밍하여 수백 메가바이트 규모의 폴더도 메모리 사용량을 낮게 유지합니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결책 |
|------|------|--------|
| **Empty zip file** | `FileInfo`가 존재하지 않는 경로를 가리킴 | `dataDir` 및 파일 이름을 확인하고, 엔트리를 만들기 전에 `File.Exists`로 존재 여부를 검사하세요. |
| **Incorrect filename encoding** | 비ASCII 이름에 기본 인코딩 사용 | `ArchiveSaveOptions`에서 `Encoding = Encoding.UTF8`로 설정하세요. |
| **OutOfMemoryException on large files** | 파일 전체를 메모리로 로드 | `FileInfo`가 파일을 스트리밍하도록 하고, 다른 곳에서 파일을 바이트 배열로 읽지 않도록 하세요. |
| **Permission denied** | 출력 폴더에 대한 쓰기 권한 부족 | 적절한 권한으로 앱을 실행하거나 쓰기 가능한 디렉터리를 선택하세요. |

## 자주 묻는 질문

**Q: 단일 호출로 전체 폴더를 zip 아카이브에 추가할 수 있나요?**  
A: 단일 호출 메서드는 없지만, `DirectoryInfo`로 파일을 열거하고 각각 `CreateEntry`로 추가하면 동일한 결과를 효율적으로 얻을 수 있습니다.

**Q: Aspose.Zip이 비밀번호 보호를 지원하나요?**  
A: 네, 저장하기 전에 `Archive` 객체에 비밀번호를 설정하면 전체 아카이브가 암호화됩니다.

**Q: Aspose.Zip이 처리할 수 있는 zip 파일 크기는 얼마나 큰가요?**  
A: 라이브러리는 4 GB를 초과하는 파일을 처리하며, 전체 아카이브를 메모리에 로드하지 않고도 10 GB 이상을 생성할 수 있습니다.

**Q: API가 .NET 6 및 .NET 8과 호환되나요?**  
A: 물론입니다. Aspose.Zip은 .NET 5부터 .NET 10까지 지원하므로 현재 모든 LTS 릴리스를 포괄합니다.

**Q: 어떤 압축 수준을 선택할 수 있나요?**  
A: `CompressionLevel.NoCompression`, `Fast`, `Normal`, `Maximum` 중에서 선택해 속도와 크기 사이의 균형을 맞출 수 있습니다.

## 추가 자료

- 최신 Aspose.Zip 패키지 다운로드: [Aspose.Zip 다운로드 페이지](https://releases.aspose.com/zip/net/)  
- 프로덕션 사용을 위한 라이선스 구매: [구매 페이지](https://purchase.aspose.com/buy)  
- 커뮤니티에서 도움 받기: [Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37)  
- 무료 체험판 사용: [무료 체험 여기](https://releases.aspose.com/)  
- 평가용 임시 라이선스 획득: [이 링크](https://purchase.aspose.com/temporary-license/)  

## 결론

이제 Aspose.Zip for .NET을 사용해 **add folder to zip** 및 **how to create zip archive** 파일을 만드는 방법, **add files to zip** 하는 방법, 그리고 이 방법이 ASP.NET 및 기타 .NET 애플리케이션에 왜 이상적인지 알게 되었습니다. 다양한 압축 수준, 인코딩, 암호화 옵션을 실험해 보면서 필요에 맞게 아카이브를 맞춤 설정해 보세요. 즐거운 압축 작업 되시길!

---

**마지막 업데이트:** 2026-07-18  
**테스트 환경:** Aspose.Zip for .NET 24.12 (latest)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Zip for .NET을 사용하여 폴더 압축하기](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Aspose.Zip for .NET으로 손쉽게 압축](/zip/net/file-compression/compress-multiple-files/)
- [Create Zip Archive .NET – Aspose.Zip으로 파일 압축](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}