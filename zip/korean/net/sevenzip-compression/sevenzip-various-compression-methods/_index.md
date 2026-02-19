---
date: 2025-12-25
description: Aspose.Zip for .NET를 사용하여 7z 파일을 만드는 방법을 배우고, LZMA2, BZip2, Store 등 7가지
  압축 방식을 다룹니다. 폴더를 7z로 압축하는 시나리오에 적합합니다.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 7z 파일 만들기 방법 – Aspose.Zip for .NET 튜토리얼
url: /ko/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 7z 파일 만들기 – Aspose.Zip for .NET 튜토리얼

## 소개

.NET 애플리케이션에서 프로그래밍 방식으로 **how to create 7z** 아카이브를 만들어야 한다면, 여기가 바로 정답입니다. Aspose.Zip for .NET은 지원되는 압축 알고리즘을 사용해 Seven Zip 아카이브를 손쉽게 생성할 수 있게 해줍니다. 배포용으로 **compress folder to 7z** 하거나 단순히 신뢰할 수 있는 **seven zip archive .net** 솔루션이 필요할 때도 마찬가지입니다. 이 가이드에서는 세 가지 인기 압축 방식인 LZMA2, BZip2, Store(압축 없음)를 살펴보고, 몇 줄의 C# 코드만으로 7z 파일을 만드는 방법을 정확히 보여드립니다.

## 빠른 답변
- **What library should I use?** Aspose.Zip for .NET은 가장 완전한 Seven Zip 기능 세트를 제공합니다.  
- **Which compression method gives the best ratio?** LZMA2는 일반적으로 혼합 데이터에 대해 가장 높은 압축률을 제공합니다.  
- **Can I create a 7z without any compression?** 예—Store(압축 없음) 방식을 사용하면 됩니다.  
- **Do I need a license for development?** 무료 체험판을 사용할 수 있으며, 제품 환경에서는 라이선스가 필요합니다.  
- **Is this compatible with .NET 6/7?** 물론입니다—Aspose.Zip은 .NET Framework, .NET Core 및 .NET 5+를 지원합니다.

## Seven Zip 압축 방식은 무엇인가요?

Seven Zip은 여러 알고리즘을 지원하며, 각각은 다양한 시나리오에 최적화되어 있습니다:

* **LZMA2** – 높은 압축률, 대용량 혼합형 파일에 이상적입니다.  
* **BZip2** – 견고한 압축을 제공하지만 LZMA2보다 느립니다; 오래된 도구와의 호환성이 필요할 때 유용합니다.  
* **Store** – 압축 없음; 크기 감소 없이 단순히 파일을 보관해야 할 때 완벽합니다(예: 원본 파일 타임스탬프를 보존할 경우).

이러한 **seven zip compression methods**를 이해하면 프로젝트에 맞는 설정을 선택하는 데 도움이 됩니다.

## 전제 조건

시작하기 전에 다음이 준비되어 있는지 확인하세요:

- C# 및 Visual Studio에 대한 기본 지식.  
- Aspose.Zip for .NET 라이브러리가 설치되어 있어야 합니다. 공식 다운로드 페이지 **[here](https://releases.aspose.com/zip/net/)**에서 받으세요.  
- 아카이브하려는 파일이 들어 있는 폴더(`dataDir`).

## 네임스페이스 가져오기

먼저, C# 파일에 필요한 네임스페이스를 추가합니다:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

이 클래스들을 통해 압축 설정 및 아카이브 처리를 할 수 있습니다.

## LZMA2 압축 – 최대 비율로 7z 만들기

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

> **Pro tip:** LZMA2는 소스 파일이 1 MB보다 클 때 가장 잘 작동합니다. 많은 작은 파일의 경우 BZip2가 더 빠를 수 있습니다.

## BZip2 압축 – 균형 잡힌 선택

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2는 견고한 압축을 제공하면서도 합리적인 속도를 유지하므로, 대상 환경에서 LZMA2를 지원하지 않을 때 좋은 대안이 됩니다.

## Store (압축 없음) – 크기가 중요하지 않을 때

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

기를 변경하지 않고 단순히 파일을 묶기만 하면 된다면 Store 방식을 사용하세요—원본 타임스탬프를 보존하거나 아카이브가 실시간으로 압축 해제될 때 완벽합니다.

## 일반적인 사용 사례

| 시나리오 | 권장 방법 |
|----------|--------------------|
| 대형 설치 프로그램 배포 | LZMA2 |
| 레거시 도구와 로그 공유 | BZip2 |
| 빠른 추출을 위한 파일 패키징 | Store (no compression) |
| 웹 서비스에서 실시간으로 **compress folder to 7z** 필요 | LZMA2 (최고 비율) |

## 문제 해결 및 팁

- **Missing files in the archive?** `dataDir`가 올바른 디렉터리를 가리키는지와 프로세스에 읽기 권한이 있는지 확인하세요.  
- **Archive fails to open on older 7‑Zip versions?** LZMA2는 최신 압축 해제 라이브러리가 필요할 수 있으므로, BZip2 또는 Store를 사용하세요.  
- **Performance bottleneck?** 대용량 데이터 세트의 경우, 모든 항목을 메모리에 로드하는 대신 아카이브를 스트리밍하는 것을 고려하세요.

## 자주 묻는 질문

**Q: Aspose.Zip for .NET을 모든 유형의 파일에 사용할 수 있나요?**  
A: 네, Aspose.Zip은 다양한 파일 형식을 지원하므로 사실상 모든 파일 유형을 압축 및 압축 해제할 수 있습니다.

**Q: Aspose.Zip for .NET의 무료 체험판을 제공하나요?**  
A: 네, 무료 체험판은 **[here](https://releases.aspose.com/)**에서 받을 수 있습니다.

**Q: Aspose.Zip for .NET 문서는 어디에서 찾을 수 있나요?**  
A: 전체 API 레퍼런스는 **[here](https://reference.aspose.com/zip/net/)**에서 확인할 수 있습니다.

**Q: Aspose.Zip for .NET 임시 라이선스는 어떻게 얻을 수 있나요?**  
A: 임시 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 받을 수 있습니다.

**Q: Aspose.Zip for .NET 지원은 어디에서 받을 수 있나요?**  
A: **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**에서 지원을 받을 수 있습니다.

---

**마지막 업데이트:** 2025-12-25  
**테스트 환경:** Aspose.Zip for .NET 24.12  
**작성자:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
