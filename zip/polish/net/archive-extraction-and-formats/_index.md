---
date: 2026-06-19
description: Dowiedz się, jak kompresować pliki tar, tworzyć archiwa targz i wyodrębniać
  chronione hasłem pliki zip przy użyciu Aspose.Zip dla .NET – zwiększając wydajność
  przechowywania i bezpieczeństwo.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Ekstrakcja archiwów i formaty
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak kompresować pliki Tar przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak kompresować pliki Tar przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

W tym przewodniku odkryjesz **jak kompresować tar** przy użyciu Aspose.Zip dla .NET, nauczysz się tworzyć archiwa TarGz oraz zobaczysz, jak rozpakowywać chronione hasłem archiwa zip. Efektywna obsługa archiwów to podstawowa umiejętność współczesnych programistów .NET — niezależnie od tego, czy tworzysz usługę tworzenia kopii zapasowych, klienta przechowywania w chmurze, czy potok przetwarzania danych, opanowanie tych formatów obniża koszty przechowywania, przyspiesza transfery i chroni wrażliwe dane.

## Szybkie odpowiedzi
- **Co to jest TarBz2?** Skompresowany archiwum, które łączy pakowanie TAR z kompresją BZIP2 dla wysokich współczynników kompresji.  
- **Dlaczego wybrać Aspose.Zip dla .NET?** Oferuje jednorodne, płynne API do tworzenia i rozpakowywania wielu formatów archiwów bez zewnętrznych zależności.  
- **Czy mogę utworzyć archiwum TarGz?** Tak – Aspose.Zip obsługuje TarGz, TarLz, TarXz, TarZ i inne.  
- **Jak rozpakować chronione hasłem archiwum zip?** Użyj właściwości `Password` w obiekcie `ArchiveEntry` podczas rozpakowywania.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest licencja komercyjna do produkcji; dostępna jest bezpłatna wersja próbna do oceny.

## Co to jest kompresja Tar?
Tar (Tape Archive) jest formatem kontenera, który grupuje wiele plików i katalogów w jeden strumień bez kompresji. Gdy zastosujesz algorytm kompresji, taki jak BZIP2, GZip, LZMA lub XZ, otrzymujesz **archiwum oparte na tar**, np. `.tar.bz2`, `.tar.gz`, `.tar.lz` itp. Formaty te są szeroko wspierane w systemach Linux, macOS i Windows, co czyni je idealnymi do wymiany danych między platformami.

## Dlaczego używać Aspose.Zip dla .NET do obsługi tych formatów?
Aspose.Zip zapewnia **zunifikowane, wolne od zależności API**, które obsługuje ponad 50 formatów archiwów i kompresji, w tym TarBz2, TarGz, TarLz, TarXz i TarZ. Działa na Windows, Linux i macOS, a jego architektura oparta na strumieniach utrzymuje zużycie pamięci poniżej 10 MB nawet przy archiwach wielokrotnie przekraczających setki megabajtów. Ochrona hasłem jest wbudowana, umożliwiając szyfrowanie poszczególnych wpisów bez dodatkowych bibliotek.

## Prerequisites
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, or .NET 5–10.  
- Aspose.Zip for .NET NuGet package installed (`Install-Package Aspose.Zip`).  
- Podstawowa znajomość operacji I/O w C# oraz systemu projektów .NET.

## Przewodnik krok po kroku

### Jak kompresować pliki Tar – Bezpośrednia odpowiedź
`Archive` reprezentuje plik archiwum i udostępnia metody do dodawania wpisów oraz zapisywania.  
Utwórz instancję `Archive`, dodaj pliki, które chcesz spakować, ustaw `CompressionType.BZip2` i wywołaj `Save` z `ArchiveFormat.TarBz2`. Biblioteka zapisuje kontener TAR i kompresuje go w jednym przebiegu strumieniowym, więc nigdy nie musisz ładować całego archiwum do pamięci.

```csharp
Archive archive = new Archive();
archive.AddAll(@"C:\MyFolder");
archive.CompressionType = CompressionType.BZip2;
archive.Save("output.tar.bz2", ArchiveFormat.TarBz2);
```

### Krok 1: Wybierz potrzebny format archiwum
Zdecyduj, który format oparty na tar najlepiej odpowiada Twoim wymaganiom dotyczącym stosunku kompresji do szybkości:

- **TarBz2** – Najwyższy współczynnik kompresji (≈30 % mniejszy niż TarGz), ale wolniejszy.  
- **TarGz** – Dobre połączenie szybkości i rozmiaru; idealny dla większości scenariuszy przechowywania w chmurze.  
- **TarLz / TarXz** – Bardzo wysoka kompresja przy umiarkowanej szybkości, przydatna do archiwizacji.  
- **TarZ** – Starszy format zapewniający kompatybilność ze starszymi narzędziami Unix.

### Krok 2: Utwórz nową instancję `Archive`
`Archive` jest obiektem najwyższego poziomu, który reprezentuje pojedynczy plik archiwum w pamięci.  

Klasa `Archive` zarządza procesem pakowania i kompresji, udostępniając metody do dodawania wpisów i zapisu finalnego pliku.

### Krok 3: Dodaj pliki i foldery
Możesz dodać cały drzewo katalogów przy pomocy `AddAll` lub pojedyncze pliki przy pomocy `AddFile`. Zachowanie oryginalnej struktury katalogów jest tak proste, jak podanie ścieżki bazowego katalogu.

