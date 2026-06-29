---
date: 2026-06-29
description: Aspose.Zip for .NET를 사용하여 폴더를 7z로 압축하는 방법을 배우세요. LZMA2, BZip2, Store와
  같은 Seven Zip 압축 방식을 다룹니다. 프로그래밍으로 7z 아카이브를 생성하는 데 적합합니다.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: 다양한 압축 방식을 지원하는 SevenZip
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 폴더를 7z로 압축하는 방법 – Aspose.Zip for .NET 튜토리얼
url: /ko/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 폴더를 7z로 압축하는 방법 – Aspose.Zip for .NET 튜토리얼

## 소개

.NET 애플리케이션에서 프로그래밍 방식으로 **compress folder to 7z** 아카이브를 만들어야 한다면, 올바른 곳에 오셨습니다. Aspose.Zip for .NET은 지원되는 압축 알고리즘 중 어느 것이든 Seven Zip 아카이브를 손쉽게 생성할 수 있게 해줍니다. 전체 디렉터리를 배포용으로 묶거나 신뢰할 수 있는 **seven zip archive .net** 솔루션이 필요할 때도 마찬가지입니다. 이 가이드에서는 LZMA2, BZip2, Store(압축 없음)라는 세 가지 인기 압축 방식을 살펴보고, C# 코드 몇 줄만으로 7z 파일을 만드는 방법을 정확히 보여드립니다.

## 빠른 답변
- **어떤 라이브러리를 사용해야 하나요?** Aspose.Zip for .NET은 가장 완전한 Seven Zip 기능 세트를 제공합니다.  
- **어떤 압축 방법이 가장 높은 압축률을 제공하나요?** LZMA2는 일반적으로 혼합 데이터에 대해 가장 높은 압축을 제공합니다.  
- **압축 없이 7z를 만들 수 있나요?** 예—Store(압축 없음) 방법을 사용하세요.  
- **개발에 라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 프로덕션 사용에는 라이선스가 필요합니다.  
- **.NET 6/7과 호환됩니까?** 물론입니다—Aspose.Zip은 .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, 그리고 .NET 5–10을 지원합니다.

## Seven Zip 압축 방법에는 무엇이 있나요?

Seven Zip은 여러 알고리즘을 지원하며, 각각은 다양한 상황에 최적화되어 있습니다. **LZMA2**는 가장 높은 압축 비율을 제공하며(종종 BZip2보다 30‑40 % 작음), **BZip2**는 레거시 도구 지원이 넓은 견고한 압축을 제공하고, **Store**는 파일을 축소하지 않고 그대로 아카이브하여 원본 타임스탬프를 완벽히 보존합니다.

## 필수 조건

Before we dive in, make sure you have:

