---
date: 2026-02-12
description: Dowiedz się, jak spakować folder przy użyciu Aspose.Zip dla .NET, efektywnie
  tworzyć archiwa zip w .NET i zmniejszyć zużycie miejsca na dysku w swoich aplikacjach
  .NET.
linktitle: How to Zip a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak spakować folder przy użyciu Aspose.Zip dla .NET
url: /pl/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak spakować folder przy użyciu Aspose.Zip dla .NET

W tym samouczku dowiesz się **jak spakować folder** szybko i niezawodnie przy użyciu Aspose.Zip dla .NET. Niezależnie od tego, czy tworzysz narzędzie desktopowe, usługę w chmurze, czy zautomatyzowany skrypt backupowy, kompresja folderu do archiwum ZIP może znacząco zmniejszyć wymagania dyskowe i przyspieszyć transfery sieciowe. Przejdziemy przez każdy krok, wyjaśnimy, dlaczego każda linia ma znaczenie, oraz wskażemy typowe pułapki, abyś mógł zastosować technikę z pełnym przekonaniem.

## Szybkie odpowiedzi
- **Co robi Aspose.Zip?** Udostępnia prosty interfejs .NET do tworzenia i rozpakowywania archiwów ZIP bez zewnętrznych zależności.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut dla podstawowej kompresji folderu.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, oraz .NET 5/6+.  
- **Czy potrzebna jest licencja do produkcji?** Tak, do użytku produkcyjnego wymagana jest licencja komercyjna.  
- **Czy mogę kompresować wiele folderów jednocześnie?** Oczywiście — użyj metody `CreateEntries` na dowolnej kolekcji `DirectoryInfo`, aby **spakować wiele folderów** w jednym uruchomieniu.

## Co to jest „jak spakować folder”?

Kompresja folderu oznacza pobranie każdego pliku i podfolderu znajdującego się w danym katalogu i spakowanie ich do jednego archiwum ZIP. Zmniejsza to ogólny rozmiar, zachowuje pierwotną strukturę i ułatwia przenoszenie lub przechowywanie danych.

## Dlaczego używać Aspose.Zip do tego zadania?

- **Szybkość i wydajność:** Zoptymalizowane algorytmy radzą sobie szybko z dużymi folderami.  
- **Czysty .NET:** Nie wymaga natywnych binarek ani narzędzi firm trzecich.  
- **Bogaty zestaw funkcji:** Obsługuje ochronę hasłem (`add password zip`), strumieniowanie oraz ustawianie własnego poziomu kompresji (`set compression level`).  
- **Spójne API:** Działa tak samo w .NET Framework, .NET Core i .NET 5/6, co czyni go idealnym w scenariuszach **create zip archive .net**.  

## Wymagania wstępne

- **Aspose.Zip dla .NET** – pobierz go [tutaj](https://releases.aspose.com/zip/net/).  
- **Środowisko programistyczne** – Visual Studio, Rider lub dowolne IDE obsługujące C#.  
- **Katalog dokumentów** – zamień `"Your Document Directory"` w kodzie na ścieżkę do folderu, który chcesz skompresować.  
- **Dokumentacja referencyjna** – zapoznaj się z oficjalną dokumentacją [tutaj](https://reference.aspose.com/zip/net/).

## Importowanie przestrzeni nazw

Rozpocznij od zaimportowania niezbędnych przestrzeni nazw. Dzięki temu uzyskasz dostęp do podstawowych klas kompresji.

```csharp
using Aspose.Zip;
using System.IO;
```

## Jak spakować folder przy użyciu Aspose.Zip

Poniżej znajduje się prosty przykład demonstrujący **jak spakować folder**. Ten sam schemat można rozbudować, aby **spakować wiele plików .net** lub stworzyć własne struktury archiwów.

### Krok 1: Zainicjalizuj katalog dokumentów

Ustaw zmienną `dataDir` na ścieżkę katalogu, który chcesz skompresować.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Utwórz pliki ZIP wyjściowe

Otwórz dwa obiekty `FileStream` dla plików wyjściowych ZIP. Pokazuje to, jak można wygenerować więcej niż jedno archiwum z tego samego źródła — przydatne przy wersjonowanych kopiach zapasowych.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Krok 3: Skompresuj katalog

Użyj klasy `Archive`, aby dodać każdy wpis z docelowego folderu. Przykład korzysta z przykładowego folderu **CanterburyCorpus**, ale możesz wskazać dowolny katalog.

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
|-------|--------------------------|-------------|
| Pusty plik ZIP | `dataDir` wskazuje niewłaściwy folder lub brakuje końcowego ukośnika | Zweryfikuj ścieżkę i upewnij się, że folder zawiera pliki |
| `UnauthorizedAccessException` | Aplikacja nie ma uprawnień do systemu plików | Uruchom Visual Studio jako administrator lub przyznaj prawa odczytu/zapisu |
| Duże zużycie pamięci przy ogromnych katalogach | Ładowanie wszystkich wpisów do pamięci jednocześnie | Użyj `Archive.CreateEntryFromFile` w pętli, aby strumieniowo przetwarzać pliki pojedynczo |

## Najczęściej zadawane pytania (dodatkowe)

**P: Czy mogę dodać hasło do archiwum ZIP?**  
O: Tak. Ustaw `archive.Password = "yourPassword";` przed wywołaniem `Save`.

**P: Jak uwzględnić tylko określone typy plików?**  
O: Przefiltruj kolekcję `DirectoryInfo` przy pomocy `GetFiles("*.txt")` lub podobnej metody przed wywołaniem `CreateEntries`.

**P: Czy istnieje sposób na aktualizację istniejącego ZIP bez jego ponownego tworzenia?**  
O: Aspose.Zip obsługuje przyrostowe aktualizacje poprzez `Archive.UpdateEntry`.

## FAQ

### P1: Czy mogę używać Aspose.Zip dla .NET zarówno w projektach komercyjnych, jak i prywatnych?

O1: Tak, Aspose.Zip dla .NET jest licencjonowany zarówno do użytku komercyjnego, jak i prywatnego.

### P2: Czy dostępna jest darmowa wersja próbna?

O2: Tak, darmową wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/zip/net).

### P3: Jak uzyskać wsparcie dla Aspose.Zip dla .NET?

O3: Odwiedź [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) w celu uzyskania pomocy społeczności lub rozważ zakup [tymczasowej licencji](https://purchase.aspose.com/temporary-license/) dla dedykowanej obsługi.

### P4: Czy dostępne są inne przykłady i samouczki?

O4: Tak, [dokumentacja](https://reference.aspose.com/zip/net/) zawiera obszerne przykłady i samouczki.

### P5: Czy mogę zakupić Aspose.Zip dla .NET?

O5: Oczywiście, zakup możesz dokonać [tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-02-12  
**Testowano z:** Aspose.Zip 24.11 dla .NET  
**Autor:** Aspose  

---