### Krok 4: Ustaw żądany typ kompresji
`CompressionType` wylicza obsługiwane algorytmy.  

`CompressionType` definiuje algorytm (BZip2, GZip, LZMA, XZ itp.), który zostanie zastosowany do strumienia TAR podczas zapisu.

### Krok 5: Zapisz archiwum
`ArchiveFormat` to zestaw wyliczeń (np. `TarBz2`, `TarGz`), który informuje pisarz, jaki kontener i kompresję użyć.  

Wywołanie `Save` zapisuje archiwum na dysku w wybranym formacie.

### Krok 6: Rozpakowywanie archiwów z hasłami
`ArchiveEntry` reprezentuje pojedynczy plik lub katalog w archiwum.  

Aby rozpakować chronione hasłem zip, otwórz archiwum, znajdź każdy `ArchiveEntry`, przypisz jego właściwość `Password` i wywołaj `Extract`. Ten model haseł per‑entry pozwala chronić poszczególne pliki w jednym zipie.

### Krok 7: Zweryfikuj wynik
Po rozpakowaniu porównaj rozmiary plików i sumy kontrolne SHA‑256, aby potwierdzić, że archiwum zachowało integralność danych po pełnym cyklu.

## Typowe przypadki użycia
- **Narzędzia do tworzenia kopii zapasowych** – Przechowuj codzienne kopie jako `.tar.bz2`, aby zmniejszyć koszty przechowywania nawet o 30 %.  
- **Wymiana danych między platformami** – Formaty oparte na Tar są natywnie obsługiwane przez narzędzia Linux, macOS i Windows.  
- **Bezpieczna dystrybucja** – Przypisz hasła do wrażliwych wpisów, spełniając wymagania zgodności bez dodatkowych narzędzi szyfrujących.

## Rozwiązywanie problemów i wskazówki
- **Duże archiwa** – Preferuj API strumieniowe (`Archive.CreateEntryFromFile`), aby utrzymać niskie zużycie pamięci.  
- **Niezgodności haseł** – Hasło ustawione dla każdego `ArchiveEntry` musi dokładnie pasować; w przeciwnym razie zostanie rzucony `InvalidPasswordException`.  
- **Poziom kompresji** – BZIP2 nie udostępnia własnych poziomów; jeśli potrzebna jest większa kontrola, przełącz się na LZMA (`CompressionType.LZMA`) lub XZ (`CompressionType.XZ`).  

## Najczęściej zadawane pytania

**Q: Jak utworzyć archiwum TarGz?**  
A: Ustaw `CompressionType.GZip` i użyj `ArchiveFormat.TarGz` przy wywołaniu `Save`. To spowoduje utworzenie pliku `.tar.gz` w jednym kroku.

**Q: Czy mogę rozpakować chronione hasłem archiwum bez znajomości hasła?**  
A: Nie. Każdy wpis musi otrzymać prawidłowe hasło; w przeciwnym razie rozpakowywanie zakończy się `InvalidPasswordException`.

**Q: Czy Aspose.Zip obsługuje rozpakowywanie archiwów z różnymi hasłami per entry?**  
A: Tak. Przypisz hasło do każdego `ArchiveEntry` indywidualnie przed wywołaniem `Extract`.

**Q: Który format zapewnia najlepszą kompresję?**  
A: TarBz2 zazwyczaj daje najmniejszy rozmiar, następnie TarLz i TarXz. TarGz oferuje szybszą, wciąż skuteczną alternatywę.

**Q: Czy istnieje limit liczby plików, które mogę dodać do archiwum TAR?**  
A: Praktycznie brak, ale bardzo duże archiwa (>10 GB) mogą skorzystać z podziału na części, co ułatwia ich obsługę.

## Samouczki dotyczące rozpakowywania archiwów i formatów
### [Kompresowanie plików do TarBz2 przy użyciu Aspose.Zip dla .NET](./compress-to-tar-bz2/)
Dowiedz się, jak kompresować pliki do formatu TarBz2 w .NET przy użyciu Aspose.Zip. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby efektywnie kompresować pliki.  
### [Kompresowanie do TarGz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-gz/)
Poznaj efektywną kompresję plików w .NET z Aspose.Zip. Kompresuj do TarGz bez wysiłku.  
### [Kompresowanie do TarLz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-lz/)
Łatwo kompresuj pliki w .NET z Aspose.Zip. Naucz się tworzyć archiwa TarLz krok po kroku.  
### [Kompresowanie do TarXz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-xz/)
Dowiedz się, jak kompresować pliki do formatu TarXz w .NET przy użyciu Aspose.Zip. Skorzystaj z naszego przewodnika, aby efektywnie przechowywać i przesyłać dane.  
### [Kompresowanie do TarZ przy użyciu Aspose.Zip dla .NET](./compress-to-tar-z/)
Poznaj krok po kroku kompresję do TarZ przy użyciu Aspose.Zip dla .NET. Efektywna obsługa plików dla Twoich projektów .NET.  
### [Rozpakowywanie wpisów archiwum z różnymi hasłami w Aspose.Zip dla .NET](./extract-archive-different-passwords/)
Dowiedz się, jak rozpakowywać wpisy archiwum z różnymi hasłami w Aspose.Zip dla .NET. Zwiększ bezpieczeństwo i elastyczność w swoich aplikacjach.

---

**Ostatnia aktualizacja:** 2026-06-19  
**Testowano z:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz archiwum tar i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak kompresować tar i tworzyć TarBz2 przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Dodaj pliki do tar i utwórz archiwum tarxz przy użyciu Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}