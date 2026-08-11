---
date: 2026-05-30
description: Dowiedz się, jak spakować folder przy użyciu Aspose.Zip dla .NET, efektywnie
  tworzyć archiwa zip w .NET i zmniejszyć zużycie miejsca na dysku w aplikacjach .NET.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Jak spakować folder
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak spakować folder przy użyciu Aspose.Zip dla .NET
url: /pl/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak spakować folder przy użyciu Aspose.Zip dla .NET

W tym samouczku odkryjesz **jak spakować folder** szybko i niezawodnie przy użyciu Aspose.Zip dla .NET. Niezależnie od tego, czy tworzysz narzędzie desktopowe, usługę w chmurze, czy zautomatyzowany skrypt tworzenia kopii zapasowych, kompresowanie folderu do archiwum ZIP może znacząco zmniejszyć wymagania dotyczące przechowywania i przyspieszyć transfery sieciowe. Przejdziemy przez każdy krok, wyjaśnimy, dlaczego każda linia ma znaczenie, i podkreślimy typowe pułapki, abyś mógł zastosować tę technikę z pewnością.

## Szybkie odpowiedzi
- **Co robi Aspose.Zip?** Udostępnia prosty .NET API do tworzenia i rozpakowywania archiwów ZIP bez zewnętrznych zależności.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut dla podstawowego kompresowania folderu.  
- **Które wersje .NET są obsługiwane?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1 oraz .NET 5‑10.  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna do użytku produkcyjnego.  
- **Czy mogę kompresować wiele folderów jednocześnie?** Oczywiście — użyj metody `CreateEntries` na dowolnej kolekcji `DirectoryInfo`, aby **spakować wiele folderów** w jednym uruchomieniu.  

`CreateEntries` dodaje wszystkie pliki z katalogu do archiwum.

## Co to jest „jak spakować folder”?

Kompresowanie folderu oznacza wzięcie każdego pliku i podfolderu wewnątrz określonego katalogu i spakowanie ich do jednego archiwum ZIP. Zmniejsza to ogólny rozmiar, zachowuje oryginalną hierarchię i ułatwia przenoszenie lub przechowywanie danych. Powstały plik ZIP może być otwarty na dowolnej platformie bez specjalnego oprogramowania, a struktura folderów zostaje zachowana, tak że po rozpakowaniu układ jest dokładnie taki sam jak przed kompresją.

## Dlaczego używać Aspose.Zip do tego zadania?

Aspose.Zip pozwala **utworzyć archiwum zip** bezpośrednio z kodu .NET przy spójnym API we wszystkich obsługiwanych środowiskach uruchomieniowych. Załaduj klasę `Archive`, dodaj wpisy, ustaw `CompressionLevel`, opcjonalnie przypisz hasło i wywołaj `Save`. Biblioteka przetwarza foldery zawierające tysiące plików w mniej niż sekundę na typowym sprzęcie i obsługuje ponad 50 różnych formatów kompresji oraz algorytmów szyfrowania.

## Wymagania wstępne

