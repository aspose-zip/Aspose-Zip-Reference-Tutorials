---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# pakowanie wielu plików c# przy użyciu równoległej kompresji Aspose.Zip

## Wprowadzenie

Jeśli potrzebujesz **zip multiple files c#** szybko i efektywnie, wykorzystanie przetwarzania równoległego jest właściwym rozwiązaniem. W nowoczesnych aplikacjach .NET tworzenie dużych archiwów zip może stać się wąskim gardłem — szczególnie przy obsłudze dziesiątek lub setek plików. Aspose.Zip dla .NET eliminuje ten problem, oferując wbudowaną **parallel zip compression**, która rozkłada pracę na wszystkie dostępne rdzenie CPU. W tym samouczku przeprowadzimy Cię przez cały proces: od skonfigurowania środowiska po zapisanie archiwum zip z włączoną równoległością, a także pokażemy, jak **create zip archive c#** działa płynnie w .NET Core.

## Szybkie odpowiedzi
- **Czym jest równoległa kompresja zip?** Kompresuje kilka plików jednocześnie, używając wielu wątków, aby skrócić całkowity czas przetwarzania.  
- **Która biblioteka .NET ją obsługuje?** Aspose.Zip dla .NET udostępnia prosty interfejs API do równoległej kompresji.  
- **Czy potrzebna jest licencja do produkcji?** Tak — wymagana jest pełna licencja; tymczasowa licencja jest dostępna do testów.  
- **Czy mogę dodawać pliki do zip w locie?** Oczywiście — użyj `Archive.CreateEntry` dla każdego pliku, który chcesz uwzględnić.  
- **Czy jest kompatybilna z .NET 6/7?** Tak, API działa we wszystkich nowoczesnych środowiskach .NET.

## Czym jest zip multiple files c#?
`zip multiple files c#` odnosi się do praktyki tworzenia jednego archiwum ZIP zawierającego wiele pojedynczych plików przy użyciu kodu C#. Gdy połączysz to z **parallel zip compression**, biblioteka przetwarza każdy plik w osobnym wątku, dramatycznie skracając czas potrzebny na wygenerowanie finalnego archiwum.

## Dlaczego używać Aspose.Zip do równoległej kompresji?
Równoległa kompresja pozwala wykorzystać każdy rdzeń maszyny wieloprocesorowej, często zapewniając **2‑3× szybszy** przepustowość niż podejście jednowątkowe. Skalowalność jest również naturalna: dodanie większej liczby plików nie zwiększa liniowo czasu rzeczywistego, a API zarządza wątkami za Ciebie, dzięki czemu możesz skoncentrować się na logice biznesowej.  

- **Szybkość:** Wykorzystuje wszystkie logiczne procesory, skracając czas tworzenia zip nawet o 70 % przy typowych obciążeniach.  
- **Skalowalność:** Obsługuje partie 500+ plików bez proporcjonalnego wzrostu czasu CPU.  
- **Prostota:** Metody wysokiego poziomu ukrywają złożoność `System.Threading.Tasks`.  
- **Elastyczność:** Obsługuje .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 oraz .NET 5–10, w tym .NET 6/7 dla usług chmurowych.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz:

