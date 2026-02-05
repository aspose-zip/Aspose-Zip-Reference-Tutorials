---
date: 2026-02-05
description: Naucz się, jak spakować wiele plików w C# i utworzyć archiwum ZIP w .NET
  przy użyciu Aspose.Zip. Ten przewodnik krok po kroku pokazuje kompresję plików za
  pomocą FileInfo w projektach ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak spakować wiele plików w C# przy użyciu Aspose.Zip dla .NET
url: /pl/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak spakować wiele plików c# przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

Jeśli potrzebujesz **spakować wiele plików c#** programowo, Aspose.Zip dla .NET zapewnia czyste, wysokowydajne API, które działa w każdej aplikacji .NET (w tym ASP.NET). W tym samouczku przeprowadzimy Cię przez kompresję plików przy użyciu klasy `FileInfo`, pokażemy, jak **dodawać pliki do zip**, i wyjaśnimy, dlaczego to podejście jest idealne dla nowoczesnych projektów .NET. Zaczynajmy!

## Szybkie odpowiedzi
- **Jaki jest najprostszy sposób na utworzenie archiwum zip?** Użyj klasy `Archive` z Aspose.Zip wraz z obiektami `FileInfo`.  
- **Czy mogę dodać wiele plików jednocześnie?** Tak – po prostu utwórz `FileInfo` dla każdego pliku i wywołaj `CreateEntry`.  
- **Czy potrzebuję specjalnej licencji dla ASP.NET?** Wymagana jest komercyjna licencja Aspose.Zip do produkcji; darmowa wersja próbna działa w celach ewaluacyjnych.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy API jest wątkowo‑bezpieczne?** Tak, pod warunkiem że każdy wątek pracuje z własną instancją `Archive`.  
- **Jak spakować pliki c# bez ładowania ich do pamięci?** Użyj obiektów `FileInfo` – one strumieniują dane bezpośrednio.  

## Jak spakować wiele plików c#

Archiwum zip łączy jeden lub więcej plików w pojedynczy, skompresowany kontener. Dzięki temu zmniejsza się zajętość dysku, przyspieszają transfery sieciowe i upraszcza dystrybucję. Niezależnie od tego, czy dostarczasz logi, eksportujesz raporty, czy pakujesz zasoby dla klienta, znajomość **jak spakować pliki c#** programowo jest cenną umiejętnością dla każdego dewelopera .NET.

## Dlaczego używać Aspose.Zip do dodawania plików do zip?

- **Zero zewnętrznych zależności** – czysta implementacja .NET.  
- **Pełna kontrola nad poziomem kompresji i kodowaniem** (ASCII, UTF‑8, itp.).  
- **Obsługuje duże pliki** (> 4 GB) oraz ochronę hasłem.  
- **Spójne API w .NET Framework, .NET Core i .NET 5+**.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnij się, że masz:

