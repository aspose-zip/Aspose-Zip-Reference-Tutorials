---
date: 2026-10-25
description: Dowiedz się, jak wyodrębnić hasło zip i ustawić compression algorithm
  podczas kompresji plików tar przy użyciu Aspose.Zip dla .NET, zwiększając storage
  efficiency i security.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Ekstrakcja archiwów i formaty
og_description: Dowiedz się, jak wyodrębnić hasło zip i ustawić compression algorithm
  podczas kompresji plików tar przy użyciu Aspose.Zip dla .NET, zwiększając storage
  efficiency i security.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Wyodrębnij hasło zip i kompresuj pliki tar przy użyciu Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Wyodrębnij hasło zip i kompresuj pliki tar przy użyciu Aspose.Zip
url: /pl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wyodrębnianie hasła zip i kompresowanie plików tar przy użyciu Aspose.Zip

## Wprowadzenie

W tym przewodniku odkryjesz techniki **extract zip password**, dowiesz się, jak ustawić algorytm kompresji przy tworzeniu archiwów opartych na tar, oraz zobaczysz, jak budować formaty TarGz, TarBz2 i inne przy użyciu Aspose.Zip dla .NET. Niezależnie od tego, czy tworzysz usługę tworzenia kopii zapasowych, klienta przechowywania w chmurze, czy potok przetwarzania danych, opanowanie tych operacji zmniejsza koszty przechowywania, przyspiesza transfery i zabezpiecza wrażliwe pliki.

## Szybkie odpowiedzi
- **Czym jest TarBz2?** Skompresowane archiwum, które łączy pakowanie TAR z kompresją BZIP2, zapewniając wysokie współczynniki kompresji.  
- **Dlaczego wybrać Aspose.Zip dla .NET?** Obsługuje ponad 50 formatów archiwów i kompresji, działa na Windows, Linux i macOS oraz utrzymuje zużycie pamięci poniżej 10 MB dla archiwów wielokrotnie setek megabajtów.  
- **Czy mogę utworzyć archiwum TarGz?** Tak – Aspose.Zip oferuje TarGz, TarLz, TarXz, TarZ i inne.  
- **Jak wyodrębnić chronione hasłem archiwum zip?** Ustaw właściwość `Password` dla każdego `ArchiveEntry` przed wywołaniem `Extract`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Licencja komercyjna jest wymagana w środowisku produkcyjnym; dostępna jest bezpłatna wersja próbna do oceny.

## Czym jest kompresja tar?

Kompresja tar łączy kontener TAR z algorytmem kompresji, takim jak BZIP2, GZIP, LZMA lub XZ. Wynikiem jest pojedynczy plik (np. `.tar.gz`, `.tar.bz2`), który można rozpakować na Linux, macOS i Windows. Zachowuje on oryginalną hierarchię katalogów, umożliwia losowy dostęp do wyodrębniania i jest szeroko wspierany przez narzędzia wiersza poleceń oraz biblioteki programistyczne, co czyni go idealnym do wieloplatformowej dystrybucji i archiwizacji.

## Dlaczego używać Aspose.Zip dla .NET do obsługi tych formatów?

Aspose.Zip zapewnia jednolite, niezależne od zależności API, które obsługuje **ponad 50** formatów archiwów i kompresji, w tym wszystkie główne typy oparte na tar. Jego architektura strumieniowa przetwarza archiwa większe niż 10 GB, utrzymując zużycie RAM poniżej 10 MB, co czyni go idealnym dla obciążeń serwerowych o wysokiej przepustowości.  

**Bezpośrednia odpowiedź:** Używasz Aspose.Zip, ponieważ pozwala tworzyć, kompresować i wyodrębniać archiwa oparte na tar oraz chronione hasłem pliki zip przy użyciu jednej płynnej API, bez zewnętrznych narzędzi, obsługując jednocześnie archiwa wielogigabajtowe w trybie pamięciooszczędnym.

