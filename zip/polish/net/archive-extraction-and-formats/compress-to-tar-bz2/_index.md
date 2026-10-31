---
date: 2026-10-31
description: Dowiedz się, jak utworzyć archiwum tar i skompresować je do pliku TarBz2
  w .NET przy użyciu Aspose.Zip. Przewodnik krok po kroku pokazuje tworzenie tar,
  kompresję Bzip2 oraz wskazówki najlepszych praktyk.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: Kompresja do TarBz2
og_description: Dowiedz się, jak utworzyć archiwum tar i skompresować je do pliku
  TarBz2 przy użyciu Aspose.Zip dla .NET. Przewodnik krok po kroku obejmuje tworzenie
  tar, kompresję Bzip2 oraz wskazówki najlepszych praktyk.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: Utwórz archiwum tar i skompresuj do TarBz2 w .NET
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
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
title: Jak utworzyć archiwum tar i skompresować do formatu TarBz2 w .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć archiwum tar i skompresować do TarBz2 w .NET

W tym samouczku dowiesz się **jak tworzyć pliki archiwum tar** i następnie kompresować je do kompaktowego pakietu **TarBz2** przy użyciu biblioteki **Aspose.Zip** dla .NET. Niezależnie od tego, czy tworzysz narzędzie do tworzenia kopii zapasowych, przygotowujesz pakiety wdrożeniowe, czy potrzebujesz lekkiego formatu dystrybucji, poniższe kroki przeprowadzą Cię przez dodawanie plików do kontenera tar, stosowanie kompresji Bzip2 oraz zapisywanie końcowego pliku `.tar.bz2`.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip dla .NET  
- **Jak długo trwa implementacja?** Około 5‑10 minut  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa licencja do produkcji; dostępna jest darmowa wersja próbna  
- **Czy mogę kompresować wiele plików?** Tak – możesz dodać dowolną liczbę wpisów do archiwum tar  
- **Czy jest kompatybilny z .NET 6+?** Absolutnie, Aspose.Zip obsługuje .NET Framework oraz .NET Core/5/6  

## Czym jest archiwum TarBz2?

Plik TarBz2 łączy tradycyjny kontener **tar** (zachowujący strukturę katalogów i metadane plików) z kompresją **Bzip2**, co skutkuje wysoko skompresowanym pakietem `.tar.bz2`. Format ten jest popularny w systemach Unix‑like, ponieważ zapewnia dobrą równowagę między współczynnikiem kompresji a szybkością dekompresji.

## Dlaczego kompresować pliki do TarBz2 przy użyciu Aspose.Zip?

Aspose.Zip może wygenerować archiwum TarBz2 w **dwóch wywołaniach API**, jednocześnie efektywnie obsługując strumienie. Obsługuje **ponad 50 formatów archiwów i kompresji**, przetwarza pliki do **2 GB** bez ładowania całego archiwum do pamięci i działa na środowiskach .NET w Windows, Linux i macOS. Biblioteka daje także precyzyjną kontrolę nad nazwami wpisów, znacznikami czasu i poziomami kompresji, co czyni ją idealną zarówno dla narzędzi konsolowych, jak i usług sieciowych.

## Wymagania wstępne

- **Aspose.Zip dla .NET** – pobierz najnowszy pakiet z oficjalnej strony: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Katalog dokumentów** – folder zawierający pliki, które chcesz zarchiwizować. W przykładach odwołujemy się do niego zmienną `dataDir`.

> **Wskazówka:** Przechowuj pliki źródłowe w dedykowanym folderze, aby uniknąć przypadkowego dołączania niechcianych plików.

## Importuj przestrzenie nazw

Najpierw zaimportuj wymagane przestrzenie nazw, aby uzyskać dostęp do klas Tar i Bzip2 biblioteki Aspose.Zip.

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

> Zamień `"Your Document Directory"` na absolutną lub względną ścieżkę do swojego folderu źródłowego.

