---
date: 2025-12-09
description: Dowiedz się, jak kompresować katalog przy użyciu Aspose.Zip dla .NET
  i efektywnie tworzyć archiwa zip w .NET. Optymalizuj miejsce na dysku w swoich aplikacjach
  .NET.
linktitle: How to Compress a Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak skompresować katalog przy użyciu Aspose.Zip dla .NET
url: /pl/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bezproblemowa kompresja katalogu przy użyciu Aspose.Zip dla .NET

W tym samouczku pokażemy, **jak skompresować katalog** przy użyciu Aspose.Zip dla .NET, potężnego narzędzia do zarządzania dużymi zestawami danych i oszczędzania miejsca na dysku. Niezależnie od tego, czy tworzysz aplikację desktopową, czy usługę w chmurze, efektywna kompresja folderów może znacząco poprawić wydajność i obniżyć koszty. Przejdziemy krok po kroku, wyjaśnimy logikę kodu i wskażemy typowe pułapki, abyś mógł zastosować tę technikę z pewnością.

## Szybkie odpowiedzi
- **Co robi Aspose.Zip?** Udostępnia prosty interfejs .NET API do tworzenia i rozpakowywania archiwów ZIP bez zewnętrznych zależności.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut dla podstawowej kompresji katalogu.  
- **Które wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6+.  
- **Czy potrzebna jest licencja do produkcji?** Tak, do użytku produkcyjnego wymagana jest licencja komercyjna.  
- **Czy mogę skompresować wiele folderów jednocześnie?** Oczywiście — użyj metody `CreateEntries` na dowolnej kolekcji `DirectoryInfo`.

## Wprowadzenie

Aspose.Zip dla .NET to potężna biblioteka, która umożliwia programistom .NET płynną pracę z plikami i katalogami skompresowanymi. Niezależnie od tego, czy pracujesz z dużymi zestawami danych, czy potrzebujesz **generować archiwa zip w stylu c#**, Aspose.Zip oferuje solidny zestaw funkcji do zadań kompresji i dekompresji.

## Co to jest „jak skompresować katalog”?

Kompresowanie katalogu oznacza pobranie wszystkich plików i podfolderów w danym folderze i spakowanie ich do jednego archiwum ZIP. Zmniejsza to całkowity rozmiar, upraszcza transfer i zachowuje pierwotną strukturę folderów.

## Dlaczego używać Aspose.Zip do tego zadania?

- **Szybkość i wydajność:** Zoptymalizowane algorytmy szybko obsługują duże foldery.  
- **Czysty .NET:** Nie wymaga natywnych binarek ani narzędzi firm trzecich.  
- **Bogaty zestaw funkcji:** Obsługuje ochronę hasłem, strumieniowanie i dynamiczne dodawanie wpisów — idealny dla scenariuszy **zip multiple files .net**.  
- **Spójne API:** Działa tak samo w .NET Framework, .NET Core i .NET 5/6.

## Wymagania wstępne

- **Aspose.Zip for .NET** – pobierz go [tutaj](https://releases.aspose.com/zip/net/).  
- **Środowisko programistyczne** – Visual Studio, Rider lub dowolne IDE obsługujące C#.  
- **Katalog dokumentów** – zamień `"Your Document Directory"` w kodzie na ścieżkę do folderu, który chcesz skompresować.  
- **Dokumentacja referencyjna** – zapoznaj się z oficjalną dokumentacją [tutaj](https://reference.aspose.com/zip/net/).

## Importowanie przestrzeni nazw

Zacznij od zaimportowania niezbędnych przestrzeni nazw. Dają one dostęp do podstawowych klas kompresji.

```csharp
using Aspose.Zip;
using System.IO;
```

## Jak spakować folder przy użyciu Aspose.Zip

Poniżej znajduje się prosty przykład, który demonstruje **jak spakować folder**. Ten sam wzorzec można rozszerzyć na **zip multiple files .net** lub na tworzenie niestandardowych struktur archiwów.

### Krok 1: Zainicjalizuj katalog dokumentów

Ustaw zmienną `dataDir` na ścieżkę katalogu, który chcesz skompresować.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Utwórz pliki wyjściowe ZIP

Otwórz dwa obiekty `FileStream` dla wyjściowych plików ZIP. Pokazuje to, jak można wygenerować więcej niż jedno archiwum z tego samego źródła — przydatne przy wersjonowanych kopiach zapasowych.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Krok 3: Skompresuj katalog

Użyj klasy `Archive`, aby dodać każdy wpis z docelowego folderu. Przykład używa przykładowego folderu o nazwie **CanterburyCorpus**, ale możesz wskazać dowolny katalog.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Wskazówka:** Jeśli potrzebujesz **create zip archive .net** z określonym poziomem kompresji, ustaw `archive.CompressionLevel` przed wywołaniem `Save`.

## Typowe problemy i rozwiązania

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Pusty plik ZIP | `dataDir` wskazuje na niewłaściwy folder lub brak końcowego ukośnika | Sprawdź ścieżkę i upewnij się, że folder zawiera pliki |
| `UnauthorizedAccessException` | Aplikacja nie ma uprawnień do systemu plików | Uruchom Visual Studio jako administrator lub przyznaj prawa odczytu/zapisu |
| Wysokie zużycie pamięci przy dużych katalogach | Ładowanie wszystkich wpisów do pamięci jednocześnie | Użyj `Archive.CreateEntryFromFile` w pętli, aby strumieniowo przetwarzać pliki pojedynczo |

## Najczęściej zadawane pytania (dodatkowe)

**P: Czy mogę dodać hasło do archiwum ZIP?**  
O: Tak. Ustaw `archive.Password = "yourPassword";` przed wywołaniem `Save`.

**P: Jak uwzględnić tylko określone typy plików?**  
O: Przefiltruj kolekcję `DirectoryInfo` przy użyciu `GetFiles("*.txt")` lub podobnej metody przed wywołaniem `CreateEntries`.

**P: Czy istnieje sposób na aktualizację istniejącego ZIP bez jego ponownego tworzenia?**  
O: Aspose.Zip obsługuje przyrostowe aktualizacje za pomocą `Archive.UpdateEntry`.

## FAQ

### P1: Czy mogę używać Aspose.Zip dla .NET zarówno w projektach komercyjnych, jak i prywatnych?

O1: Tak, Aspose.Zip dla .NET jest licencjonowany zarówno do użytku komercyjnego, jak i prywatnego.

### P2: Czy dostępna jest darmowa wersja próbna?

O2: Tak, możesz wypróbować darmową wersję próbną [tutaj](https://releases.aspose.com/zip/net).

### P3: Jak uzyskać wsparcie dla Aspose.Zip dla .NET?

O3: Odwiedź [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) w celu uzyskania wsparcia społeczności lub rozważ zakup [tymczasowej licencji](https://purchase.aspose.com/temporary-license/) dla dedykowanej pomocy.

### P4: Czy dostępne są inne przykłady i samouczki?

O4: Tak, [dokumentacja](https://reference.aspose.com/zip/net/) zawiera obszerne przykłady i samouczki.

### P5: Czy mogę zakupić Aspose.Zip dla .NET?

O5: Oczywiście, możesz dokonać zakupu [tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-09  
**Testowano z:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose