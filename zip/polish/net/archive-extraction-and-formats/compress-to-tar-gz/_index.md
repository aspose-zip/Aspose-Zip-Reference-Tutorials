---
date: 2026-01-28
description: Dowiedz się, jak utworzyć archiwum tar.gz, dodać pliki do tar i skompresować
  je przy użyciu Aspose.Zip dla .NET – szybki, niezawodny sposób na archiwizowanie
  plików.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Utwórz archiwum tar.gz i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj pliki do tar i utwórz TarGz przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

W nowoczesnych aplikacjach .NET, **add files to tar** szybko i niezawodnie jest powszechnym wymaganiem — niezależnie od tego, czy pakujesz logi, przygotowujesz dane do przechowywania w chmurze, czy tworzysz pakiety wdrożeniowe. Aspose.Zip dla .NET zapewnia czyste, wysokowydajne API do **add files to tar**, a następnie kompresuje archiwum do powszechnie używanego formatu **tar.gz**. W tym samouczku dowiesz się dokładnie, jak **create tar.gz archive** od podstaw, krok po kroku, używając biblioteki Aspose.Zip .NET.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip for .NET  
- **Jak dodać pliki do tar?** Użyj `TarArchive.CreateEntry` dla każdego pliku.  
- **Czy mogę kompresować bezpośrednio do tar.gz?** Tak — wywołaj `SaveGzipped`.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest ważna licencja Aspose dla użytku nie‑trial.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest „add files to tar”?
Dodawanie plików do archiwum tar oznacza łączenie wielu plików w jeden, nieskompresowany kontener. Format tar zachowuje strukturę katalogów i metadane plików, co czyni go idealnym do archiwizacji przed opcjonalną kompresją (np. gzip) w celu **create tar.gz archive**.

## Dlaczego używać Aspose.Zip do kompresji plików do tar.gz?
- **Brak zewnętrznych narzędzi** – wszystko działa wewnątrz Twojego kodu .NET.  
- **Wysoka wydajność** – API oparte na strumieniach efektywnie obsługuje duże pliki.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS.  
- **Bogaty zestaw funkcji** – obsługuje szyfrowanie, ochronę hasłem i niestandardowe atrybuty wpisów.  

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz:

- Podstawowe doświadczenie w programowaniu .NET.  
- Visual Studio (lub dowolne preferowane IDE).  
- Aspose.Zip for .NET zainstalowany – zobacz oficjalną dokumentację [tutaj](https://reference.aspose.com/zip/net/).  
- Bibliotekę Aspose.Zip pobrano z [tego linku](https://releases.aspose.com/zip/net/).

## Importowanie przestrzeni nazw

W swoim projekcie .NET zaimportuj przestrzenie nazw, które udostępniają klasy związane z tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak utworzyć archiwum tar.gz przy użyciu Aspose.Zip dla .NET

### Krok 1: Ustaw katalog dokumentu

Najpierw wskaż w kodzie folder, który zawiera pliki, które chcesz zarchiwizować.

```csharp
string dataDir = "Your Document Directory";
```

> **Wskazówka:** Używaj `Path.Combine` przy budowaniu ścieżek, aby uniknąć problemów z separatorami specyficznymi dla platformy.

### Krok 2: Zainicjalizuj TarArchive

Utwórz instancję `TarArchive`, która będzie przechowywać wpisy.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

### Krok 3: Dodaj pliki – rdzeń „add files to tar”

Wewnątrz bloku `using` dodaj każdy plik, który chcesz uwzględnić w archiwum.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Każde wywołanie `CreateEntry` przyjmuje **nazwę wpisu** (jak plik będzie widoczny w tar) oraz **ścieżkę do pliku źródłowego** na dysku.

### Krok 4: Zapisz jako Gzipped Tar (jak kompresować pliki do tar.gz)

Na koniec zapisz zawartość tar do strumienia gzip, aby uzyskać kompaktowy `archive.tar.gz`.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` obsługuje zarówno pakowanie tar, jak i kompresję gzip w jednym płynnym wywołaniu.

## Typowe przypadki użycia

| Scenariusz | Dlaczego „add files to tar” pomaga |
|------------|------------------------------------|
| **Agregacja logów** | Zgrupuj codzienne logi w jedno archiwum przed przesłaniem do przechowywania w chmurze. |
| **Pakiety wdrożeniowe** | Utwórz przenośne pakiety tar.gz dla serwerów Linux z potoku budowania w Windows. |
| **Kopia zapasowa danych** | Zachowaj hierarchię folderów i metadane, jednocześnie utrzymując mały rozmiar kopii zapasowej. |

## Typowe problemy i rozwiązania

- **Błąd pliku nie znaleziono** – Upewnij się, że `dataDir` kończy się odpowiednim separatorem ścieżki lub użyj `Path.Combine`.  
- **Duże pliki powodują obciążenie pamięci** – Użyj przeciążeń opartych na strumieniach (`CreateEntry` z `Stream`), aby uniknąć ładowania całych plików do pamięci.  
- **Wyjście gzip jest uszkodzone** – Zweryfikuj, że archiwum jest zamknięte (`using` block) przed wywołaniem `SaveGzipped`.  

## Najczęściej zadawane pytania

**Q: Czy Aspose.Zip for .NET jest kompatybilny ze wszystkimi aplikacjami .NET?**  
A: Tak, działa z projektami .NET Framework, .NET Core oraz .NET 5/6/7.

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Zip for .NET?**  
A: Odwiedź [stronę tymczasowej licencji](https://purchase.aspose.com/temporary-license/), aby poprosić o licencję próbną.

**Q: Czy istnieją ograniczenia rozmiaru plików?**  
A: Biblioteka jest zoptymalizowana pod kątem dużych plików; nie ma sztywnego limitu rozmiaru poza dostępną pamięcią systemową.

**Q: Gdzie mogę uzyskać wsparcie?**  
A: Skorzystaj z forum wsparcia prowadzonego przez społeczność [tutaj](https://forum.aspose.com/c/zip/37), aby uzyskać pomoc od inżynierów Aspose i innych programistów.

**Q: Czy mogę wypróbować Aspose.Zip for .NET za darmo?**  
A: Oczywiście — pobierz darmową wersję próbną ze [strony wydań Aspose Zip](https://releases.aspose.com/zip/net).

## Podsumowanie

Teraz nauczyłeś się **how to add files to tar**, tworzyć archiwum tar i kompresować je do **tar.gz** przy użyciu Aspose.Zip dla .NET. To podejście eliminuje zewnętrzne zależności, daje precyzyjną kontrolę nad zawartością archiwum i skaluje się do dużych zestawów danych. Śmiało eksploruj dodatkowe funkcje Aspose.Zip, takie jak szyfrowanie, niestandardowe atrybuty wpisów i API strumieniowe, aby jeszcze bardziej usprawnić swój proces archiwizacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-28  
**Testowano z:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose