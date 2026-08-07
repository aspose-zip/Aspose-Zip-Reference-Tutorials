---
date: 2026-08-07
description: Dowiedz się, jak dodać pliki do tar i wygenerować archiwum TarBz2 w .NET
  przy użyciu Aspose.Zip. Przewodnik krok po kroku pokazuje tworzenie tar, kompresję
  Bzip2 oraz wskazówki najlepszych praktyk.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Kompresja do TarBz2
og_description: Dodaj pliki do tar i wygeneruj archiwum TarBz2 w .NET przy użyciu
  Aspose.Zip. Ten przewodnik obejmuje tworzenie tar, kompresję Bzip2 oraz wskazówki
  rozwiązywania problemów.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Dodaj pliki do tar i utwórz archiwum TarBz2 przy użyciu Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Dodaj pliki do tar i utwórz archiwum TarBz2 przy użyciu Aspose.Zip
url: /pl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj pliki do tar i utwórz archiwum TarBz2 przy użyciu Aspose.Zip

W tym samouczku odkryjesz **jak dodać pliki do tar** archiwów i przekształcić je w kompaktowy plik **TarBz2** przy użyciu biblioteki **Aspose.Zip** dla .NET. Niezależnie od tego, czy tworzysz narzędzie do tworzenia kopii zapasowych, publikujesz pakiety wdrożeniowe, czy potrzebujesz lekkiego pakietu do dystrybucji, poniższe kroki przeprowadzą Cię przez dodawanie plików do kontenera tar, zastosowanie kompresji Bzip2 i wygenerowanie gotowego do udostępnienia archiwum.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip for .NET  
- **Jak długo trwa implementacja?** Około 5‑10 minut  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa licencja do produkcji; dostępna jest bezpłatna wersja próbna  
- **Czy mogę kompresować wiele plików?** Tak – dodaj dowolną liczbę wpisów do archiwum tar  
- **Czy jest kompatybilny z .NET 6+?** Zdecydowanie tak, Aspose.Zip obsługuje .NET Framework oraz .NET Core/5/6  

## Czym jest archiwum TarBz2?

Plik TarBz2 łączy tradycyjny kontener **tar** (który zachowuje strukturę katalogów i metadane plików) z kompresją **Bzip2**, co skutkuje wysoko skompresowanym pakietem `.tar.bz2`. Ten format jest popularny w systemach podobnych do Unix, ponieważ zapewnia dobrą równowagę między współczynnikiem kompresji a szybkością dekompresji.

## Dlaczego kompresować pliki do TarBz2 przy użyciu Aspose.Zip?

Aspose.Zip może wygenerować archiwum TarBz2 w **dwóch wywołaniach API**, jednocześnie efektywnie obsługując strumienie. Obsługuje **ponad 50 formatów archiwów i kompresji**, przetwarza pliki do **2 GB** bez ładowania całego archiwum do pamięci i działa na środowiskach .NET w Windows, Linux i macOS. Biblioteka daje także precyzyjną kontrolę nad nazwami wpisów, znacznikami czasu i poziomami kompresji, co czyni ją idealną zarówno dla narzędzi konsolowych, jak i usług internetowych.

## Wymagania wstępne

- **Aspose.Zip for .NET** – pobierz najnowszy pakiet ze strony oficjalnej: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – folder zawierający pliki, które chcesz zarchiwizować. W przykładach odwołujemy się do niego zmienną `dataDir`.

> **Pro tip:** Trzymaj pliki źródłowe w dedykowanym folderze, aby uniknąć przypadkowego dołączenia niechcianych plików.

## Importuj przestrzenie nazw

Najpierw zaimportuj wymagane przestrzenie nazw, aby mieć dostęp do klas Tar i Bzip2 biblioteki Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Krok 1: ustaw katalog dokumentu

Zdefiniuj ścieżkę wskazującą na folder zawierający pliki, które chcesz zarchiwizować.

```csharp
string dataDir = "Your Document Directory";
```

