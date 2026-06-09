---
date: 2026-06-09
description: Aspose.Zip for .NET을 사용하여 zip에 비밀번호를 추가하고 LZMA zip 아카이브를 만드는 방법을 배웁니다.
  이 튜토리얼에서는 Bzip2, LZMA(사전 크기), PPMd, Enhanced Deflate, Store 압축 및 대용량 파일의 ASP.NET
  파일 압축을 다룹니다.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: 압축 설정 최적화
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Aspose.Zip for .NET을 사용하여 zip에 비밀번호를 추가하고 LZMA 아카이브 만들기
url: /ko/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip에 비밀번호를 추가하고 Aspose.Zip for .NET으로 LZMA 아카이브 만들기

현대 .NET 애플리케이션에서 **zip에 비밀번호를 추가**하면서 고압축률 LZMA zip 아카이브를 만들면 민감한 데이터를 보호하면서 최상의 압축을 얻을 수 있습니다. ASP.NET 파일 압축 서비스, 다중 기가바이트 파일을 처리하는 데스크톱 유틸리티, 또는 클라우드 기반 워크플로우를 구축하든, 이 튜토리얼은 Aspose.Zip for .NET을 사용하여 파일을 안전하게 압축하는 정확한 단계들을 안내합니다.

## 빠른 답변
- **LZMA 압축의 주요 이점은 무엇인가요?** 대부분의 파일 유형에 대해 합리적인 속도로 가장 높은 압축률을 제공합니다.  
- **어떤 방법이 압축 없이 파일을 저장합니까?** Store compression(‘store compression zip’라고도 함).  
- **ASP.NET 애플리케이션에서 이 설정을 사용할 수 있나요?** 예—프로젝트에 Aspose.Zip을 참조하고 동일한 API를 호출하면 됩니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 프로덕션에는 상용 라이선스가 필요하며, 무료 체험판을 사용할 수 있습니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, 그리고 .NET 5–10.

## Aspose.Zip에서 “zip에 비밀번호를 추가”란 무엇인가요?
**zip 비밀번호를 추가하면 ZIP 아카이브 내부의 모든 항목이 암호화되어 비밀번호를 아는 사용자만 파일을 추출할 수 있습니다.** Aspose.Zip은 기존 ZipCrypto 암호화와 AES 암호화(128, 192, 또는 256‑비트)를 모두 지원합니다. 암호화 설정은 `Archive`를 생성할 때 `ArchiveEntrySettings`의 두 번째 인수로 제공되며, 별도의 `SetPassword` 메서드는 없습니다.

## .NET 파일 압축에 Aspose.Zip을 사용하는 이유는?
Aspose.Zip은 다양한 알고리즘을 포괄하면서 높은 성능과 낮은 메모리 사용량을 제공하는 단일 일관된 API를 제공합니다. 개발자는 각 시나리오에 가장 적합한 압축 방식을 선택하고 한 단계에서 암호화를 적용할 수 있어 코드가 단순해지고 유지 보수 부담이 줄어듭니다.

- **통합 API** – Bzip2, LZMA, PPMd, Enhanced Deflate, Store에 대한 일관된 인터페이스 하나.  
- **성능 최적화** – 최적화된 네이티브 구현은 전체 파일을 메모리에 로드하지 않고 **10 GB까지** 처리합니다.  
- **ASP.NET 친화적** – 웹 프로젝트, 백그라운드 서비스, Azure Functions에서 원활하게 작동합니다.  
- **세밀한 제어** – 사전 크기, 압축 수준, 암호화를 단일 생성자 호출로 조정합니다.  
- **10개 이상의 압축 알고리즘 지원** – 엔터프라이즈 데이터 파이프라인에서 가장 일반적인 사용 사례를 포괄합니다.