- Podstawową wiedzę o C# i programowaniu w .NET.  
- Zainstalowany Aspose.Zip dla .NET. Możesz go pobrać **[tutaj](https://releases.aspose.com/zip/net/)**.  
- Tymczasową lub pełną licencję (tymczasowa licencja wystarczy do tego samouczka).  

## Importowanie przestrzeni nazw

Przestrzeń nazw `Aspose.Zip` zawiera wszystkie typy potrzebne do pracy z archiwami ZIP.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Najpierw wprowadź wymagane przestrzenie nazw do swojego pliku C#, aby kompilator wiedział, gdzie znaleźć używane klasy.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Krok 1: Skonfiguruj katalog dokumentów

Zdefiniuj folder, który zawiera pliki do skompresowania. Ścieżka jest przechowywana w zmiennej `dataDir`, którą możesz skierować na dowolną lokalizację na dysku.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Zainicjuj proces kompresji

Otwórz nowy plik ZIP do zapisu. Instrukcja `using` zapewnia, że strumień pliku zostanie prawidłowo zwolniony po zakończeniu operacji, zapobiegając wyciekom uchwytów plików.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Krok 3: Odczytaj i kompresuj pliki równolegle

`Parallel.ForEach` wykonuje pętlę foreach, w której iteracje mogą działać jednocześnie na wielu wątkach.  

Otwórz każdy plik źródłowy, który zamierzasz dodać do archiwum. W tym przykładzie pracujemy z dwoma klasycznymi tekstami, ale możesz **add files to zip** dla dowolnej liczby dokumentów. Pętla `Parallel.ForEach` automatycznie rozdziela pracę pomiędzy wątki.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Krok 4: Utwórz wpisy archiwum

Klasa `Archive` jest głównym obiektem Aspose.Zip, który reprezentuje kontener ZIP, który budujesz.  

`CreateEntry` tworzy nowy wpis w archiwum ZIP dla określonego pliku. Każde wywołanie `CreateEntry` dodaje nowy wpis pliku do archiwum.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Krok 5: Zdefiniuj kryterium równoległości

`ParallelOptions` to typ .NET, który kontroluje sposób wykonywania pętli równoległych.  

Skonfiguruj kompresję, aby działała równolegle, ustawiając `ParallelOptions`. Flaga `ParallelCompressInMemory` instruuje Aspose.Zip, aby zawsze używał przetwarzania równoległego, a `MaxDegreeOfParallelism` pozwala ograniczyć liczbę jednoczesnych wątków.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Krok 6: Zapisz skompresowane archiwum

Na koniec zapisz archiwum na dysku z wybranymi opcjami, w tym kodowaniem, komentarzem i wcześniej zdefiniowanymi ustawieniami równoległości. Metoda `Save` finalizuje plik ZIP.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** Jeśli kompresujesz bardzo duże pliki, rozważ ustawienie `ParallelOptions.MaxDegreeOfParallelism` na wartość niższą niż liczba logicznych procesorów. Pomoże to utrzymać responsywność serwera pod obciążeniem.

### Typowe przypadki użycia

- **Raportowanie wsadowe:** Generuj pakiet zip codziennych raportów CSV dla systemów downstream.  
- **Archiwizacja dokumentów:** Przechowuj duże kolekcje PDF‑ów, obrazów lub logów w jednym archiwum jako kopię zapasową.  
- **API eksportu danych:** Zwróć plik zip zawierający wiele plików danych klientowi w jednej odpowiedzi HTTP.  

## Typowe problemy i wskazówki

- **Presja pamięci przy ogromnych plikach:** Zamiast ładować cały plik do pamięci, strumieniuj go w fragmentach lub używaj trybu `ParallelCompressInMemory` selektywnie.  
- **Bezpieczeństwo wątków:** API Aspose.Zip jest bezpieczne wątkowo w trybie równoległym, ale unikaj modyfikacji tego samego `FileStream` spoza biblioteki podczas trwania kompresji.  
- **Dostrajanie wydajności:** Eksperymentuj z `ParallelOptions.MaxDegreeOfParallelism`, jeśli musisz ograniczyć zużycie CPU na współdzielonych serwerach.  

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Zip dla .NET razem z innymi bibliotekami kompresji?**  
O: Tak, Aspose.Zip może współistnieć z innymi bibliotekami .NET; wystarczy zachować odrębne przestrzenie nazw.

**P: Czy dostępna jest tymczasowa licencja do celów testowych?**  
O: Tak, tymczasową licencję do testów możesz uzyskać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**P: Gdzie mogę poprosić o pomoc, jeśli napotkam problemy?**  
O: Odwiedź **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**, aby uzyskać wsparcie społeczności i dyskusje.

**P: Gdzie znajdę więcej przykładów kodu i szczegółową dokumentację API?**  
O: Przeglądaj **[dokumentację Aspose.Zip](https://reference.aspose.com/zip/net/)**, aby uzyskać kompleksowe przykłady.

**P: Jak mogę zakupić pełną licencję na Aspose.Zip?**  
O: Pełną licencję Aspose.Zip dla .NET możesz nabyć **[tutaj](https://purchase.aspose.com/buy)**.

---

**Ostatnia aktualizacja:** 2026-06-09  
**Testowano z:** Aspose.Zip 24.11 dla .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [zip multiple files c# – Bezproblemowa kompresja z Aspose.Zip dla .NET](/zip/net/file-compression/compress-multiple-files/)
- [Jak utworzyć archiwum Zip i dodać plik do Zip przy użyciu Aspose.Zip dla .NET](/zip/net/file-compression/compress-single-file/)
- [Kompresja wielu plików z szyfrowaniem w Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}