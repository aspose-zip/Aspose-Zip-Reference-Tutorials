---
date: 2026-05-30
description: Aspose.Zip for .NET를 사용하여 .NET에서 압축 없이 zip을 만드는 방법을 배워보세요. 이 가이드는 압축
  없이 파일을 zip하는 방법, 파일을 압축되지 않은 상태로 저장하는 방법, 그리고 아카이브를 효율적으로 관리하는 방법을 보여줍니다.
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: 압축 없이 여러 파일 저장하기
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: .NET에서 Aspose.Zip을 사용하여 압축 없이 zip 만들기
url: /ko/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip을 사용한 .NET에서 압축 없이 ZIP 만들기

현대 .NET 개발에서 **압축 없이 ZIP 만들기**는 압축 속도를 크게 향상시키고 파일 크기를 예측 가능하게 유지할 수 있습니다. 규제 규칙을 충족하거나, 다운스트림 처리 속도를 높이거나, 원본 바이트 시퀀스가 그대로 유지되는 것을 보장해야 할 경우, **압축 없이 파일을 ZIP**해야 할 경우, Aspose.Zip for .NET은 깔끔하고 직관적인 API를 제공합니다. 이 튜토리얼에서는 압축되지 않은 ZIP 아카이브를 만드는 정확한 단계, 파일 추가 방법 및 솔루션을 애플리케이션에 통합하는 방법을 안내합니다.

## 빠른 답변
- **“uncompressed zip”이란 무엇을 의미합니까?** 원본 파일 바이트를 그대로 두고 “store” 방식을 사용해 각 항목을 저장하는 ZIP 아카이브입니다.  
- **왜 압축을 피합니까?** 아카이브 속도를 높이고, 다운스트림 처리에 원본 파일 크기를 유지하거나, 데이터 변경을 금지하는 규제 요구사항을 충족하기 위해서입니다.  
- **어떤 Aspose.Zip 클래스가 이를 처리합니까?** `ArchiveEntrySettings`와 `StoreCompressionSettings`를 결합합니다.  
- **라이선스가 필요합니까?** 테스트용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, 그리고 .NET 5–10.  

## 압축 없이 ZIP이란 무엇인가요?
**압축 없이 ZIP**은 각 파일 항목이 *store* 방식을 사용하여 데이터를 압축 알고리즘 없이 그대로 아카이브에 복사하는 ZIP 아카이브입니다. 이 경우 아카이브 크기는 원본 파일들의 합계에 ZIP 오버헤드 몇 바이트를 더한 것과 같습니다.

## 압축 없이 ZIP 파일에 Aspose.Zip을 사용하는 이유는?
Aspose.Zip은 고성능 아카이빙을 위해 최적화되어 있어 압축 알고리즘의 오버헤드 없이 파일을 즉시 저장할 수 있습니다. 전체 ZIP 호환성을 보장하고, 저장된 항목과 압축된 항목을 혼합할 수 있으며, 저수준 ZIP 구조를 추상화하는 간단한 API를 제공하여 구현을 빠르고 안정적으로 만들 수 있습니다.