- C# 및 Visual Studio에 대한 기본 지식.  
- Aspose.Zip for .NET 라이브러리를 설치하세요. 공식 다운로드 페이지 **[here](https://releases.aspose.com/zip/net/)**에서 받을 수 있습니다.  
- `dataDir` 폴더에 아카이브하려는 파일이 포함되어 있어야 합니다.

## 네임스페이스 가져오기

먼저, C# 파일에 필요한 네임스페이스를 추가하세요:
```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

이 클래스들을 통해 압축 설정 및 아카이브 처리를 할 수 있습니다.

## LZMA2 압축 – 최대 비율로 7z 만들기

`Archive` 클래스는 여러 파일을 포함할 수 있는 7z 아카이브를 나타냅니다.  
LZMA2 알고리즘은 지원되는 방법 중 가장 높은 압축 비율을 제공합니다. 입력을 블록으로 나누고 정교한 사전 압축을 적용합니다. Aspose.Zip에서는 파일을 추가하기 전에 `Archive` 객체의 `CompressionMethod`를 `CompressionMethod.Lzma2`로 설정합니다.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tip:** LZMA2는 원본 파일이 1 MB보다 클 때 가장 잘 작동합니다. 많은 작은 파일의 경우 BZip2가 더 빠를 수 있습니다.

## BZip2 압축 – 균형 잡힌 선택

`Archive` 클래스는 여러 파일을 포함할 수 있는 7z 아카이브를 나타냅니다.  
BZip2는 오래된 도구와의 호환성이 좋은 견고한 압축을 제공합니다. Burrows‑Wheeler 변환과 Huffman 코딩을 사용해 크기를 줄입니다. Aspose.Zip에서는 `Archive` 인스턴스를 구성할 때 `CompressionMethod.BZip2`를 선택하여 대부분의 텍스트 및 바이너리 파일에 대해 속도와 압축 비율의 균형을 맞춥니다.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2는 합리적인 속도를 유지하면서 견고한 압축을 제공하므로, 대상 환경에서 LZMA2를 지원하지 않을 때 좋은 대안이 됩니다.

## Store (압축 없음) – 크기가 중요하지 않을 때

`Archive` 클래스는 여러 파일을 포함할 수 있는 7z 아카이브를 나타냅니다.  
Store 방법은 데이터를 압축하지 않고 아카이브를 생성합니다. 원본 파일을 7z 컨테이너에 그대로 복사하여 타임스탬프와 디렉터리 구조를 보존합니다. Aspose.Zip에서 사용하려면, 번들링하려는 파일을 추가하기 전에 `Archive`에 `CompressionMethod.Store`를 설정하세요.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

파일 크기를 변경하지 않고 단순히 함께 번들링만 하면 될 경우 Store 방법을 사용하세요—원본 타임스탬프를 보존하거나 아카이브가 실시간으로 압축 해제될 때 이상적입니다.

## 7z에 파일을 어떻게 추가하나요?

`Archive` 인스턴스를 생성하고 원하는 `CompressionMethod`를 설정한 뒤 `AddAllFiles(dataDir)`를 호출하여 7z 아카이브에 파일을 추가합니다. 이 메서드는 지정된 폴더를 재귀적으로 스캔하여 아카이브 내부에 디렉터리 계층 구조를 보존합니다. 이 접근 방식을 사용하면 초기 설정 후 단 한 줄의 코드로 **compress folder to 7z** 할 수 있습니다.

## 일반적인 사용 사례

| Scenario | Recommended Method |
|----------|--------------------|
| 대형 설치 프로그램 배포 | LZMA2 |
| 레거시 도구와 로그 공유 | BZip2 |
| 빠른 추출을 위한 파일 패키징 | Store (no compression) |
| 웹 서비스에서 실시간으로 **compress folder to 7z** 필요 | LZMA2 (for best ratio) |

## 문제 해결 및 팁

- **아카이브에 파일이 누락되었나요?** `dataDir`가 올바른 디렉터리를 가리키는지와 프로세스에 읽기 권한이 있는지 확인하세요.  
- **구버전 7‑Zip에서 아카이브를 열 수 없나요?** LZMA2는 최신 압축 해제 라이브러리가 필요할 수 있으므로 BZip2 또는 Store를 사용하세요.  
- **성능 병목 현상이 있나요?** 대용량 데이터 세트의 경우 모든 항목을 메모리에 로드하는 대신 아카이브를 스트리밍하는 것을 고려하세요.

## 자주 묻는 질문

**Q: Aspose.Zip for .NET을 모든 유형의 파일에 사용할 수 있나요?**  
A: 예, Aspose.Zip은 다양한 파일 형식을 지원하여 사실상 모든 파일 유형을 압축 및 압축 해제할 수 있습니다.

**Q: Aspose.Zip for .NET의 무료 체험판을 이용할 수 있나요?**  
A: 예, 무료 체험판은 **[here](https://releases.aspose.com/)**에서 받을 수 있습니다.

**Q: Aspose.Zip for .NET 문서는 어디에서 찾을 수 있나요?**  
A: 전체 API 레퍼런스는 **[here](https://reference.aspose.com/zip/net/)**에서 확인할 수 있습니다.

**Q: Aspose.Zip for .NET의 임시 라이선스를 어떻게 받을 수 있나요?**  
A: 임시 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 받을 수 있습니다.

**Q: Aspose.Zip for .NET에 대한 지원은 어디서 받을 수 있나요?**  
A: 지원은 **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**에서 받을 수 있습니다.

---

**마지막 업데이트:** 2026-06-29  
**테스트 환경:** Aspose.Zip for .NET 24.12  
**작성자:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [파일 압축 C# – Aspose.Zip for .NET으로 7z 아카이브 만들기](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Aspose.Zip for .NET을 사용하여 폴더 압축하는 방법](/zip/net/directory-and-folder-compression/compress-directory/)
- [Aspose.Zip for .NET에서 LZMA 압축하는 방법](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}