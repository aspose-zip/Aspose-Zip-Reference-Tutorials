---
date: 2026-06-09
description: Dowiedz się, jak dodać hasło do zip i utworzyć archiwa LZMA przy użyciu
  Aspose.Zip dla .NET. Ten samouczek obejmuje Bzip2, LZMA (rozmiar słownika), PPMd,
  Enhanced Deflate, kompresję Store oraz kompresję dużych plików w ASP.NET.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Optymalizacja ustawień kompresji
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
title: Dodaj hasło do zip i utwórz archiwum LZMA przy użyciu Aspose.Zip dla .NET
url: /pl/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj hasło do zip i utwórz archiwum LZMA przy użyciu Aspose.Zip dla .NET

W nowoczesnych aplikacjach .NET, **add password to zip** podczas tworzenia archiwum zip LZMA o wysokim współczynniku kompresji może chronić wrażliwe dane i jednocześnie zapewnić najlepszą możliwą kompresję. Niezależnie od tego, czy tworzysz usługę kompresji plików w ASP.NET, narzędzie desktopowe obsługujące pliki wielogigabajtowe, czy przepływ pracy w chmurze, ten samouczek przeprowadzi Cię krok po kroku przez proces zabezpieczania i kompresowania plików przy użyciu Aspose.Zip dla .NET.

## Szybkie odpowiedzi
- **Jaka jest główna zaleta kompresji LZMA?** Highest compression ratio with reasonable speed for most file types.  
- **Która metoda przechowuje pliki bez kompresji?** Store compression (also called “store compression zip”).  
- **Czy mogę używać tych ustawień w aplikacji ASP.NET?** Yes—simply reference Aspose.Zip in your project and call the same API.  
- **Czy potrzebuję licencji do użytku produkcyjnego?** A commercial license is required for production; a free trial is available.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.

## Co to jest „add password to zip” w Aspose.Zip?
**Dodanie hasła do zip szyfruje każdy wpis w archiwum ZIP, tak aby tylko użytkownicy znający hasło mogli wyodrębnić pliki.** Aspose.Zip supports both traditional ZipCrypto encryption and AES encryption (128, 192, or 256‑bit). Encryption settings are supplied as the second argument to `ArchiveEntrySettings` when constructing an `Archive`; there is no separate `SetPassword` method.

## Dlaczego warto używać Aspose.Zip do kompresji plików w .NET?
Aspose.Zip zapewnia jednorodne API obejmujące wiele algorytmów, zapewniając wysoką wydajność i niskie zużycie pamięci. Umożliwia programistom wybór najlepszej metody kompresji dla każdego scenariusza oraz zastosowanie szyfrowania w jednym kroku, upraszczając kod i zmniejszając nakład utrzymania.

- **Unified API** – Jednolity interfejs dla Bzip2, LZMA, PPMd, Enhanced Deflate i Store.  
- **Performance‑tuned** – Zoptymalizowana natywna implementacja przetwarza **pliki do 10 GB** bez ładowania całego pliku do pamięci.  
- **ASP.NET friendly** – Działa bezproblemowo w projektach webowych, usługach w tle i Azure Functions.  
- **Fine‑grained control** – Umożliwia regulację rozmiaru słownika, poziomu kompresji i szyfrowania za pomocą jednego wywołania konstruktora.  
- **Supports 10+ compression algorithms** – obejmuje najczęstsze przypadki użycia w przedsiębiorstwowych pipeline'ach danych.