## Wymagania wstępne
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 lub .NET 5–10.  
- Pakiet NuGet Aspose.Zip dla .NET (`Install-Package Aspose.Zip`).  
- Podstawowa znajomość operacji I/O w C# oraz systemu projektów .NET.

## Przewodnik krok po kroku

### Jak kompresować pliki tar – bezpośrednia odpowiedź
Utwórz instancję `Archive`, dodaj pliki, które chcesz spakować, ustaw `CompressionType.BZip2` (lub inny algorytm) i wywołaj `Save` z `ArchiveFormat.TarBz2`. Biblioteka zapisuje kontener TAR i kompresuje go w jednym przebiegu strumieniowym, więc nigdy nie ładujesz całego archiwum do pamięci.

### Krok 1: Wybierz potrzebny format archiwum
Zdecyduj, który format oparty na tar najlepiej odpowiada Twoim wymaganiom dotyczącym stosunku kompresji do szybkości:

- **TarBz2** – Najwyższy współczynnik kompresji (≈30 % mniejszy niż TarGz), ale wolniejszy.  
- **TarGz** – Dobry kompromis między szybkością a rozmiarem; idealny dla większości scenariuszy przechowywania w chmurze.  
- **TarLz / TarXz** – Bardzo wysoka kompresja przy umiarkowanej szybkości, przydatna do archiwizacji.  
- **TarZ** – Starszy format zapewniający kompatybilność ze starszymi narzędziami Unix.

### Krok 2: Utwórz nową instancję `Archive`
`Archive` reprezentuje pojedynczy plik archiwum i udostępnia metody do dodawania wpisów oraz zapisywania archiwum.  

Klasa `Archive` zarządza procesem pakowania i kompresji, udostępniając metody do dodawania wpisów i zapisu finalnego pliku.

### Krok 3: Dodaj pliki i foldery
Możesz dodać cały drzewo katalogów za pomocą `AddAll` lub pojedyncze pliki przy pomocy `AddFile`.  

`AddAll` dodaje całe drzewo katalogów do archiwum, zachowując jego strukturę.  
`AddFile` dodaje pojedynczy plik do archiwum. Zachowanie oryginalnej hierarchii folderów jest tak proste, jak podanie ścieżki bazowego katalogu.

### Krok 4: Ustaw żądany typ kompresji
Enum `CompressionType` określa algorytm kompresji stosowany do strumienia TAR.  

`CompressionType` wymienia obsługiwane algorytmy (BZip2, GZip, LZMA, XZ itp.), które zostaną zastosowane podczas zapisu.

### Krok 5: Zapisz archiwum
Enum `ArchiveFormat` wybiera kontener i kombinację kompresji dla pliku wyjściowego.  

Wywołanie `Save` zapisuje archiwum na dysku przy użyciu wybranego formatu.

### Krok 6: Rozpakowywanie archiwów z hasłami
`ArchiveEntry` reprezentuje pojedynczy plik lub katalog w archiwum.  

Aby wyodrębnić chronione hasłem zip, otwórz archiwum, znajdź każdy `ArchiveEntry`, przypisz mu właściwość `Password` i wywołaj `Extract`. Właściwość `Password` ustawia hasło deszyfrujące dla wpisu zip. Ten model hasła per wpis pozwala chronić poszczególne pliki w jednym archiwum zip.

### Krok 7: Zweryfikuj wynik
Po wyodrębnieniu porównaj rozmiary plików i sumy kontrolne SHA‑256, aby potwierdzić, że operacja archiwizacji i odtworzenia zachowała integralność danych.

## Typowe przypadki użycia
- **Narzędzia backupowe** – Przechowuj codzienne kopie zapasowe jako `.tar.bz2`, aby obniżyć koszty przechowywania nawet o 30 %.  
- **Wymiana danych między platformami** – Formaty oparte na tar są natywnie rozumiane przez narzędzia Linux, macOS i Windows.  
- **Bezpieczna dystrybucja** – Przypisuj hasła do wrażliwych wpisów, spełniając wymogi zgodności bez dodatkowych narzędzi szyfrujących.