> Zastąp `"Your Document Directory"` absolutną lub względną ścieżką do swojego folderu źródłowego.

## Krok 2: dodaj pliki do tar i utwórz archiwum TarBz2

`TarArchive` reprezentuje pamięciowy kontener tar, który może przechowywać wiele wpisów plików.  
`Bzip2Archive` kompresuje strumień przy użyciu algorytmu Bzip2.  
Metoda `CreateEntry` dodaje plik do archiwum tar jako nowy wpis.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **dodaje pliki do tar** – możesz wywołać tę metodę dla każdego pliku, którego potrzebujesz w archiwum.  
- `bz2.SetSource(archive)` informuje archiwum Bzip2, aby skompresowało cały strumień tar.  
- `bz2.Save(...)` zapisuje ostateczny plik **TarBz2** na dysku.

**Wskazówka:** Aby **dodać pliki do tar** masowo, po prostu powtórz `archive.CreateEntry` dla każdego pliku przed wywołaniem `bz2.Save`.

## Jak dodać pliki do tar?

Wczytaj katalog źródłowy, utwórz instancję `TarArchive`, dodaj każdy plik za pomocą `CreateEntry`, a następnie otocz strumień tar w `Bzip2Archive` i wywołaj `Save`. Ten dwustopniowy wzorzec dodaje dowolną liczbę plików i generuje plik `.tar.bz2` w jednym płynnym przepływie, eliminując potrzebę plików tymczasowych lub zewnętrznych narzędzi.

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| **Błąd: plik nie znaleziony** | Nieprawidłowa ścieżka `dataDir` lub brak rozszerzenia pliku | Sprawdź pełną ścieżkę i upewnij się, że plik istnieje. |
| **Puste archiwum** | Brak wpisów dodanych przed `bz2.Save` | Dodaj przynajmniej jedno wywołanie `CreateEntry`. |
| **Odmowa dostępu** | Aplikacja nie ma uprawnień do zapisu w folderze wyjściowym | Uruchom aplikację z odpowiednimi uprawnieniami lub wybierz zapisywalny katalog. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Zip jest kompatybilny ze wszystkimi aplikacjami .NET?**  
A: Tak. Działa z .NET Framework, .NET Core, .NET 5/6 i nowszymi środowiskami uruchomieniowymi.

**P: Czy mogę kompresować wiele plików jednocześnie?**  
A: Zdecydowanie tak. Wywołaj `CreateEntry` dla każdego pliku przed zapisaniem archiwum.

**P: Gdzie mogę znaleźć dodatkową dokumentację?**  
A: Szczegółowa dokumentacja jest dostępna w **referencji API Aspose.Zip .NET**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**P: Jak uzyskać tymczasową licencję dla Aspose.Zip?**  
A: Możesz **poprosić o tymczasową licencję** tutaj: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**P: Czy dostępna jest bezpłatna wersja próbna?**  
A: Tak, **pobierz wersję próbną z wydań Aspose**: [download a trial version](https://releases.aspose.com/).

## Zakończenie

Teraz wiesz **jak dodać pliki do tar**, skompresować strumień tar przy użyciu Bzip2 i wygenerować archiwum **TarBz2** przy pomocy Aspose.Zip dla .NET. Podejście jest szybkie, oszczędne pod względem pamięci i działa na wszystkich nowoczesnych platformach .NET. Śmiało eksperymentuj z większymi zestawami plików, niestandardowymi nazwami wpisów lub zintegrować kod ze swoimi własnymi procesami tworzenia kopii zapasowych lub wdrożeń.

Jeśli napotkasz jakiekolwiek problemy, społeczność Aspose.Zip jest gotowa pomóc — po prostu przejdź do **forum wsparcia Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Ostatnia aktualizacja:** 2026-08-07  
**Testowano z:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Utwórz archiwum tar i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Dodaj pliki do tar i utwórz archiwum tarxz przy użyciu Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Dodaj pliki do tar i skompresuj do TarZ przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}