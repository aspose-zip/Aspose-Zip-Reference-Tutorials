---
date: 2026-06-24
description: Dowiedz się, jak kompresować LZMA w Aspose.Zip dla .NET, optymalizując
  przechowywanie i efektywność transferu danych.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Kompresuj do Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak kompresować LZMA w Aspose.Zip dla .NET
url: /pl/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak kompresować LZMA w Aspose.Zip dla .NET

## Wprowadzenie

W tym samouczku dowiesz się **jak kompresować LZMA** w Aspose.Zip dla .NET, co jest kluczową umiejętnością optymalizacji miejsca na dysku i zwiększenia efektywności transferu danych. LZMA (algorytm Lempel‑Ziv‑Markov chain) zapewnia archiwa nawet o 70 % mniejsze w porównaniu z tradycyjnym ZIP, przy zachowaniu szybkiej dekompresji, co czyni go idealnym w scenariuszach o ograniczonej przepustowości.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Zip for .NET  
- **Jakiego algorytmu dotyczy ten przewodnik?** LZMA compression  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do testów; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 oraz .NET 5–10  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 10 minut dla prostego pliku.

## Czym jest kompresja LZMA?

LZMA jest wysokoratio bezstratnym algorytmem kompresji, który wykorzystuje kompresję słownikową i kodowanie zakresowe. Może zmniejszyć pliki tekstowe o 30‑70 %, zachowując prędkość dekompresji porównywalną z ZIP. Dla dużych zestawów danych LZMA obniża koszty przechowywania i przyspiesza transfery sieciowe bez utraty integralności danych.

## Dlaczego używać Aspose.Zip dla LZMA?

Aspose.Zip obsługuje **5 algorytmów kompresji** (ZIP, Deflate, BZIP2, LZMA i ZSTD) i może obsługiwać archiwa do **4 GB** bez wczytywania całego pliku do pamięci. Biblioteka przetwarza dokumenty wielostronicowe w czasie krótszym niż **2 sekundy** na typowym serwerze, zapewniając zarówno wydajność, jak i skalowalność.

## Wymagania wstępne

Zanim przejdziesz dalej, upewnij się, że masz następujące elementy:

- Aspose.Zip for .NET: Upewnij się, że biblioteka Aspose.Zip jest zainstalowana. Dokumentację znajdziesz [tutaj](https://reference.aspose.com/zip/net/).
- Katalog dokumentów: Wybierz lub utwórz folder zawierający pliki, które chcesz skompresować.

## Importowanie przestrzeni nazw

Dodaj wymagane przestrzenie nazw na początku pliku C#, aby uzyskać dostęp do funkcji LZMA w Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Jak ustawić folder źródłowy do kompresji?

Określ folder, w którym znajdują się pliki, które chcesz zarchiwizować. Udostępnienie dedykowanego katalogu źródłowego zapewnia, że przetwarzane będą tylko zamierzone pliki, zmniejsza ryzyko dołączenia niechcianych danych i upraszcza zarządzanie ścieżkami przy pracy nad wieloma zadaniami kompresji w tym samym projekcie.

```csharp
string dataDir = "Your Document Directory";
```

## Jak skompresować plik przy użyciu LZMA?

`LzmaArchive` jest klasą Aspose.Zip służącą do tworzenia i zarządzania archiwami LZMA.

Utwórz instancję `LzmaArchive`, wskaż na plik źródłowy i wywołaj `Save`, aby wygenerować archiwum `.lzma`. Ten dwuliniowy wzorzec wykonuje cały proces kompresji, zarządzając strumieniami wewnętrznie i tworząc kompaktowy plik gotowy do dystrybucji lub przechowywania.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Jak potwierdzić, że kompresja zakończyła się sukcesem?

`Console.WriteLine` wypisuje wiersz tekstu na standardowe wyjście konsoli.

Po zapisaniu archiwum wyświetl krótką wiadomość potwierdzającą przy użyciu `Console.WriteLine`. Ta natychmiastowa informacja zwrotna pomaga programistom zweryfikować, że krok kompresji zakończył się bez błędów, upraszcza debugowanie podczas automatycznych buildów oraz dostarcza jasnych informacji o stanie, gdy procedura jest integrowana z większymi aplikacjami lub skryptami.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Typowe problemy i rozwiązania

- **Plik nie znaleziony** – Sprawdź, czy ciąg ścieżki używa podwójnych backslashy (`\\`) lub dosłownego łańcucha (`@"C:\Path"`).  
- **Niewystarczająca pamięć** – Aspose.Zip strumieniuje dane, ale bardzo duże pliki mogą wymagać zwiększenia limitu pamięci procesu.  
- **Licencja nie zastosowana** – Upewnij się, że wywołujesz `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` przed jakąkolwiek operacją Aspose.Zip.

## Najczęściej zadawane pytania

**P: Czy mogę skompresować wiele plików do jednego archiwum LZMA?**  
**O:** Tak. Wywołaj `archive.AddFile()` dla każdego pliku przed wywołaniem `archive.Save()`.

**P: Czy istnieje sposób ustawienia poziomu kompresji dla LZMA?**  
**O:** Klasa `LzmaArchive` używa domyślnego poziomu kompresji, który zapewnia dobrą równowagę między szybkością a rozmiarem. Zaawansowane ustawienia są dostępne poprzez `LzmaEncoder`, jeśli potrzebujesz precyzyjnej kontroli.

**P: Czy powstały plik .lzma będzie działał na platformach nie‑Windows?**  
**O:** Zdecydowanie. Format LZMA jest niezależny od platformy, więc archiwum może być dekompresowane na dowolnym systemie operacyjnym przy użyciu narzędzia kompatybilnego z LZMA.

**P: Jak zdekompresować archiwum LZMA przy użyciu Aspose.Zip?**  
**O:** Użyj konstruktora `LzmaArchive` z ścieżką do archiwum, a następnie wywołaj `ExtractToDirectory()`, aby wyodrębnić jego zawartość.

**P: Czy Aspose.Zip obsługuje kompresję strumieniową, aby uniknąć ładowania całych plików do pamięci?**  
**O:** Tak. Możesz pracować ze strumieniami, przekazując obiekty `Stream` do metod `SetSource()` i `Save()`.

---

**Ostatnia aktualizacja:** 2026-06-24  
**Testowano z:** Aspose.Zip for .NET (latest version at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak kompresować pliki przy użyciu Aspose.Zip dla .NET](/zip/net/file-compression/compress-file/)
- [Jak otworzyć archiwum GZip i inne techniki kompresji przy użyciu Aspose.Zip dla .NET](/zip/net/other-compression-techniques/)
- [kompresować pliki c# – Tworzenie archiwum 7z przy użyciu Aspose.Zip dla .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}