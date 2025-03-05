---
title: .NET용 Aspose.Zip에서 FileInfo를 사용하여 파일 압축
linktitle: FileInfo를 사용하여 파일 압축
second_title: 파일 압축 및 보관을 위한 Aspose.Zip .NET API
description: .NET용 Aspose.Zip에서 fileinfo를 사용하여 파일을 압축하는 방법을 알아보세요. 효율적인 파일 관리를 위한 단계별 가이드를 따르세요.
type: docs
weight: 11
url: /ko/net/file-compression/compress-files-fileinfo/
---
## 소개

.NET용 Aspose.Zip을 사용한 파일 압축에 대한 포괄적인 가이드에 오신 것을 환영합니다! 파일 저장이나 전송을 최적화하려는 경우 Aspose.Zip이 가장 적합한 솔루션입니다. 이 튜토리얼에서는 FileInfo 클래스를 사용하여 파일을 압축하는 과정을 안내하고 자세한 단계별 가이드를 제공합니다. 뛰어들어보자!

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET용 Aspose.Zip: Aspose.Zip 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/zip/net/).

2. 문서 디렉터리: 압축하려는 파일을 저장할 디렉터리를 시스템에 설정합니다.

## 네임스페이스 가져오기

.NET 프로젝트에 필요한 네임스페이스를 포함합니다.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## 1단계: 문서 디렉토리 설정

가장 먼저 문서가 저장되는 디렉터리를 정의합니다. 다음 코드를 사용할 수 있습니다.

```csharp
string dataDir = "Your Document Directory";
```

## 2단계: FileInfo를 사용하여 파일 압축

 이제 프로세스의 핵심으로 들어가 보겠습니다. 우리는`FileInfo` Aspose.Zip과 함께 클래스를 사용하여 파일을 압축합니다. 다음과 같이하세요:

### 2.1단계: Zip 파일 열기

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### 2.2단계: FileInfo 개체 만들기

 만들다`FileInfo` 압축하려는 파일의 개체:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### 2.3단계: 아카이브 생성 및 항목 추가

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### 2.4단계: Zip 파일 저장

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

축하해요! .NET용 Aspose.Zip의 FileInfo 클래스를 사용하여 파일을 성공적으로 압축했습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Zip을 사용하여 파일을 효율적으로 압축하는 방법을 살펴보았습니다. 다음 단계를 수행하면 파일 관리 기능을 향상하고 공간 사용을 최적화할 수 있습니다. Aspose.Zip의 잠재력을 최대한 활용하려면 다양한 파일 형식과 크기로 실험해 보세요.

## FAQ

### Q1: Aspose.Zip은 모든 파일 형식과 호환됩니까?

A1: Aspose.Zip은 광범위한 파일 형식을 지원하여 압축의 다양성을 보장합니다.

### Q2: Aspose.Zip을 상업용 프로젝트에 사용할 수 있나요?

 A2: 물론이죠! 우리를 방문하세요[구매 페이지](https://purchase.aspose.com/buy) 라이선스 옵션을 살펴보세요.

### Q3: Aspose.Zip에 대한 지원은 어떻게 받을 수 있나요?

 A3: 다음 커뮤니티에 참여하세요.[Aspose.Zip 포럼](https://forum.aspose.com/c/zip/37) 도움과 토론을 위해.

### Q4: 무료 평가판이 제공됩니까?

 A4: 그렇습니다.[여기에서 무료 평가판](https://releases.aspose.com/).

### Q5: Aspose.Zip에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 A5: 방문[이 링크](https://purchase.aspose.com/temporary-license/) 임시 면허 취득에 관한 정보를 확인하세요.