## Wymagania wstępne
- **Aspose.Zip for .NET Library** – Pobierz i zainstaluj z [Aspose documentation](https://reference.aspose.com/zip/net/).  
- **Sample Text File** – Przygotuj przykładowy plik (np. `sample.txt`), który zostanie skompresowany.  
- **.NET development environment** – Visual Studio 2022 lub dowolne kompatybilne IDE.  

## Importowanie przestrzeni nazw

Klasy `Archive`, `ArchiveEntrySettings` oraz klasy szyfrowania znajdują się w przestrzeni nazw `Aspose.Zip`. Zaimportuj je na początku pliku:

- `Archive` reprezentuje kontener archiwum ZIP.  
- `ArchiveEntrySettings` przechowuje opcje kompresji i szyfrowania dla każdego wpisu.  
- Klasy szyfrowania (np. `AesEncryptionSettings`) definiują sposób szyfrowania danych.  

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

Teraz przyjrzyjmy się każdemu ustawieniu kompresji i zobaczmy, jak **add password to zip** w odpowiednich miejscach.

## Using Bzip2 Compression Settings

### Krok 1: Inicjalizacja kompresji Bzip2 z tradycyjnym szyfrowaniem

`Bzip2CompressionSettings` konfiguruje algorytm Bzip2 (rozmiar bloku itp.).  
`TraditionalEncryptionSettings` stosuje starsze szyfrowanie ZipCrypto do wpisu.

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

*Ochrona hasłem jest stosowana za pomocą `TraditionalEncryptionSettings` przekazywanego bezpośrednio do `ArchiveEntrySettings`.*

## Jak dodać hasło do zip przy użyciu Aspose.Zip dla .NET

Załaduj plik źródłowy, utwórz `Archive` z ustawieniami wpisu i dodaj plik do archiwum. Szyfrowanie jest stosowane automatycznie, ponieważ zostało podane przy tworzeniu instancji `ArchiveEntrySettings`.

**Direct answer (40‑70 words):**  
Utwórz obiekt `ArchiveEntrySettings`, który zawiera zarówno żądane ustawienia kompresji, jak i `TraditionalEncryptionSettings` lub `AesEncryptionSettings`. Następnie przekaż ten obiekt do konstruktora `Archive` i dodaj pliki za pomocą `AddEntry`. Archiwum jest zapisywane z już wbudowanym hasłem, więc po utworzeniu nie jest wymagana dodatkowa operacja.

`ArchiveEntrySettings` jest kontenerem konfiguracji, który określa, jak Aspose.Zip ma kompresować i szyfrować każdy wpis.  

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

## Jak utworzyć archiwum zip LZMA przy użyciu Aspose.Zip

### Krok 1: Inicjalizacja kompresji LZMA z szyfrowaniem AES256

`LzmaCompressionSettings` kontroluje specyficzne dla LZMA parametry, takie jak rozmiar słownika i szybkie bajty.  
`AesEncryptionSettings` zapewnia szyfrowanie AES‑256 dla wpisów w archiwum.

**Direct answer (40‑70 words):**  
Utwórz instancję `LzmaCompressionSettings` z wybranym `DictionarySize`, utwórz obiekt `AesEncryptionSettings` z hasłem i `EncryptionMethod.AES256`, a następnie zbuduj `ArchiveEntrySettings` z obu. Przekaż to do konstruktora `Archive` i dodaj pliki; wynikowy zip będzie skompresowany LZMA i zabezpieczony AES w jednej operacji.

`LzmaCompressionSettings` jest klasą kontrolującą specyficzne dla LZMA parametry, takie jak rozmiar słownika i szybkie bajty.  

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

> **Tip:** LZMA oferuje konfigurowalny **rozmiar słownika LZMA**, który wpływa zarówno na współczynnik kompresji, jak i zużycie pamięci. Możesz go ustawić za pomocą `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }`, jeśli potrzebujesz dokładnie dostroić dla bardzo dużych plików.

## Używanie ustawień kompresji PPMd

### Krok 1: Inicjalizacja kompresji PPMd z szyfrowaniem AES256

`PpmdCompressionSettings` definiuje kolejność i zużycie pamięci dla algorytmu PPMd.  
`AesEncryptionSettings` zapewnia szyfrowanie AES‑256 dla wpisów w archiwum.

**Direct answer (40‑70 words):**  
Utwórz instancję `PpmdCompressionSettings`, połącz ją z obiektem `AesEncryptionSettings` zawierającym Twoje hasło i przekaż oba do `ArchiveEntrySettings`. Użyj tego obiektu ustawień przy konstruowaniu `Archive`; wynikowy zip będzie skompresowany PPMd i zabezpieczony hasłem bez dodatkowych wywołań.

`PpmdCompressionSettings` definiuje kolejność i zużycie pamięci dla algorytmu PPMd.`  

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

## Używanie ustawień kompresji Enhanced Deflate

### Krok 1: Inicjalizacja kompresji Enhanced Deflate z szyfrowaniem AES256

`EnhancedDeflateCompressionSettings` pozwala określić poziom kompresji, który równoważy szybkość i rozmiar.  
`AesEncryptionSettings` zapewnia szyfrowanie AES‑256 dla wpisów w archiwum.

**Direct answer (40‑70 words):**  
Utwórz `EnhancedDeflateCompressionSettings` z wybranym poziomem (0‑9), połącz go z `AesEncryptionSettings` i opakuj w `ArchiveEntrySettings`. Przekaż to do konstruktora `Archive` i dodaj pliki; archiwum zostanie utworzone z kompresją Enhanced Deflate i ochroną hasłem AES‑256 w jednym przebiegu.

`EnhancedDeflateCompressionSettings` pozwala określić poziom kompresji, który równoważy szybkość i rozmiar.`  

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

## Używanie ustawień Store Compression (store compression zip)

### Krok 1: Inicjalizacja Store Compression z tradycyjnym szyfrowaniem

`StoreCompressionSettings` instruuje Aspose.Zip, aby całkowicie pominąć kompresję, zachowując plik źródłowy bajt po bajcie.  
`TraditionalEncryptionSettings` stosuje starsze szyfrowanie ZipCrypto.

**Direct answer (40‑70 words):**  
Utwórz instancję `StoreCompressionSettings` (która nie wykonuje kompresji), połącz ją z `TraditionalEncryptionSettings` zawierającym Twoje hasło i opakuj oba w `ArchiveEntrySettings`. Przekaż to do konstruktora `Archive`; wynikowy zip będzie zawierał oryginalny plik bez kompresji, ale zabezpieczony hasłem.

`StoreCompressionSettings` instruuje Aspose.Zip, aby całkowicie pominąć kompresję, zachowując plik źródłowy bajt po bajcie.`  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Pro tip:** Dostosuj zmienną `dataDir`, aby wskazywała na rzeczywisty katalog roboczy, i ponownie użyj tej samej instancji `Archive`, jeśli musisz dodać wiele plików do jednego archiwum.

## Typowe problemy i rozwiązania
- **Błędy „File not found”** – Upewnij się, że `dataDir` kończy się separatorem ścieżki (`\\` lub `/`) oraz że `sample.txt` istnieje.  
- **Zużycie pamięci przy dużych plikach** – Użyj `ArchiveEntrySettings`, aby włączyć tryb strumieniowy, który zapisuje dane bezpośrednio do strumienia wyjściowego.  
- **Niezgodny poziom kompresji** – Niektóre algorytmy (np. LZMA) udostępniają dodatkowe właściwości, takie jak `DictionarySize`. Skonsultuj dokumentację API, jeśli potrzebujesz dokładniejszej kontroli.  
- **Hasło nie zastosowane** – Upewnij się, że obiekt ustawień szyfrowania jest przekazywany jako drugi argument do `ArchiveEntrySettings` w czasie konstrukcji, a nie po utworzeniu archiwum.  

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Zip dla .NET z innymi bibliotekami kompresji?**  
A: Aspose.Zip jest zaprojektowany do pracy z własnymi wbudowanymi algorytmami. Integracja z bibliotekami innych firm jest możliwa, ale wymaga własnej obsługi poza API Aspose.

**Q: Jak mogę dodać ochronę hasłem do zip utworzonego przy użyciu Aspose.Zip?**  
A: Przekaż `TraditionalEncryptionSettings` lub `AesEncryptionSettings` jako drugi argument do `ArchiveEntrySettings` przy konstruowaniu `Archive`. Zobacz [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/) po pełne przykłady.

**Q: Czy istnieje wersja próbna, którą mogę przetestować?**  
A: Tak, wersję próbną można uzyskać [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać pomoc społeczności lub zadać pytania?**  
A: Wsparcie i dyskusje społecznościowe znajdziesz na [forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

**Q: Czy mogę uzyskać tymczasową licencję do oceny?**  
A: Tak, tymczasową licencję można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Jak to pomaga w kompresji plików w ASP.NET?**  
A: Wywołując to samo API z kontrolera lub middleware ASP.NET, możesz kompresować pliki w locie przed ich wysłaniem do klienta, zmniejszając zużycie pasma i poprawiając postrzeganą wydajność.

**Q: Jaki jest najlepszy sposób na efektywną kompresję dużych plików?**  
A: Połącz tryb strumieniowy z kompresją LZMA i odpowiednim `DictionarySize`. To równoważy zużycie pamięci i współczynnik kompresji przy ogromnych zestawach danych.

**Last Updated:** 2026-06-09  
**Testowano z:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Aspose.Zip dla .NET - Ochrona hasłem archiwum Zip i przechowywanie wielu plików bez kompresji](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Utwórz zip chroniony hasłem dla katalogów .NET – Samouczek Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [zip wielu plików c# – Bezproblemowa kompresja z Aspose.Zip dla .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}