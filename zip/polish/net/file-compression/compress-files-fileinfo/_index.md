---
date: 2025-12-05
description: Dowiedz się, jak utworzyć archiwum zip i dodać pliki do zip przy użyciu
  Aspose.Zip dla .NET. Ten przewodnik krok po kroku pokazuje, jak kompresować pliki
  za pomocą FileInfo w projektach ASP.NET.
language: pl
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak utworzyć archiwum ZIP przy użyciu Aspose.Zip dla .NET – kompresowanie plików
  za pomocą FileInfo
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć archiwum Zip przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

Jeśli potrzebujesz **utworzyć archiwum zip** programowo, Aspose.Zip dla .NET oferuje czyste, wysokowydajne API, które działa w każdej aplikacji .NET (w tym ASP.NET). W tym samouczku przeprowadzimy Cię przez kompresję plików przy użyciu klasy `FileInfo`, pokażemy, jak **dodać pliki do zip**, oraz wyjaśnimy, dlaczego to podejście jest idealne dla nowoczesnych projektów .NET. Zaczynajmy!

## Szybkie odpowiedzi
- **Jaki jest najprostszy sposób na utworzenie archiwum zip?** Użyj klasy `Archive` z Aspose.Zip razem z obiektami `FileInfo`.  
- **Czy mogę dodać wiele plików jednocześnie?** Tak – wystarczy utworzyć `FileInfo` dla każdego pliku i wywołać `CreateEntry`.  
- **Czy potrzebna jest specjalna licencja dla ASP.NET?** Wymagana jest komercyjna licencja Aspose.Zip do środowiska produkcyjnego; darmowa wersja próbna wystarcza do oceny.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy API jest wątkowo‑bezpieczne?** Tak, pod warunkiem, że każdy wątek pracuje z własną instancją `Archive`.

## Czym jest archiwum Zip i dlaczego je tworzyć?
Archiwum zip łączy jeden lub więcej plików w jedną, skompresowaną całość. Redukuje to zajmowaną przestrzeń dyskową, przyspiesza transfery sieciowe i upraszcza dystrybucję. Niezależnie od tego, czy dostarczasz logi, eksportujesz raporty, czy pakujesz zasoby dla klienta, znajomość **sposobu tworzenia plików zip** programowo jest cenną umiejętnością dla każdego programisty .NET.

## Dlaczego warto używać Aspose.Zip do dodawania plików do zip?
- **Zero zewnętrznych zależności** – czysta implementacja .NET.  
- **Pełna kontrola nad poziomem kompresji i kodowaniem** (ASCII, UTF‑8 itp.).  
- **Obsługa dużych plików** (> 4 GB) oraz ochrony hasłem.  
- **Spójne API w .NET Framework, .NET Core i .NET 5+**.

## Wymagania wstępne

Zanim przejdziesz do kodu, upewnij się, że masz:

