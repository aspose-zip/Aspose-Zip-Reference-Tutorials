---
date: 2026-02-23
description: Naucz się kompresować wiele plików tar przy użyciu Aspose.Zip dla .NET
  i efektywnie tworzyć archiwa tar.lz.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak skompresować wiele plików tar przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak kompresować wiele plików tar przy użyciu Aspose.Zip dla .NET

W nowoczesnym rozwoju .NET efektywne pakowanie plików może znacząco poprawić rozmiar wdrożenia i czasy przesyłu sieciowego. **kompresować wiele plików tar** jest częstym wymaganiem, gdy potrzebny jest lekki archiwum TAR skompresowane LZ‑kompresją do kopii zapasowych, dystrybucji lub przesyłania do chmury. W tym samouczku przeprowadzimy Cię krok po kroku przez **przykład kompresji tar.lz** przy użyciu biblioteki Aspose.Zip, abyś mógł szybko utworzyć **archiwum tar.lz** w swoich aplikacjach.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip for .NET.  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowego przykładu.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę kompresować wiele plików jednocześnie?** Tak – wystarczy dodać więcej wpisów przed zapisaniem.

## Jak kompresować wiele plików tar
Ta sekcja bezpośrednio odnosi się do głównego słowa kluczowego i pokazuje dokładne kroki, aby **kompresować wiele plików tar** przy użyciu Aspose.Zip. Podejście działa dla dowolnej liczby plików i można je łatwo dostosować do własnych struktur folderów.

## Czym jest kompresja tar.lz?
`tar.lz` to archiwum TAR skompresowane przy użyciu algorytmu LZMA (często określanego po prostu jako **LZ**). Łączy prostotę grupowania plików w TAR z wysokim współczynnikiem kompresji LZ, co czyni je idealnym do plików kopii zapasowych, dystrybucji pakietów lub wszelkich scenariuszy, w których liczy się przepustowość.

## Dlaczego używać Aspose.Zip dla .NET?
Aspose.Zip ukrywa szczegóły niskiego poziomu tworzenia archiwów, zapewniając czyste, obiektowo‑zorientowane API. Otrzymujesz:
* **Zero zewnętrznych zależności** – czysta implementacja .NET.  
* **Wsparcie wieloplatformowe** – działa na Windows, Linux i macOS.  
* **Wbudowana kompresja LZ** – nie wymaga instalacji dodatkowych narzędzi natywnych.  
* **Silne obsługiwanie błędów** – wyjątki są opisowe, co ułatwia debugowanie.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:
- **Bibliotekę Aspose.Zip for .NET** – pobierz ją z [tutaj](https://releases.aspose.com/zip/net/).  
- Folder zawierający pliki, które chcesz zarchiwizować. Ścieżka do tego folderu zostanie zapisana w zmiennej `dataDir` (ustawisz ją w Kroku 3).

## Importowanie przestrzeni nazw
Dodaj wymagane przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć klasy, które będziemy używać.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak utworzyć archiwum tar.lz – przewodnik krok po kroku

### Krok 1: Kompresuj pojedynczy plik
Pierwszy przykład pokazuje najprostszy scenariusz – dodanie jednego pliku do archiwum TAR, a następnie zapisanie go jako plik **tar.lz**.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Wyjaśnienie**
- `new TarArchive()` tworzy pusty kontener TAR.  
- `CreateEntry` dodaje plik `alice29.txt` z Twojego `dataDir`.  
- `SaveLzipped` zapisuje archiwum na dysku i stosuje kompresję LZ, tworząc `archive.tar.lz`.

### Krok 2: Kompresuj wiele plików w jednym archiwum
Często będziesz musiał połączyć kilka plików razem. Po prostu wywołaj `CreateEntry` dla każdego pliku przed zapisaniem. To pokazuje **dodawanie plików do tar lz** i skutecznie **kompresować wiele plików tar**.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Wyjaśnienie**
- Kod podąża tym samym schematem co Krok 1, ale dodaje drugi wpis (`lcet10.txt`).  
- Możesz powtarzać `CreateEntry` dowolną liczbę razy; biblioteka automatycznie obsługuje wewnętrzną strukturę TAR.

### Krok 3: Określ katalog dokumentów
Zastąp placeholder rzeczywistą ścieżką, w której znajdują się Twoje pliki źródłowe. Ścieżka ta jest używana w powyższych przykładach.

```csharp
string dataDir = "Your Document Directory";
```

**Wyjaśnienie**
- Ustaw `dataDir` na w pełni kwalifikowaną ścieżkę folderu, np. `@"C:\\MyFiles\\"`.  
- Przechowywanie katalogu w zmiennej sprawia, że kod jest wielokrotnego użytku i łatwiejszy w utrzymaniu.

## Częste pułapki i rozwiązywanie problemów
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| `FileNotFoundException` podczas uruchamiania przykładu | `dataDir` wskazuje na nieistniejący folder lub nazwa pliku jest błędna | Sprawdź ścieżkę i nazwy plików; użyj `Path.Combine` dla bezpieczeństwa. |
| Plik wyjściowy ma **0 KB** | `archive.SaveLzipped` został wywołany przed dodaniem jakichkolwiek wpisów | Upewnij się, że przynajmniej jedno wywołanie `CreateEntry` poprzedza `SaveLzipped`. |
| Kompresja wydaje się wolna | Duże pliki przy domyślnym rozmiarze bufora | Rozważ przetwarzanie plików w fragmentach lub użycie asynchronicznego I/O, jeśli wydajność jest krytyczna. |

## Podsumowanie
Teraz wiesz, **jak kompresować pliki tar.lz** przy użyciu Aspose.Zip dla .NET, niezależnie od tego, czy pracujesz z pojedynczym dokumentem, czy z kolekcją plików. Ten **przykład kompresji tar.lz** pokazuje czysty, gotowy do produkcji sposób **tworzenia archiwów tar lz**, które można łatwo przenosić lub przechowywać.

## Najczęściej zadawane pytania

**Q:** Czy mogę kompresować pliki dowolnego rozmiaru przy użyciu Aspose.Zip dla .NET?  
**A:** Tak, biblioteka obsługuje zarówno małe, jak i bardzo duże pliki; wystarczy zapewnić wystarczającą pamięć i miejsce na dysku dla tymczasowej struktury TAR.

**Q:** Czy kod jest kompatybilny z najnowszą wersją Aspose.Zip?  
**A:** Przykład jest skierowany do bieżącej wersji; zawsze aktualizuj pakiet NuGet, aby uzyskać poprawki błędów i nowe funkcje.

**Q:** Czy istnieją kwestie licencyjne?  
**A:** Licencja komercyjna jest wymagana do użytku produkcyjnego. Zobacz szczegóły licencjonowania na [stronie Aspose](https://purchase.aspose.com/buy).

**Q:** Czy mogę używać tego w projekcie komercyjnym?  
**A:** Oczywiście – po uzyskaniu ważnej licencji możesz osadzić bibliotekę w dowolnej aplikacji komercyjnej.

**Q:** Gdzie mogę uzyskać pomoc, jeśli napotkam problemy?  
**A:** Odwiedź [forum Aspose.Zip](https://forum.aspose.com/c/zip/37), aby uzyskać wsparcie społeczności i oficjalną pomoc.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-23  
**Testowano z:** Aspose.Zip for .NET (najnowsze wydanie)  
**Autor:** Aspose