- **Aspose.Zip for .NET** – pobierz go [tutaj](https://releases.aspose.com/zip/net/) lub [tutaj](https://releases.aspose.com/zip/net).  
- **Środowisko programistyczne** – Visual Studio, Rider lub dowolne IDE obsługujące C#.  
- **Katalog dokumentów** – zamień `"Your Document Directory"` w kodzie na ścieżkę do folderu, który chcesz skompresować.  
- **Dokumentacja referencyjna** – zapoznaj się z oficjalną dokumentacją [tutaj](https://reference.aspose.com/zip/net/).

## Importowanie przestrzeni nazw

Begin by importing the necessary namespaces. These give you access to the core compression classes.

```csharp
using Aspose.Zip;
using System.IO;
```

## Jak spakować folder przy użyciu Aspose.Zip

Poniżej znajduje się prosty przykład, który demonstruje **jak spakować folder**. Ten sam wzorzec można rozszerzyć, aby **spakować wiele plików .net** lub utworzyć własne struktury archiwów.

### Krok 1: Zainicjalizuj katalog dokumentów

Ustaw zmienną `dataDir` na ścieżkę katalogu, który chcesz skompresować.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Utwórz pliki wyjściowe ZIP

Otwórz dwa obiekty `FileStream` dla plików wyjściowych ZIP. Pokazuje to, jak można wygenerować więcej niż jedno archiwum z tego samego źródła — przydatne przy wersjonowanych kopiach zapasowych.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Krok 3: Skompresuj katalog

Klasa `Archive` reprezentuje archiwum ZIP i udostępnia metody do dodawania wpisów oraz zapisywania pliku. Użyj jej, aby dodać każdy wpis z docelowego folderu. Przykład używa przykładowego folderu o nazwie **CanterburyCorpus**, ale możesz wskazać dowolny katalog.

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

> **Porada:** Jeśli potrzebujesz **utworzyć archiwum zip .net** z określonym poziomem kompresji, ustaw `archive.CompressionLevel` przed wywołaniem `Save`.

## Typowe problemy i rozwiązania

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Pusty plik ZIP | `dataDir` wskazuje na niewłaściwy folder lub brakuje końcowego ukośnika | Sprawdź ścieżkę i upewnij się, że folder zawiera pliki |
| `UnauthorizedAccessException` | Aplikacja nie ma uprawnień do systemu plików | Uruchom Visual Studio jako administrator lub przyznaj prawa odczytu/zapisu |
| Duże zużycie pamięci przy ogromnych katalogach | Ładowanie wszystkich wpisów do pamięci jednocześnie | Użyj `Archive.CreateEntryFromFile` w pętli, aby przesyłać pliki pojedynczo |

## Najczęściej zadawane pytania (dodatkowe)

**P: Czy mogę dodać hasło do archiwum ZIP?**  
O: Tak. Ustaw `archive.Password = "yourPassword";` przed wywołaniem `Save`.

**P: Jak uwzględnić tylko określone typy plików?**  
O: Przefiltruj kolekcję `DirectoryInfo` przy pomocy `GetFiles("*.txt")` lub podobnej przed wywołaniem `CreateEntries`.

**P: Czy istnieje sposób na zaktualizowanie istniejącego ZIP bez jego ponownego tworzenia?**  
O: Aspose.Zip obsługuje aktualizacje przyrostowe za pomocą `Archive.UpdateEntry`.

## FAQ

### P1: Czy mogę używać Aspose.Zip dla .NET zarówno w projektach komercyjnych, jak i prywatnych?

A1: Tak, Aspose.Zip dla .NET jest licencjonowany zarówno do użytku komercyjnego, jak i prywatnego.

### P2: Czy dostępna jest darmowa wersja próbna?

A2: Tak, możesz wypróbować darmową wersję próbną [tutaj](https://releases.aspose.com/zip/net).

### P3: Jak uzyskać wsparcie dla Aspose.Zip dla .NET?

A3: Odwiedź [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) w celu uzyskania wsparcia społeczności lub rozważ zakup [tymczasowej licencji](https://purchase.aspose.com/temporary-license/) dla dedykowanej pomocy.

### P4: Czy dostępne są inne przykłady i samouczki?

A4: Tak, [dokumentacja](https://reference.aspose.com/zip/net/) zawiera obszerne przykłady i samouczki.

### P5: Czy mogę kupić Aspose.Zip dla .NET?

A5: Oczywiście, możesz dokonać zakupu [tutaj](https://purchase.aspose.com/buy).

## Podsumowanie

Masz teraz kompletny, gotowy do produkcji wzorzec **jak spakować folder** przy użyciu Aspose.Zip dla .NET. Korzystając z klasy `Archive` biblioteki, możesz **utworzyć archiwum zip** pliki, ustawić własny `CompressionLevel`, dodać ochronę hasłem i nawet **spakować wiele folderów** w jednym przebiegu — co czyni go idealnym do automatyzacji zadań tworzenia kopii zapasowych folderów. Eksperymentuj z API, aby dodać szyfrowanie, podzielić archiwa lub strumieniowo przesyłać je bezpośrednio do chmury, a będziesz mieć solidne rozwiązanie dla każdego .NET‑owego zapotrzebowania na kompresję.

---

**Ostatnia aktualizacja:** 2026-05-30  
**Testowano z:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose  


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
