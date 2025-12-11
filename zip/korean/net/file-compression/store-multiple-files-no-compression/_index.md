---
date: 2025-12-10
description: Aspose.Zip for .NET을 사용하여 압축 없이 파일을 저장하는 방법을 배워보세요. 이 가이드는 압축되지 않은 ZIP
  파일을 생성하고, 파일을 ZIP에 저장하며, 아카이브를 효율적으로 관리하는 방법을 보여줍니다.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET를 사용하여 파일을 압축되지 않게 저장하는 방법
url: /ko/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip for .NET을 사용하여 파일을 압축 없이 저장하는 방법

현대 .NET 개발에서 **파일을 저장하는 방법**은 성능과 저장 비용에 큰 영향을 미칠 수 있습니다. 파일을 그대로—압축 없이—보관해야 할 때 Aspose.Zip for .NET은 간단하고 직관적인 API를 제공합니다. 이 튜토리얼에서는 압축되지 않은 ZIP 아카이브를 생성하고, 파일을 ZIP에 저장하며, 솔루션을 애플리케이션에 통합하는 과정을 단계별로 안내합니다.

## 빠른 답변
- **“압축되지 않은 zip”이란?** 각 엔트리가 “store” 방식으로 저장되어 원본 파일 바이트가 그대로 유지되는 ZIP 아카이브를 의미합니다.  
- **왜 압축을 피하나요?** 아카이빙 속도를 높이고, 다운스트림 처리 시 원본 파일 크기를 유지하거나, 데이터 변형을 금지하는 규제 요구사항을 충족하기 위해서입니다.  
- **어떤 Aspose.Zip 클래스가 이를 처리하나요?** `ArchiveEntrySettings`와 `StoreCompressionSettings`를 함께 사용합니다.  
- **라이선스가 필요합니까?** 무료 체험판으로 테스트가 가능하지만, 상용 환경에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework, .NET Core, .NET 5/6/7 및 이후 버전.

## 압축 없이 여러 파일을 저장한다는 의미
압축 없이 여러 파일을 저장한다는 것은 *store* 압축 방식을 사용해 각 파일을 ZIP 컨테이너에 추가한다는 뜻입니다. 파일은 원본과 바이트 단위로 동일하게 유지되므로, 빠른 아카이빙이 필요하거나 데이터를 변경하지 않아야 할 때 이상적입니다.

## Aspose.Zip을 사용해 압축되지 않은 아카이브를 만드는 이유
- **속도:** CPU 집약적인 압축 알고리즘이 실행되지 않습니다.  
- **예측 가능한 크기:** 아카이브 크기는 원본 파일들의 합계에 최소한의 ZIP 오버헤드만 추가된 값과 같습니다.  
- **호환성:** 생성된 ZIP은 모든 표준 압축 해제 유틸리티와 호환됩니다.  
- **유연성:** 필요에 따라 동일한 아카이브에 압축된 엔트리와 압축되지 않은 엔트리를 혼합해서 사용할 수 있습니다.

## 사전 준비
- **Aspose.Zip for .NET** – 프로젝트에 통합되어 있어야 합니다. 설치 방법은 공식 [documentation](https://reference.aspose.com/zip/net/)을 참고하세요.  
- **.NET 개발 환경** – Visual Studio, VS Code 또는 선호하는 IDE.  
- **문서 디렉터리** – 아카이브에 포함하려는 파일이 들어 있는 폴더(예: “Your Document Directory”).

## 네임스페이스 가져오기
코드를 작성하기 전에 필요한 네임스페이스를 가져와야 컴파일러가 Aspose 클래스를 찾을 수 있습니다.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## 단계 1: 문서 디렉터리 설정
소스 파일이 위치한 경로를 정의합니다. 플레이스홀더를 실제 시스템의 폴더 경로로 교체하세요.

```csharp
string dataDir = "Your Document Directory";
```

## 단계 2: 압축 없이 Zip 아카이브 만들기
튜토리얼의 핵심 – `StoreCompressionSettings`로 구성된 `Archive` 인스턴스를 생성합니다. 이렇게 하면 Aspose.Zip이 각 엔트리를 *store* (즉, 압축하지 않음) 방식으로 저장합니다.

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

> **팁:** 일부 파일은 압축하고 다른 파일은 압축하지 않으려면 파일마다 별도의 `ArchiveEntrySettings` 인스턴스를 만들고 동일한 `Archive`에 추가하면 됩니다.

## 일반적인 문제와 해결책
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **File not found** | `dataDir` 경로가 잘못되었거나 파일 확장자가 누락되었습니다. | 경로를 확인하고 파일이 존재하는지 확인하세요. `Path.Combine`을 사용하면 더 안전합니다. |
| **Access denied** | 프로세스에 소스 파일을 읽거나 ZIP을 쓸 권한이 없습니다. | 적절한 권한으로 애플리케이션을 실행하거나 쓰기 권한이 있는 폴더를 선택하세요. |
| **Unexpected file size in ZIP** | 아카이브가 기본 압축 설정으로 생성되었습니다. | `new StoreCompressionSettings()`가 `ArchiveEntrySettings`에 전달되었는지 확인하세요. |

## 자주 묻는 질문

**Q: 특정 파일 유형은 압축하고, 다른 파일은 압축 없이 저장할 수 있나요?**  
A: 네, 파일마다 다른 `ArchiveEntrySettings`를 만들어 압축된 엔트리와 압축되지 않은 엔트리를 동일한 아카이브에 혼합할 수 있습니다.

**Q: Aspose.Zip for .NET은 .NET Core 및 .NET 5/6과 호환되나요?**  
A: 물론입니다. 이 라이브러리는 .NET Framework, .NET Core, .NET Standard 및 최신 .NET 버전을 모두 지원합니다.

**Q: 아카이빙 과정에서 예외를 어떻게 처리해야 하나요?**  
A: 아카이빙 코드를 `try‑catch` 블록으로 감싸고 예외 세부 정보를 로그에 기록하세요. 이렇게 하면 정상적인 실패 처리와 디버깅이 쉬워집니다.

**Q: Aspose.Zip은 다중 스레드 아카이빙을 지원하나요?**  
A: 지원합니다. 여러 파일을 병렬로 처리해 아카이브에 추가할 수 있지만, `Archive` 객체 자체는 스레드 안전하지 않으므로 엔트리를 추가할 때는 동기화가 필요합니다.

**Q: 기존 프로젝트에 Aspose.Zip을 큰 코드 변경 없이 통합할 수 있나요?**  
A: 가능합니다. API가 간단히 끼워넣을 수 있도록 설계되었습니다. 마이그레이션 가이드는 공식 [documentation](https://reference.aspose.com/zip/net/)을 참고하세요.

---

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Zip for .NET 24.12 (작성 시 최신 버전)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}