## Rozwiązywanie problemów i wskazówki
- **Duże archiwa** – Używaj API strumieniowego (`Archive.CreateEntryFromFile`), aby utrzymać niskie zużycie pamięci.  
- **Niezgodność haseł** – Hasło ustawione dla każdego `ArchiveEntry` musi być dokładnie takie samo; w przeciwnym razie zostanie zgłoszony `InvalidPasswordException`.  
- **Poziom kompresji** – BZIP2 nie udostępnia poziomów niestandardowych; jeśli potrzebna jest większa kontrola, przełącz się na LZMA (`CompressionType.LZMA`) lub XZ (`CompressionType.XZ`).  

## Najczęściej zadawane pytania

**P: Jak utworzyć archiwum TarGz?**  
O: Ustaw `CompressionType.GZip` i użyj `ArchiveFormat.TarGz` podczas wywoływania `Save`. To spowoduje utworzenie pliku `.tar.gz` w jednym kroku.

**P: Czy mogę wyodrębnić archiwum chronione hasłem bez znajomości hasła?**  
O: Nie. Każdy wpis musi otrzymać prawidłowe hasło; w przeciwnym razie wyodrębnianie zakończy się `InvalidPasswordException`.

**P: Czy Aspose.Zip obsługuje wyodrębnianie archiwów z różnymi hasłami per wpis?**  
O: Tak. Przypisz hasło do każdego `ArchiveEntry` indywidualnie przed wywołaniem `Extract`.

**P: Który format zapewnia najlepszą kompresję?**  
O: TarBz2 zazwyczaj daje najmniejszy rozmiar, następnie TarLz i TarXz. TarGz oferuje szybszą, wciąż skuteczną alternatywę.

**P: Czy istnieje limit liczby plików, które można dodać do archiwum TAR?**  
O: Praktycznie brak, ale bardzo duże archiwa (>10 GB) mogą skorzystać z podziału na części w celu łatwiejszej obsługi.

## Samouczki dotyczące rozpakowywania archiwów i formatów
### [Kompresowanie plików do TarBz2 przy użyciu Aspose.Zip dla .NET](./compress-to-tar-bz2/)
Dowiedz się, jak kompresować pliki do formatu TarBz2 w .NET przy użyciu Aspose.Zip. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby efektywnie kompresować pliki.  
### [Kompresowanie do TarGz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-gz/)
Poznaj efektywną kompresję plików w .NET z Aspose.Zip. Kompresuj do TarGz bez wysiłku.  
### [Kompresowanie do TarLz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-lz/)
Łatwo kompresuj pliki w .NET przy użyciu Aspose.Zip. Naucz się tworzyć archiwa TarLz krok po kroku.  
### [Kompresowanie do TarXz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-xz/)
Dowiedz się, jak kompresować pliki do formatu TarXz w .NET przy użyciu Aspose.Zip. Skorzystaj z naszego przewodnika, aby zoptymalizować przechowywanie i transmisję.  
### [Kompresowanie do TarZ przy użyciu Aspose.Zip dla .NET](./compress-to-tar-z/)
Odkryj krok po kroku kompresję do TarZ przy użyciu Aspose.Zip dla .NET. Efektywna obsługa plików dla Twoich projektów .NET.  
### [Wyodrębnianie wpisów archiwum z różnymi hasłami w Aspose.Zip dla .NET](./extract-archive-different-passwords/)
Naucz się wyodrębniać wpisy archiwum z różnymi hasłami w Aspose.Zip dla .NET. Zwiększ bezpieczeństwo i elastyczność w swoich aplikacjach.

## Powiązane samouczki

- [Utwórz archiwum tar i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak skompresować tar i utworzyć TarBz2 przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Dodaj pliki do tar i utwórz archiwum tarxz przy użyciu Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Ostatnia aktualizacja:** 2026-10-25  
**Testowano z:** Aspose.Zip dla .NET 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}