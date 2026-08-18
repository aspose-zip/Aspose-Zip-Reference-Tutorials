---
date: 2026-07-04
description: Dowiedz się, jak kompresować wiele plików tar przy użyciu Aspose.Zip
  for .NET i efektywnie tworzyć archiwa tar.lz.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Kompresja do TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak kompresować wiele plików tar przy użyciu Aspose.Zip for .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak kompresować wiele plików tar przy użyciu Aspose.Zip dla .NET

W nowoczesnym rozwoju .NET efektywne pakowanie plików może znacząco poprawić rozmiar wdrożenia i czasy transferu sieciowego. **Compress multiple files tar** jest częstym wymaganiem, gdy potrzebny jest lekki, skompresowany LZ‑algorytmem archiwum TAR do kopii zapasowych, dystrybucji lub przesyłania do chmury. W tym samouczku przeprowadzimy Cię przez przejrzysty, krok po kroku **przykład kompresji tar.lz** przy użyciu biblioteki Aspose.Zip, abyś mógł szybko utworzyć **archiwum tar.lz** w swoich aplikacjach.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip for .NET.  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowego przykładu.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę kompresować wiele plików jednocześnie?** Tak – po prostu dodaj więcej wpisów przed zapisaniem.  

## Jak kompresować wiele plików tar przy użyciu Aspose.Zip dla .NET?
Wczytaj swoje pliki źródłowe, utwórz instancję `TarArchive`, dodaj każdy plik za pomocą `CreateEntry` i zakończ wywołaniem `SaveLzipped`. Biblioteka obsługuje strukturę TAR i kompresję LZ wewnętrznie, więc otrzymujesz pojedynczy plik `*.tar.lz` w zaledwie kilku linijkach kodu. To podejście działa na Windows, Linux i macOS bez żadnych natywnych zależności.

## Czym jest kompresja tar.lz?
`tar.lz` to archiwum TAR skompresowane przy użyciu algorytmu LZMA (często określanego po prostu jako **LZ**). Łączy prostotę grupowania plików w TAR z wysokim współczynnikiem kompresji LZ, co czyni je idealnym do plików kopii zapasowych, dystrybucji pakietów lub wszelkich scenariuszy, w których liczy się przepustowość.