## 사전 요구 사항
- **Aspose.Zip for .NET 라이브러리** – [Aspose documentation](https://reference.aspose.com/zip/net/)에서 다운로드하고 설치합니다.  
- **샘플 텍스트 파일** – 압축할 샘플 파일(예: `sample.txt`)을 준비합니다.  
- **.NET 개발 환경** – Visual Studio 2022 또는 호환되는 IDE.

## 네임스페이스 가져오기

`Archive`, `ArchiveEntrySettings`, 암호화 클래스는 `Aspose.Zip` 네임스페이스에 있습니다. 파일 상단에 이를 가져옵니다:

- `Archive`는 ZIP 아카이브 컨테이너를 나타냅니다.  
- `ArchiveEntrySettings`는 각 항목에 대한 압축 및 암호화 옵션을 보유합니다.  
- 암호화 클래스(예: `AesEncryptionSettings`)는 데이터 암호화 방식을 정의합니다.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

이제 각 압축 설정을 살펴보고 적절한 경우 **zip에 비밀번호를 추가**하는 방법을 확인해 보겠습니다.

## Bzip2 압축 설정 사용

### 단계 1: 전통 암호화와 함께 Bzip2 압축 초기화

`Bzip2CompressionSettings`는 Bzip2 알고리즘(블록 크기 등)을 구성합니다.  
`TraditionalEncryptionSettings`는 항목에 레거시 ZipCrypto 암호화를 적용합니다.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*비밀번호 보호는 `ArchiveEntrySettings`에 직접 전달되는 `TraditionalEncryptionSettings`를 통해 적용됩니다.*

## Aspose.Zip for .NET을 사용하여 zip에 비밀번호를 추가하는 방법

소스 파일을 로드하고, 항목 설정으로 `Archive`를 생성한 다음 파일을 아카이브에 추가합니다. `ArchiveEntrySettings` 인스턴스를 만들 때 암호화 설정을 제공했기 때문에 암호화가 자동으로 적용됩니다.

**직접 답변 (40‑70 단어):**  
`ArchiveEntrySettings` 객체를 생성하여 원하는 압축 설정과 `TraditionalEncryptionSettings` 또는 `AesEncryptionSettings` 중 하나를 포함합니다. 그런 다음 이 객체를 `Archive` 생성자에 전달하고 `AddEntry`로 파일을 추가합니다. 아카이브는 비밀번호가 이미 포함된 상태로 작성되므로 생성 후 추가 단계가 필요하지 않습니다.

`ArchiveEntrySettings`는 Aspose.Zip에 각 항목을 어떻게 압축하고 암호화할지 알려주는 구성 보관소입니다.

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Aspose.Zip을 사용하여 LZMA zip 아카이브 만드는 방법

### 단계 1: AES256 암호화와 함께 LZMA 압축 초기화

`LzmaCompressionSettings`는 사전 크기와 fast bytes와 같은 LZMA 전용 매개변수를 제어합니다.  
`AesEncryptionSettings`는 아카이브 항목에 AES‑256 암호화를 제공합니다.

**직접 답변 (40‑70 단어):**  
선택한 `DictionarySize`로 `LzmaCompressionSettings`를 인스턴스화하고, 비밀번호와 `EncryptionMethod.AES256`을 포함한 `AesEncryptionSettings` 객체를 만든 다음 두 개를 사용해 `ArchiveEntrySettings`를 구성합니다. 이를 `Archive` 생성자에 전달하고 파일을 추가하면 결과 zip이 LZMA 압축 및 AES 보호를 한 번에 수행합니다.

`LzmaCompressionSettings`는 사전 크기와 fast bytes와 같은 LZMA 전용 매개변수를 제어하는 클래스입니다.

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **팁:** LZMA는 압축 비율과 메모리 사용량에 영향을 주는 구성 가능한 **LZMA 사전 크기**를 제공합니다. 매우 큰 파일에 대해 미세 조정이 필요하면 `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }`와 같이 설정할 수 있습니다.

## PPMd 압축 설정 사용

### 단계 1: AES256 암호화와 함께 PPMd 압축 초기화

`PpmdCompressionSettings`는 PPMd 알고리즘의 순서와 메모리 사용량을 정의합니다.  
`AesEncryptionSettings`는 아카이브 항목에 AES‑256 암호화를 제공합니다.

**직접 답변 (40‑70 단어):**  
`PpmdCompressionSettings` 인스턴스를 생성하고 비밀번호가 포함된 `AesEncryptionSettings` 객체와 결합한 뒤 두 개를 `ArchiveEntrySettings`에 전달합니다. `Archive`를 생성할 때 이 설정 객체를 사용하면 결과 zip이 PPMd 압축 및 비밀번호 보호가 적용되어 추가 호출이 필요 없습니다.

`PpmdCompressionSettings`는 PPMd 알고리즘의 순서와 메모리 사용량을 정의합니다.

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Enhanced Deflate 압축 설정 사용

### 단계 1: AES256 암호화와 함께 Enhanced Deflate 압축 초기화

`EnhancedDeflateCompressionSettings`는 속도와 크기의 균형을 맞추는 압축 수준을 지정할 수 있게 합니다.  
`AesEncryptionSettings`는 아카이브 항목에 AES‑256 암호화를 제공합니다.

**직접 답변 (40‑70 단어):**  
원하는 수준(0‑9)으로 `EnhancedDeflateCompressionSettings`를 인스턴스화하고 `AesEncryptionSettings`와 결합한 뒤 `ArchiveEntrySettings`에 래핑합니다. 이를 `Archive` 생성자에 전달하고 파일을 추가하면 아카이브가 Enhanced Deflate 압축 및 AES‑256 비밀번호 보호를 한 번에 적용해 생성됩니다.

`EnhancedDeflateCompressionSettings`는 속도와 크기의 균형을 맞추는 압축 수준을 지정할 수 있게 합니다.

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Store 압축 설정 사용 (store compression zip)

### 단계 1: 전통 암호화와 함께 Store 압축 초기화

`StoreCompressionSettings`는 Aspose.Zip에 압축을 전혀 수행하지 않고 원본 파일을 바이트 단위로 그대로 보존하도록 지시합니다.  
`TraditionalEncryptionSettings`는 레거시 ZipCrypto 암호화를 적용합니다.

**직접 답변 (40‑70 단어):**  
`StoreCompressionSettings` 인스턴스를 생성하고(압축을 수행하지 않음) 비밀번호가 포함된 `TraditionalEncryptionSettings`와 결합한 뒤 두 개를 `ArchiveEntrySettings`에 래핑합니다. 이를 `Archive` 생성자에 전달하면 결과 zip은 원본 파일을 압축하지 않고 그대로 포함하면서 비밀번호가 보호됩니다.

`StoreCompressionSettings`는 Aspose.Zip에 압축을 전혀 수행하지 않고 원본 파일을 바이트 단위로 그대로 보존하도록 지시합니다.

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **전문가 팁:** `dataDir` 변수를 실제 작업 디렉터리를 가리키도록 조정하고, 하나의 아카이브에 여러 파일을 추가해야 할 경우 동일한 `Archive` 인스턴스를 재사용하십시오.

## 일반적인 문제 및 해결책
- **"File not found" 오류** – `dataDir`이 경로 구분자(`\` 또는 `/`)로 끝나는지와 `sample.txt`가 존재하는지 확인하십시오.  
- **대용량 파일의 메모리 사용** – `ArchiveEntrySettings`를 사용해 스트리밍 모드를 활성화하면 데이터를 직접 출력 스트림에 기록합니다.  
- **호환되지 않는 압축 수준** – 일부 알고리즘(LZMA 등)은 `DictionarySize`와 같은 추가 속성을 제공합니다. 더 세밀한 제어가 필요하면 API 문서를 참고하십시오.  
- **비밀번호가 적용되지 않음** – 암호화 설정 객체가 아카이브 생성 시 `ArchiveEntrySettings`의 두 번째 인수로 전달되었는지 확인하고, 아카이브 생성 후에 전달하지 마십시오.  

## 자주 묻는 질문

**Q: Aspose.Zip for .NET을 다른 압축 라이브러리와 함께 사용할 수 있나요?**  
A: Aspose.Zip은 자체 내장 알고리즘과 함께 작동하도록 설계되었습니다. 타사 라이브러리를 통합할 수는 있지만 Aspose API 외부에서 사용자 정의 처리가 필요합니다.

**Q: Aspose.Zip으로 만든 zip에 비밀번호 보호를 어떻게 추가할 수 있나요?**  
A: `Archive`를 생성할 때 `ArchiveEntrySettings`의 두 번째 인수로 `TraditionalEncryptionSettings` 또는 `AesEncryptionSettings`를 전달하십시오. 전체 예제는 [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)를 참고하세요.

**Q: 테스트할 수 있는 체험판이 있나요?**  
A: 예, 체험판은 [here](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: 커뮤니티 도움을 받거나 질문을 하려면 어디에 가야 하나요?**  
A: 지원 및 커뮤니티 토론은 [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)에서 확인하십시오.

**Q: 평가용 임시 라이선스를 받을 수 있나요?**  
A: 예, 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

**Q: 이것이 ASP.NET 파일 압축에 어떻게 도움이 되나요?**  
A: ASP.NET 컨트롤러나 미들웨어에서 동일한 API를 호출하면 파일을 실시간으로 압축해 클라이언트에 전송하기 전에 대역폭을 줄이고 인지된 성능을 향상시킬 수 있습니다.

**Q: 대용량 파일을 효율적으로 압축하는 최선의 방법은 무엇인가요?**  
A: 스트리밍 모드와 LZMA 압축, 적절한 `DictionarySize`를 결합하면 대규모 데이터셋에 대해 메모리 사용량과 압축 비율을 균형 있게 맞출 수 있습니다.

---

**마지막 업데이트:** 2026-06-09  
**테스트 환경:** Aspose.Zip 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Zip for .NET - 압축 없이 여러 파일 저장 및 Zip 아카이브 비밀번호 보호](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [.NET 디렉터리용 비밀번호 보호 zip 만들기 – Aspose.Zip 튜토리얼](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [여러 파일 zip c# – Aspose.Zip for .NET으로 손쉬운 압축](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}