## 전제 조건
- **Aspose.Zip for .NET** – 프로젝트에 통합됩니다. 설치 단계는 공식 [문서](https://reference.aspose.com/zip/net/)를 참조하십시오.  
- **.NET 개발 환경** – Visual Studio, VS Code 또는 선호하는 IDE.  
- **문서 디렉터리** – 아카이브하려는 파일이 들어 있는 폴더(예: “Your Document Directory”).

## 네임스페이스 가져오기
코드를 작성하기 전에 필요한 네임스페이스를 가져와야 컴파일러가 Aspose 클래스를 찾을 수 있습니다.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 단계 1: 문서 디렉터리 설정
소스 파일이 위치한 경로를 정의합니다. 자리표자를 시스템에 실제 폴더 경로로 교체하십시오.

```csharp
string dataDir = "Your Document Directory";
```

## 단계 2: 압축 없이 ZIP 아카이브 만들기
튜토리얼의 핵심 – `StoreCompressionSettings`로 구성된 `Archive` 인스턴스를 생성합니다. `Archive`는 여러 항목을 보유할 수 있는 ZIP 컨테이너를 나타냅니다. `StoreCompressionSettings`는 항목을 압축 없이 저장하도록 지정합니다. 이는 Aspose.Zip에게 각 항목을 *저장* (즉, 압축하지 않음)하도록 지시합니다.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **팁:** 일부 파일은 압축하고 다른 파일은 압축하지 않고 **ZIP에 파일을 저장**해야 하는 경우, 각 파일에 대해 별도의 `ArchiveEntrySettings` 인스턴스를 생성하고 동일한 `Archive`에 추가하십시오.

## .NET에서 압축 없이 ZIP을 만드는 방법은?
소스 파일을 로드하고 `Archive` 객체를 인스턴스화한 뒤 `new StoreCompressionSettings()`와 함께 `ArchiveEntrySettings`를 사용해 각 파일을 추가합니다. 전체 작업은 코드 3줄만 필요하며 전체 파일 크기에 비례하는 선형 시간에 실행되어 가장 빠른 아카이빙 경험을 제공합니다.

### 단계별 진행
1. **아카이브 생성** – 대상 스트림 또는 파일 경로로 `Archive`를 인스턴스화합니다.  
2. **항목 설정 구성** – 각 파일에 대해 `ArchiveEntrySettings` 객체를 생성하고 `Compression` 속성에 `new StoreCompressionSettings()`를 할당합니다.  
3. **항목 추가** – 모든 파일에 대해 `archive.Add(entrySettings)`를 호출하고, 마지막에 `archive.Save()`로 완료합니다.

## 일반적인 문제 및 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|----------|----------|
| **파일을 찾을 수 없음** | `dataDir` 경로가 잘못되었거나 파일 확장자가 누락되었습니다. | 경로를 확인하고 파일이 존재하는지 확인하십시오. 보다 안전한 결합을 위해 `Path.Combine`을 사용하십시오. |
| **액세스 거부** | 프로세스에 소스 파일을 읽거나 ZIP을 쓸 권한이 없습니다. | 적절한 권한으로 애플리케이션을 실행하거나 쓰기 권한이 있는 폴더를 선택하십시오. |
| **ZIP에서 예상치 못한 파일 크기** | 아카이브가 기본 압축으로 생성되었습니다. | `ArchiveEntrySettings`에 `new StoreCompressionSettings()`가 전달되었는지 확인하십시오. |

## 자주 묻는 질문

**Q: 특정 파일 유형은 압축하고 다른 파일은 압축 없이 저장할 수 있나요?**  
A: 예, 각 파일에 대해 다른 `ArchiveEntrySettings`를 생성하고 동일한 아카이브에 압축된 항목과 압축되지 않은 항목을 혼합할 수 있습니다.

**Q: Aspose.Zip for .NET은 .NET Core 및 .NET 5/6과 호환됩니까?**  
A: 물론입니다. 이 라이브러리는 .NET Framework, .NET Core, .NET Standard 및 최신 .NET 버전을 지원합니다.

**Q: 아카이빙 과정에서 예외를 어떻게 처리해야 하나요?**  
A: 아카이빙 코드를 `try‑catch` 블록으로 감싸고 예외 세부 정보를 로그에 기록하십시오. 이렇게 하면 정상적인 실패 처리와 디버깅이 쉬워집니다.

**Q: Aspose.Zip은 다중 스레드 아카이빙을 지원합니까?**  
A: 예, 여러 파일을 병렬로 처리하여 아카이브에 추가할 수 있지만, `Archive` 객체 자체는 스레드 안전하지 않으므로 항목을 추가할 때 접근을 동기화해야 합니다.

**Q: 기존 프로젝트에 Aspose.Zip을 큰 코드 변경 없이 통합할 수 있나요?**  
A: 확실히 가능합니다. API는 간단히 삽입하여 사용할 수 있도록 설계되었습니다. 마이그레이션 가이드는 공식 [문서](https://reference.aspose.com/zip/net/)를 참고하십시오.

**마지막 업데이트:** 2026-05-30  
**테스트 환경:** Aspose.Zip for .NET (latest version at time of writing)  
**작성자:** Aspose

## 관련 튜토리얼

- [ZIP 아카이브 만들기 .NET – Aspose.Zip을 사용한 파일 압축](/zip/net/file-compression/)
- [여러 파일 zip c# – Aspose.Zip for .NET을 사용한 손쉬운 압축](/zip/net/file-compression/compress-multiple-files/)
- [압축 없이 ZIP 만들기 및 파일 압축 해제 – Aspose.Zip](/zip/net/file-decompression/decompress-stored-file/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}