## Dlaczego warto używać Aspose.Zip dla .NET?
Aspose.Zip zapewnia czysto zarządzane, wieloplatformowe rozwiązanie, które tworzy archiwa TAR, ZIP i oparte na LZ bez zewnętrznych narzędzi, obsługuje ponad 30 formatów archiwów i zapewnia do 30 % lepszą kompresję dużych plików, jednocześnie oferując szczegółowe wyjątki dla solidnej obsługi błędów. Integruje się również bezproblemowo z frameworkami logowania .NET i udostępnia szczegółowe zdarzenia postępu.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Bibliotekę **Aspose.Zip for .NET** – pobierz ją z [tutaj](https://releases.aspose.com/zip/net/).  
- Folder zawierający pliki, które chcesz zarchiwizować. Ścieżka do tego folderu zostanie zapisana w zmiennej `dataDir` (ustawisz ją w Kroku 3).

## Importuj przestrzenie nazw
Dodaj wymagane przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć klasy, które będziemy używać.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak utworzyć archiwum tar.lz – przewodnik krok po kroku

### Krok 1: Kompresja pojedynczego pliku
Pierwszy przykład pokazuje najprostszy scenariusz – dodanie jednego pliku do archiwum TAR, a następnie zapisanie go jako plik **tar.lz**.

Klasa `TarArchive` reprezentuje kontener TAR, który może przechowywać wiele plików w jednym archiwum.  

**Wyjaśnienie**

- `new TarArchive()` tworzy pusty kontener TAR.  
- `CreateEntry` dodaje plik `alice29.txt` z Twojego `dataDir`.  
- `SaveLzipped` zapisuje archiwum na dysku i stosuje kompresję LZ, tworząc `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Krok 2: Kompresja wielu plików w jednym archiwum
Często będziesz musiał połączyć kilka plików razem. Po prostu wywołaj `CreateEntry` dla każdego pliku przed zapisaniem. To demonstruje **add files to tar lz** i skutecznie **compress multiple files tar**.

**Wyjaśnienie**

- Kod podąża tym samym schematem co Krok 1, ale dodaje drugi wpis (`lcet10.txt`).  
- Możesz powtarzać `CreateEntry` dowolną liczbę razy; biblioteka automatycznie obsługuje wewnętrzną strukturę TAR.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Krok 3: Określ katalog dokumentów
Zastąp symbol zastępczy rzeczywistą ścieżką, w której znajdują się Twoje pliki źródłowe. Ścieżka ta jest używana w powyższych przykładach.

**Wyjaśnienie**

- Ustaw `dataDir` na w pełni kwalifikowaną ścieżkę folderu, np. `@"C:\MyFiles\"`.  
- Przechowywanie katalogu w zmiennej sprawia, że kod jest wielokrotnego użytku i łatwiejszy w utrzymaniu.

```csharp
string dataDir = "Your Document Directory";
```

## Częste problemy i rozwiązywanie problemów
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| `FileNotFoundException` podczas uruchamiania przykładu | `dataDir` wskazuje na nieistniejący folder lub nazwa pliku jest błędnie napisana | Sprawdź ścieżkę i nazwy plików; użyj `Path.Combine` dla bezpieczeństwa. |
| Plik wyjściowy ma **0 KB** | `archive.SaveLzipped` został wywołany przed dodaniem jakichkolwiek wpisów | Upewnij się, że przynajmniej jedno wywołanie `CreateEntry` występuje przed `SaveLzipped`. |
| Kompresja wydaje się wolna | Duże pliki przy domyślnym rozmiarze bufora | Rozważ przetwarzanie plików w fragmentach lub użycie asynchronicznego I/O, jeśli wydajność jest krytyczna. |

## Podsumowanie
Teraz wiesz, **jak kompresować pliki tar.lz** przy użyciu Aspose.Zip dla .NET, niezależnie od tego, czy pracujesz z pojedynczym dokumentem, czy z kolekcją plików. Ten **przykład kompresji tar.lz** pokazuje czysty, gotowy do produkcji sposób **tworzenia archiwów tar lz**, które można łatwo przenosić lub przechowywać. Możesz kompresować pliki do tar.lz używając tego samego API, wywołując `SaveLzipped` po dodaniu wszystkich żądanych wpisów.

## Najczęściej zadawane pytania

**Q:** Czy mogę kompresować pliki dowolnego rozmiaru przy użyciu Aspose.Zip dla .NET?  
**A:** Tak, biblioteka obsługuje zarówno małe, jak i bardzo duże pliki; wystarczy zapewnić wystarczającą ilość pamięci i miejsca na dysku dla tymczasowej struktury TAR.

**Q:** Czy kod jest kompatybilny z najnowszą wersją Aspose.Zip?  
**A:** Przykład jest skierowany do bieżącej wersji; zawsze aktualizuj pakiet NuGet, aby uzyskać poprawki błędów i nowe funkcje.

**Q:** Czy istnieją kwestie licencyjne?  
**A:** Licencja komercyjna jest wymagana do użytku produkcyjnego. Zobacz szczegóły licencjonowania na [stronie Aspose](https://purchase.aspose.com/buy).

**Q:** Czy mogę używać tego w projekcie komercyjnym?  
**A:** Oczywiście – po uzyskaniu ważnej licencji możesz osadzić bibliotekę w dowolnej aplikacji komercyjnej.

**Q:** Gdzie mogę uzyskać pomoc, jeśli napotkam problemy?  
**A:** Odwiedź [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) w celu uzyskania wsparcia społeczności i oficjalnej pomocy.

---

**Ostatnia aktualizacja:** 2026-07-04  
**Testowano z:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Utwórz archiwum tar i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak skompresować tar i utworzyć TarBz2 przy użyciu Aspose.Zip dla .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Dodaj pliki do tar i utwórz archiwum tarxz przy użyciu Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}