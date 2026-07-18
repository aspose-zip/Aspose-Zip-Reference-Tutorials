---
date: 2026-07-18
description: Dowiedz się, jak dodać folder do archiwum ZIP i dodać pliki do ZIP przy
  użyciu Aspose.Zip dla .NET. Ten przewodnik krok po kroku pokazuje, jak kompresować
  pliki za pomocą FileInfo w projektach ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Kompresuj pliki za pomocą FileInfo
og_description: Dodaj folder do archiwum ZIP przy użyciu Aspose.Zip dla .NET. Dowiedz
  się, jak utworzyć archiwum ZIP, dodać pliki do ZIP i efektywnie kompresować foldery
  w ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Dodaj folder do archiwum ZIP – kompresuj pliki przy użyciu Aspose.Zip dla
  .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Dodaj folder do archiwum ZIP przy użyciu Aspose.Zip dla .NET – kompresuj pliki
  za pomocą FileInfo
url: /pl/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj folder do archiwum zip przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

Jeśli potrzebujesz **dodawać folder do zip** programowo, Aspose.Zip dla .NET oferuje czyste, wysokowydajne API, które działa w każdej aplikacji .NET (w tym ASP.NET). W tym samouczku przeprowadzimy Cię przez kompresję plików przy użyciu klasy `FileInfo`, pokażemy, jak **dodawać pliki do zip**, oraz wyjaśnimy, dlaczego to podejście jest idealne dla nowoczesnych projektów .NET. Omówimy także dokładne kroki, aby **dodawać folder do zip**, dzięki czemu możesz spakować całe katalogi w jednej operacji. Zaczynajmy!

## Szybkie odpowiedzi
- **Jaki jest najprostszy sposób na utworzenie archiwum zip?** Użyj klasy `Archive` Aspose.Zip wraz z obiektami `FileInfo`.  
- **Czy mogę dodać wiele plików jednocześnie?** Tak – po prostu utwórz `FileInfo` dla każdego pliku i wywołaj `CreateEntry`.  
- **Czy potrzebuję specjalnej licencji na ASP.NET?** Wymagana jest komercyjna licencja Aspose.Zip do produkcji; darmowa wersja próbna działa w ocenie.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 oraz .NET 5–10.  
- **Czy API jest wątkowo‑bezpieczne?** Tak, pod warunkiem, że każdy wątek pracuje z własną instancją `Archive`.

## Czym jest archiwum Zip i dlaczego je tworzyć?
Archiwum zip łączy jeden lub więcej plików w pojedynczy, skompresowany kontener. Dzięki temu zmniejsza się zajmowane miejsce, przyspiesza transfer sieciowy i upraszcza dystrybucję. Niezależnie od tego, czy dostarczasz logi, eksportujesz raporty, czy pakujesz zasoby dla klienta, znajomość **jak tworzyć archiwa zip** programowo jest cenną umiejętnością dla każdego programisty .NET.

## Dlaczego używać Aspose.Zip do dodawania plików do zip?
Aspose.Zip zapewnia czyste rozwiązanie .NET, które eliminuje zewnętrzne zależności, jednocześnie dając programistom precyzyjną kontrolę nad kompresją, kodowaniem i bezpieczeństwem. Obsługuje duże pliki, ochronę hasłem i działa konsekwentnie we wszystkich obsługiwanych wersjach .NET, co czyni go niezawodnym wyborem zarówno dla starszych, jak i nowoczesnych aplikacji.  

- **Zero zewnętrznych zależności** – czysta implementacja .NET.  
- **Pełna kontrola nad poziomem kompresji i kodowaniem** (ASCII, UTF‑8 itp.).  
- **Obsługuje pliki większe niż 4 GB** oraz ochronę hasłem.  
- **Spójne API w ponad 50 wersjach .NET** – od .NET Framework 2.0 do .NET 10.  

## Prerequisites

Zanim przejdziemy do kodu, upewnij się, że masz:

1. **Aspose.Zip for .NET** zainstalowany. Pobierz najnowszy pakiet ze [strony pobierania Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Folder na swoim komputerze zawierający pliki, które chcesz skompresować (np. `alice29.txt` i `fields.c`).  

## Importowanie przestrzeni nazw

W każdym pliku C#, w którym będziesz pracować z archiwami zip, dodaj następujące instrukcje `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Przewodnik krok po kroku

### Krok 1: Skonfiguruj katalog dokumentów

Najpierw określ folder, w którym znajdują się pliki źródłowe. Zastąp placeholder absolutną lub względną ścieżką w swoim systemie:

```csharp
string dataDir = "Your Document Directory";
```

> **Wskazówka:** Użyj `Path.Combine`, aby budować ścieżki w sposób wieloplatformowy.

### Krok 2: Otwórz plik Zip do zapisu

Utwórz `FileStream`, który wskazuje na wyjściowy plik zip. Strumień jest otwierany w trybie **Create**, który nadpisuje istniejący plik o tej samej nazwie:

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

> **Dlaczego używać `FileInfo`?** Unika ładowania całego pliku do pamięci, co jest szczególnie przydatne przy dużych plikach.

### Krok 4: Utwórz archiwum i dodaj wpisy

Klasa `Archive` jest podstawowym obiektem Aspose.Zip, który reprezentuje kontener zip w pamięci. Utwórz obiekt `Archive`, a następnie wywołaj `CreateEntry` dla każdego `FileInfo`. Pierwszy argument to nazwa, jaką plik będzie miał w zipie, drugi argument to źródłowy `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

Metoda `CreateEntry` dodaje nowy wpis pliku do archiwum, łącząc nazwę wpisu ze źródłowym `FileInfo`, tak aby dane były strumieniowane bezpośrednio z dysku podczas zapisywania archiwum.

### Krok 5: Zapisz archiwum Zip z wybranym kodowaniem

Na koniec zapisz archiwum do wcześniej otwartego `FileStream`. Tutaj używamy kodowania ASCII dla nazw wpisów, ale możesz przełączyć na UTF‑8, jeśli nazwy plików zawierają znaki nie‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Gdy bloki `using` zakończą się, strumienie zostaną automatycznie zamknięte i plik zip będzie gotowy do użycia.

## Jak dodać folder do Zip przy użyciu Aspose.Zip?

Wczytaj docelowy katalog, wylicz wszystkie pliki i dodaj każdy z relatywną ścieżką zawierającą nazwę folderu. To podejście pozwala **dodawać folder do zip** bez ręcznego wymieniania każdego pliku. Zachowując hierarchię folderów w nazwach wpisów, powstałe archiwum może być rozpakowane z zachowaną pierwotną strukturą katalogów, co jest istotne w wielu scenariuszach wdrożeniowych.

1. Użyj `DirectoryInfo`, aby wskazać folder, który chcesz skompresować.  
2. Wywołaj `GetFiles("*", SearchOption.AllDirectories)`, aby pobrać wszystkie pliki rekurencyjnie.  
3. Dla każdego pliku utwórz `FileInfo` i wywołaj `CreateEntry` ze ścieżką taką jak `"MyFolder/Report.pdf"`.

Ponieważ API działa z `FileInfo`, strumieniuje każdy plik bezpośrednio z dysku, utrzymując niskie zużycie pamięci nawet przy folderach zawierających setki megabajtów.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **Pusty plik zip** | `FileInfo` wskazuje na nieistniejącą ścieżkę | Sprawdź `dataDir` i nazwy plików; użyj `File.Exists`, aby zweryfikować przed tworzeniem wpisów. |
| **Nieprawidłowe kodowanie nazw plików** | Użycie domyślnego kodowania przy nazwach nie‑ASCII | Ustaw `Encoding = Encoding.UTF8` w `ArchiveSaveOptions`. |
| **OutOfMemoryException przy dużych plikach** | Ładowanie całego pliku do pamięci | `FileInfo` strumieniuje plik; upewnij się, że nie odczytujesz pliku do tablicy bajtów w innym miejscu. |
| **Odmowa dostępu** | Aplikacja nie ma uprawnień do zapisu w folderze wyjściowym | Uruchom aplikację z odpowiednimi uprawnieniami lub wybierz folder, do którego można zapisywać. |

## Najczęściej zadawane pytania

**Q: Czy mogę dodać cały folder do archiwum zip jednym wywołaniem?**  
A: Nie istnieje metoda jednoczesnego wywołania, ale wyliczanie plików przy użyciu `DirectoryInfo` i dodawanie każdego za pomocą `CreateEntry` osiąga ten sam efekt efektywnie.

**Q: Czy Aspose.Zip obsługuje ochronę hasłem?**  
A: Tak, możesz ustawić hasło na obiekcie `Archive` przed zapisaniem, aby zaszyfrować całe archiwum.

**Q: Jak duże archiwum zip może obsłużyć Aspose.Zip?**  
A: Biblioteka obsługuje pliki większe niż 4 GB i może tworzyć archiwa przekraczające 10 GB bez ładowania całego archiwum do pamięci.

**Q: Czy API jest kompatybilne z .NET 6 i .NET 8?**  
A: Zdecydowanie tak. Aspose.Zip obsługuje .NET 5 do .NET 10, obejmując wszystkie aktualne wersje LTS.

**Q: Jakie poziomy kompresji są dostępne?**  
A: Możesz wybrać `CompressionLevel.NoCompression`, `Fast`, `Normal` lub `Maximum`, aby zrównoważyć szybkość i rozmiar.

## Dalsze zasoby

- Pobierz najnowszy pakiet Aspose.Zip: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Kup licencję do użytku produkcyjnego: [purchase page](https://purchase.aspose.com/buy)  
- Uzyskaj pomoc od społeczności: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Wypróbuj Aspose.Zip za darmo: [free trial here](https://releases.aspose.com/)  
- Uzyskaj tymczasową licencję do oceny: [this link](https://purchase.aspose.com/temporary-license/)

## Zakończenie

Teraz wiesz **jak dodawać folder do zip** i **jak tworzyć archiwa zip** przy użyciu Aspose.Zip dla .NET, jak **dodawać pliki do zip**, oraz dlaczego ta metoda jest idealna dla ASP.NET i innych aplikacji .NET. Eksperymentuj z różnymi poziomami kompresji, kodowaniami i opcjami szyfrowania, aby dostosować archiwum do swoich dokładnych potrzeb. Miłej kompresji!

---

**Last Updated:** 2026-07-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak spakować folder przy użyciu Aspose.Zip dla .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Bezproblemowa kompresja z Aspose.Zip dla .NET](/zip/net/file-compression/compress-multiple-files/)
- [Utwórz archiwum Zip .NET – Kompresja plików z Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}