1. Zainstalowany **Aspose.Zip for .NET**. Pobierz najnowszy pakiet ze [strony pobierania Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Folder na twoim komputerze zawierający pliki, które chcesz skompresować (np. `alice29.txt` i `fields.c`).  

## Importowanie przestrzeni nazw

W dowolnym pliku C#, w którym będziesz pracować z archiwami zip, dodaj następujące instrukcje `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Te przestrzenie nazw dają dostęp do klasy `Archive`, opcji zapisu oraz standardowych narzędzi I/O.

## Przewodnik krok po kroku

### Krok 1: Skonfiguruj katalog dokumentów

Najpierw określ folder, w którym znajdują się pliki źródłowe. Zastąp placeholder absolutną lub względną ścieżką w twoim systemie:

```csharp
string dataDir = "Your Document Directory";
```

> **Wskazówka:** Użyj `Path.Combine`, aby budować ścieżki w sposób wieloplatformowy.

### Krok 2: Otwórz plik zip do zapisu

Utwórz `FileStream`, który wskazuje na wyjściowy plik zip. Strumień jest otwierany w trybie **Create**, który nadpisuje istniejący plik o tej samej nazwie:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Krok 3: Przygotuj obiekty `FileInfo` dla każdego pliku źródłowego

`FileInfo` zapewnia Aspose.Zip bezpośredni dostęp do fizycznych plików na dysku. Utwórz jedną instancję dla każdego pliku, który chcesz skompresować:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Dlaczego używać `FileInfo`?** Unika ładowania całego pliku do pamięci, co jest szczególnie przydatne przy dużych plikach.

### Krok 4: Utwórz archiwum i dodaj wpisy

Zainicjuj obiekt `Archive`, a następnie wywołaj `CreateEntry` dla każdego `FileInfo`. Pierwszy argument to nazwa, jaką plik będzie miał w zipie, drugi argument to źródłowy `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Krok 5: Zapisz archiwum zip z wybranym kodowaniem

Na koniec zapisz archiwum do `FileStream` otwartego wcześniej. Tutaj używamy kodowania ASCII dla nazw wpisów, ale możesz przełączyć na UTF‑8, jeśli nazwy plików zawierają znaki nie‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Gdy bloki `using` zakończą się, strumienie zostaną automatycznie zamknięte i plik zip będzie gotowy do użycia.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **Pusty plik zip** | `FileInfo` wskazuje na nieistniejącą ścieżkę | Sprawdź `dataDir` i nazwy plików; użyj `File.Exists`, aby zweryfikować przed tworzeniem wpisów. |
| **Nieprawidłowe kodowanie nazw plików** | Używanie domyślnego kodowania przy nazwach nie‑ASCII | Ustaw `Encoding = Encoding.UTF8` w `ArchiveSaveOptions`. |
| **OutOfMemoryException przy dużych plikach** | Ładowanie całego pliku do pamięci | `FileInfo` strumieniuje plik; upewnij się, że nie odczytujesz pliku do tablicy bajtów w innym miejscu. |
| **Odmowa dostępu** | Aplikacja nie ma uprawnień do zapisu w folderze wyjściowym | Uruchom aplikację z odpowiednimi uprawnieniami lub wybierz zapisywalny katalog. |

## Najczęściej zadawane pytania

**P:** Czy mogę dodać ochronę hasłem do archiwum zip?  
**O:** Tak. Po utworzeniu `Archive`, ustaw `archive.Password = "yourPassword"` przed wywołaniem `Save`.

**P:** Czy można zaktualizować istniejący plik zip?  
**O:** Aspose.Zip obsługuje otwieranie istniejącego archiwum za pomocą `Archive.Open`, a następnie dodawanie nowych wpisów.

**P:** Jak skompresować pliki w kontrolerze ASP.NET MVC?  
**O:** Ten sam kod działa; wystarczy, że strumień wyjściowy zostanie zwrócony jako `FileResult` do klienta.

**P:** Czy Aspose.Zip obsługuje algorytmy szyfrowania?  
**O:** Obsługuje standardowe szyfrowanie ZipCrypto oraz AES‑256.

**P:** Co zrobić, jeśli muszę skompresować folder rekurencyjnie?  
**O:** Iteruj przez `Directory.GetFiles` (i podfoldery) i twórz `FileInfo` dla każdego pliku, a następnie dodawaj je do archiwum.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Podsumowanie

Teraz wiesz **jak spakować wiele plików c#** przy użyciu Aspose.Zip dla .NET, jak **dodawać pliki do zip**, i dlaczego ta metoda jest idealna dla ASP.NET i innych aplikacji .NET. Eksperymentuj z różnymi poziomami kompresji, kodowaniami i opcjami szyfrowania, aby dostosować archiwum do swoich dokładnych potrzeb. Miłego kompresowania!

---

**Ostatnia aktualizacja:** 2026-02-05  
**Testowano z:** Aspose.Zip for .NET 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}