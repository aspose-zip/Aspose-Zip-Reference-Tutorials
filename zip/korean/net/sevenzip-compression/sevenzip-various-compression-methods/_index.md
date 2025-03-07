---
title: 7개의 Zip 파일 만들기 - Aspose.Zip for .NET Tutorial
linktitle: 다양한 압축 방법을 갖춘 SevenZip
second_title: 파일 압축 및 보관을 위한 Aspose.Zip .NET API
description: 다양한 압축 방법을 사용하여 .NET용 Aspose.Zip으로 Seven Zip 파일을 만드는 방법을 알아보세요. LZMA2, BZip2 및 Store(압축 없음)를 위한 쉬운 단계입니다.
weight: 12
url: /ko/net/sevenzip-compression/sevenzip-various-compression-methods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 7개의 Zip 파일 만들기 - Aspose.Zip for .NET Tutorial


## 소개

.NET 개발 영역에서 파일 관리 및 압축은 일반적인 작업입니다. .NET용 Aspose.Zip은 압축된 아카이브 작업을 위한 강력한 솔루션을 제공하며 다양한 압축 방법을 제공합니다. 이 튜토리얼에서는 Aspose.Zip for .NET을 사용하여 다양한 압축 방법으로 Seven Zip 파일을 만드는 방법을 살펴보겠습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍에 대한 기본적인 이해.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Zip. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/zip/net/).

## 네임스페이스 가져오기

필요한 네임스페이스를 C# 프로젝트로 가져오는 것부터 시작하세요. 시작하려면 다음 코드 조각을 사용하세요.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## LZMA2 압축

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

## BZip2 압축

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## 저장, 압축 없음

```csharp
//저장, 압축 없음
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## 결론

이 튜토리얼에서는 다양한 압축 방법으로 Seven Zip 파일을 생성할 때 Aspose.Zip for .NET의 다양성을 살펴보았습니다. 높은 압축 비율이 필요하든, 전혀 압축하지 않는 것을 선호하든 Aspose.Zip은 요구 사항을 충족할 수 있는 유연성을 제공합니다.

## 자주 묻는 질문

### 모든 유형의 파일에 Aspose.Zip for .NET을 사용할 수 있나요?
예, .NET용 Aspose.Zip은 광범위한 파일 형식을 지원하므로 다양한 형식을 압축하고 압축을 풀 수 있습니다.

### .NET용 Aspose.Zip에 대한 무료 평가판을 사용할 수 있습니까?
 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).

### .NET용 Aspose.Zip에 대한 설명서는 어디서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/zip/net/).

### .NET용 Aspose.Zip의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허 취득 가능[여기](https://purchase.aspose.com/temporary-license/).

### .NET용 Aspose.Zip에 대한 지원은 어디서 받을 수 있나요?
 다음에서 지원을 요청할 수 있습니다.[Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