1. **Aspose.Zip dla .NET** zainstalowany. Pobierz najnowszy pakiet ze [strony pobierania Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Folder na komputerze zawierający pliki, które chcesz skompresować (np. `alice29.txt` i `fields.c`).  

## Importowanie przestrzeni nazw

W każdym pliku C#, w którym będziesz pracować z archiwami zip, dodaj następujące dyrektywy `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Te przestrzenie nazw zapewniają dostęp do klasy `Archive`, opcji zapisu oraz standardowych narzędzi I/O.

## Przewodnik krok po kroku

### Krok 1: Ustaw katalog dokumentów

Najpierw określ folder, w którym znajdują się pliki źródłowe. Zastąp placeholder rzeczywistą ścieżką absolutną lub względną w Twoim systemie:

```csharp
string dataDir = "Your Document Directory";
```

> **Wskazówka:** Używaj `Path.Combine`, aby budować ścieżki w sposób wieloplatformowy.

### Krok 2: Otwórz plik zip do zapisu

Utwórz `FileStream` wskazujący na wyjściowy plik zip. Strumień otwierany jest w trybie **Create**, który nadpisuje istniejący plik o tej samej nazwie:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Krok 3: Przygotuj obiekty `FileInfo` dla każdego pliku źródłowego

`FileInfo` daje Aspose.Zip bezpośredni dostęp do fizycznych plików na dysku. Utwórz jedną instancję dla każdego pliku, który chcesz skompresować:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Dlaczego używać `FileInfo`?** Unika to wczytywania całego pliku do pamięci, co jest szczególnie przydatne przy dużych plikach.

### Krok 4: Utwórz archiwum i dodaj wpisy

Zainicjuj obiekt `Archive`, a następnie wywołaj `CreateEntry` dla każdego `FileInfo`. Pierwszy argument to nazwa, jaką plik będzie miał wewnątrz zip, drugi argument to źródłowy `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Krok 5: Zapisz archiwum zip z wybranym kodowaniem

Na koniec zapisz archiwum do wcześniej otwartego `FileStream`. Tutaj używamy kodowania ASCII dla nazw wpisów, ale możesz przełączyć się na UTF‑8, jeśli Twoje nazwy plików zawierają znaki spoza ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Po zakończeniu bloków `using` strumienie zostaną automatycznie zamknięte, a plik zip będzie gotowy do użycia.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **Pusty plik zip** | `FileInfo` wskazuje na nieistniejącą ścieżkę | Sprawdź `dataDir` i nazwy plików; użyj `File.Exists`, aby zweryfikować przed tworzeniem wpisów. |
| **Nieprawidłowe kodowanie nazw plików** | Użycie domyślnego kodowania przy nazwach nie‑ASCII | Ustaw `Encoding = Encoding.UTF8` w `ArchiveSaveOptions`. |
| **OutOfMemoryException przy dużych plikach** | Ładowanie całego pliku do pamięci | `FileInfo` strumieniuje plik; upewnij się, że nie odczytujesz go do tablicy bajtów w innym miejscu. |
| **Brak uprawnień** | Aplikacja nie ma prawa zapisu w folderze wyjściowym | Uruchom aplikację z odpowiednimi uprawnieniami lub wybierz katalog, do którego można zapisywać. |

## Najczęściej zadawane pytania

**P: Czy mogę dodać ochronę hasłem do archiwum zip?**  
O: Tak. Po utworzeniu `Archive` ustaw `archive.Password = "yourPassword"` przed wywołaniem `Save`.

**P: Czy można zaktualizować istniejący plik zip?**  
O: Aspose.Zip umożliwia otwarcie istniejącego archiwum metodą `Archive.Open`, a następnie dodanie nowych wpisów.

**P: Jak kompresować pliki w kontrolerze ASP.NET MVC?**  
O: Ten sam kod działa; wystarczy, że strumień wyjściowy zostanie zwrócony jako `FileResult` do klienta.

**P: Czy Aspose.Zip obsługuje algorytmy szyfrowania?**  
O: Obsługuje standardowy ZipCrypto oraz szyfrowanie AES‑256.

**P: Co zrobić, gdy muszę skompresować folder rekurencyjnie?**  
O: Przejdź przez `Directory.GetFiles` (i podfoldery), utwórz `FileInfo` dla każdego pliku i dodaj je do archiwum.

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

## Zakończenie

Teraz wiesz, **jak utworzyć archiwum zip** przy użyciu Aspose.Zip dla .NET, **jak dodać pliki do zip**, oraz dlaczego ta metoda jest idealna dla ASP.NET i innych aplikacji .NET. Eksperymentuj z różnymi poziomami kompresji, kodowaniami i opcjami szyfrowania, aby dopasować archiwum do swoich dokładnych potrzeb. Szczęśliwe kompresowanie!

---

**Ostatnia aktualizacja:** 2025-12-05  
**Testowano z:** Aspose.Zip dla .NET 24.12 (najnowsza)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}