## Krok 2: dodaj pliki do tar i utwórz archiwum TarBz2

Klasa `TarArchive` reprezentuje pamięciowy kontener tar, natomiast `Bzip2Archive` kompresuje strumienie przy użyciu algorytmu Bzip2.  
Metoda `CreateEntry` dodaje nowy wpis pliku do archiwum tar.

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

- `CreateEntry` **dodaje pliki do tar** – możesz wywołać tę metodę dla każdego pliku, który ma znaleźć się w archiwum.  
- `bz2.SetSource(archive)` instruuje archiwum Bzip2, aby skompresować cały strumień tar.  
- `bz2.Save(...)` zapisuje końcowy plik **TarBz2** na dysku.

**Wskazówka:** Aby **dodać pliki do tar** masowo, po prostu powtórz `archive.CreateEntry` dla każdego pliku przed wywołaniem `bz2.Save`.

## Jak dodać pliki do tar?

Wczytaj katalog źródłowy, utwórz instancję `TarArchive`, dodaj każdy plik za pomocą `CreateEntry`, a następnie owiń strumień tar w `Bzip2Archive` i wywołaj `Save`. Ten dwustopniowy wzorzec pozwala dodać dowolną liczbę plików i wygenerować plik `.tar.bz2` w jednej płynnej operacji, eliminując potrzebę plików tymczasowych lub zewnętrznych narzędzi.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Błąd – plik nie znaleziony** | Nieprawidłowa ścieżka `dataDir` lub brak rozszerzenia pliku | Zweryfikuj pełną ścieżkę i upewnij się, że plik istnieje. |
| **Puste archiwum** | Brak wpisów przed wywołaniem `bz2.Save` | Dodaj przynajmniej jedno wywołanie `CreateEntry`. |
| **Odmowa dostępu** | Aplikacja nie ma uprawnień do zapisu w folderze wyjściowym | Uruchom aplikację z odpowiednimi prawami lub wybierz katalog zapisu. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Zip jest kompatybilny ze wszystkimi aplikacjami .NET?**  
O: Tak. Działa z .NET Framework, .NET Core, .NET 5/6 oraz nowszymi środowiskami uruchomieniowymi.

**P: Czy mogę kompresować wiele plików jednocześnie?**  
O: Absolutnie. Wywołaj `CreateEntry` dla każdego pliku przed zapisaniem archiwum.

**P: Gdzie mogę znaleźć dodatkową dokumentację?**  
O: Szczegółowe dokumenty dostępne są w **Aspose.Zip .NET API reference**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**P: Jak uzyskać tymczasową licencję dla Aspose.Zip?**  
O: Możesz **poprosić o tymczasową licencję** tutaj: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Tak, **pobierz wersję próbną z wypuszczeń Aspose**: [download a trial version](https://releases.aspose.com/).

Możesz również [pobrać wersję próbną](https://releases.aspose.com/).

## Podsumowanie

Teraz wiesz **jak utworzyć archiwum tar**, skompresować strumień tar przy użyciu Bzip2 i wygenerować **archiwum TarBz2** przy pomocy Aspose.Zip dla .NET. Podejście jest szybkie, oszczędne pod względem pamięci i działa na wszystkich nowoczesnych platformach .NET. Śmiało eksperymentuj z większymi zestawami plików, własnymi nazwami wpisów lub integruj kod w własnych procesach tworzenia kopii zapasowych czy wdrożeń.

Jeśli napotkasz jakiekolwiek trudności, społeczność Aspose.Zip jest gotowa pomóc — wystarczy przejść na **forum wsparcia Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Ostatnia aktualizacja:** 2026-10-31  
**Testowano z:** Aspose.Zip dla .NET (najnowsze wydanie)  
**Autor:** Aspose  

## Powiązane samouczki

- [Utwórz archiwum tar i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Dodaj pliki do tar i utwórz archiwum tarxz przy użyciu Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Dodaj pliki do tar i skompresuj do TarZ przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}