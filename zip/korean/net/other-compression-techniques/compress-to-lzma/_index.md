---
date: 2026-06-24
description: Aspose.Zip for .NET에서 LZMA를 압축하는 방법을 배우고, 저장소 및 데이터 전송 효율성을 최적화하세요.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Lzma로 압축
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET에서 LZMA 압축하는 방법
url: /ko/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET에서 LZMA 압축하는 방법

## 소개

이 튜토리얼에서는 Aspose.Zip for .NET에서 **LZMA 압축 방법**을 배우게 됩니다. 이는 저장 공간을 최적화하고 데이터 전송 효율성을 향상시키는 중요한 기술입니다. LZMA(레펨‑지브‑마코프 체인 알고리즘)는 전통적인 ZIP에 비해 최대 70 % 더 작은 압축 파일을 제공하면서 빠른 압축 해제를 유지하므로 대역폭이 제한된 상황에 이상적입니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Zip for .NET  
- **이 가이드에서 다루는 알고리즘은?** LZMA 압축  
- **라이선스가 필요합니까?** 테스트에는 임시 라이선스로 충분하며, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, 그리고 .NET 5–10  
- **구현에 걸리는 시간은?** 기본 파일의 경우 일반적으로 10분 미만입니다.

## LZMA 압축이란?

LZMA는 사전 압축과 레인지 인코딩을 활용하는 고비율 무손실 압축 알고리즘입니다. 텍스트 파일을 30‑70 % 정도 압축하면서도 ZIP에 필적하는 압축 해제 속도를 유지합니다. 대용량 데이터 세트에서는 저장 비용을 절감하고 네트워크 전송 속도를 높이며 데이터 무결성을 유지합니다.

## 왜 Aspose.Zip을 사용해 LZMA를 압축하나요?

Aspose.Zip은 **5가지 압축 알고리즘**(ZIP, Deflate, BZIP2, LZMA, ZSTD)을 지원하며 전체 파일을 메모리에 로드하지 않고도 **4 GB**까지의 압축 파일을 처리할 수 있습니다. 일반 서버에서 수백 페이지 문서를 **2 초** 미만에 처리하여 성능과 확장성을 동시에 제공합니다.

## 전제 조건

시작하기 전에 다음 항목을 확인하십시오:

- Aspose.Zip for .NET: Aspose.Zip 라이브러리가 설치되어 있는지 확인하십시오. 문서는 [여기](https://reference.aspose.com/zip/net/)에서 찾을 수 있습니다.
- 문서 디렉터리: 압축하려는 파일이 들어 있는 폴더를 선택하거나 생성하십시오.

## 네임스페이스 가져오기

C# 파일 상단에 필요한 네임스페이스를 추가하여 Aspose.Zip의 LZMA 기능에 접근할 수 있습니다:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## 압축을 위한 소스 폴더를 어떻게 설정하나요?

압축하려는 파일이 들어 있는 폴더를 지정하십시오. 전용 소스 디렉터리를 사용하면 의도한 파일만 처리되고, 원치 않는 데이터가 포함될 위험이 줄어들며, 여러 압축 작업을 동시에 수행할 때 경로 관리가 간편해집니다.

```csharp
string dataDir = "Your Document Directory";
```

## LZMA를 사용해 파일을 어떻게 압축하나요?

`LzmaArchive`는 Aspose.Zip에서 LZMA 압축 파일을 생성하고 관리하는 클래스입니다.

`LzmaArchive` 인스턴스를 만들고, 소스 파일을 지정한 뒤 `Save`를 호출하면 `.lzma` 압축 파일이 생성됩니다. 이 두 줄의 패턴은 전체 압축 흐름을 수행하며, 스트림 관리를 내부에서 처리하고 배포 또는 저장에 적합한 압축 파일을 만들어 줍니다.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## 압축이 성공했는지 어떻게 확인하나요?

`Console.WriteLine`은 표준 출력 콘솔에 텍스트 라인을 출력합니다.

압축 파일이 저장된 후 `Console.WriteLine`을 사용해 간단한 확인 메시지를 출력하십시오. 즉시 피드백을 제공함으로써 개발자는 압축 단계가 오류 없이 완료되었는지 확인할 수 있고, 자동 빌드 시 디버깅을 단순화하며, 더 큰 애플리케이션이나 스크립트에 통합될 때 명확한 상태 정보를 제공합니다.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## 일반적인 문제 및 해결책

- **파일을 찾을 수 없음** – 경로 문자열에 이중 역슬래시(`\\`) 또는 verbatim 문자열(`@"C:\Path"`)이 사용되었는지 확인하십시오.  
- **메모리 부족** – Aspose.Zip은 데이터를 스트리밍하지만, 매우 큰 파일의 경우 프로세스 메모리 제한을 늘려야 할 수 있습니다.  
- **라이선스가 적용되지 않음** – Aspose.Zip 작업을 수행하기 전에 `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` 코드를 호출했는지 확인하십시오.

## 자주 묻는 질문

**Q: 여러 파일을 하나의 LZMA 압축 파일로 압축할 수 있나요?**  
A: 가능합니다. `archive.Save()`를 호출하기 전에 각 파일에 대해 `archive.AddFile()`을 호출하십시오.

**Q: LZMA 압축 수준을 설정할 방법이 있나요?**  
A: `LzmaArchive` 클래스는 기본 압축 수준을 사용하며, 이는 속도와 크기 사이의 좋은 균형을 제공합니다. 세밀한 제어가 필요하면 `LzmaEncoder`를 통해 고급 설정을 사용할 수 있습니다.

**Q: 생성된 .lzma 파일이 비 Windows 플랫폼에서도 작동하나요?**  
A: 물론입니다. LZMA 형식은 플랫폼에 구애받지 않으므로 LZMA 호환 도구가 있는 모든 OS에서 압축을 해제할 수 있습니다.

**Q: Aspose.Zip을 사용해 LZMA 압축 파일을 어떻게 해제하나요?**  
A: 압축 파일 경로를 인자로 `LzmaArchive` 생성자를 사용하고, `ExtractToDirectory()`를 호출하여 내용을 추출하십시오.

**Q: 전체 파일을 메모리에 로드하지 않고 스트리밍 압축을 지원하나요?**  
A: 지원합니다. `SetSource()`와 `Save()` 메서드에 `Stream` 객체를 전달하여 스트림으로 작업할 수 있습니다.

**마지막 업데이트:** 2026-06-24  
**테스트 환경:** Aspose.Zip for .NET (작성 시 최신 버전)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Zip for .NET으로 파일 압축하는 방법](/zip/net/file-compression/compress-file/)
- [Aspose.Zip for .NET으로 GZip 압축 파일 및 기타 압축 기술 열기](/zip/net/other-compression-techniques/)
- [compress files c# – Aspose.Zip for .NET으로 7z 압축 파일 만들기](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}