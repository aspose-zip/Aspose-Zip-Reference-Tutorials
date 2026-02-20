---
date: 2026-02-20
description: Dowiedz się, jak tworzyć archiwum tar, dodawać pliki do tar i kompresować
  do tar.gz przy użyciu Aspose.Zip dla .NET – szybki, wieloplatformowy sposób tworzenia
  archiwów TarGz.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Utwórz archiwum tar i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz archiwum tar i dodaj pliki do tar przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

W nowoczesnych aplikacjach .NET **tworzenie archiwum tar** i **dodawanie plików do tar** szybko i niezawodnie jest powszechnym wymaganiem — niezależnie od tego, czy pakujesz logi, przygotowujesz dane do przechowywania w chmurze, czy budujesz pakiety wdrożeniowe. Aspose.Zip dla .NET zapewnia czyste, wysokowydajne API do **dodawania plików do tar**, a następnie kompresji archiwum do szeroko używanego formatu **tar.gz**. W tym przewodniku przeprowadzimy Cię przez cały proces, od konfiguracji projektu po uzyskanie gotowego do wysyłki `archive.tar.gz`.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip for .NET  
- **Jak dodać pliki do tar?** Użyj `TarArchive.CreateEntry` dla każdego pliku.  
- **Czy mogę kompresować bezpośrednio do tar.gz?** Tak — wywołaj `SaveGzipped`.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest ważna licencja Aspose dla użytku nie‑trial.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest „add files to tar”?
Dodawanie plików do archiwum tar oznacza łączenie wielu plików w jeden, nieskompresowany kontener. Format tar zachowuje strukturę katalogów i metadane plików, co czyni go idealnym do archiwizacji przed opcjonalną kompresją (np. gzip) w celu **utworzenia archiwum tar.gz**.

## Dlaczego używać Aspose.Zip do kompresji plików do tar.gz?
- **Brak zewnętrznych narzędzi** – wszystko działa wewnątrz Twojego kodu .NET.  
- **Wysoka wydajność** – API oparte na strumieniach efektywnie obsługuje duże pliki.  
- **Tar wieloplatformowy** – działa na Windows, Linux i macOS bez zmian.  
- **Bogaty zestaw funkcji** – obsługuje szyfrowanie, ochronę hasłem i niestandardowe atrybuty wpisów.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

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

## Jak dodać pliki do tar przy użyciu Aspose.Zip dla .NET

### Krok 1: Ustaw katalog dokumentu

Najpierw wskaż kodowi folder, który zawiera pliki, które chcesz zarchiwizować.

```csharp
string dataDir = "Your Document Directory";
```

> **Wskazówka:** Użyj `Path.Combine` przy budowaniu ścieżek, aby uniknąć problemów z separatorami specyficznymi dla platformy.

### Krok 2: Utwórz archiwum TarGz

Teraz utworzymy archiwum tar, dodamy wpisy i skompresujemy je w jednym płynnym przepływie.

#### 2.1 Inicjalizacja TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Dodaj pliki – sedno „add files to tar”

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Każde wywołanie `CreateEntry` przyjmuje **nazwę wpisu** (jak plik pojawi się w tar) oraz **ścieżkę źródłową pliku** na dysku. Możesz wywoływać `CreateEntry` wielokrotnie, aby **dodać wiele plików tar** w jednym archiwum.

#### 2.3 Zapisz jako skompresowany Tar (jak skompresować tar.gz)

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` zapisuje zawartość tar do strumienia gzip, dając Ci kompaktowy plik `archive.tar.gz` gotowy do dystrybucji.

## Typowe przypadki użycia

| Scenariusz | Dlaczego „add files to tar” pomaga |
|------------|------------------------------------|
| **Agregacja logów** | Zgrupuj dzienne logi w jedno archiwum przed przesłaniem do chmury. |
| **Pakiety wdrożeniowe** | Utwórz przenośne pakiety tar.gz dla serwerów Linux z pipeline'u budowania w Windows. |
| **Kopia zapasowa danych** | Zachowaj strukturę katalogów i metadane, jednocześnie utrzymując mały rozmiar kopii. |

## Typowe problemy i rozwiązania

- **Błąd pliku nie znaleziono** – Upewnij się, że `dataDir` kończy się odpowiednim separatorem ścieżki lub użyj `Path.Combine`.  
- **Duże pliki powodują obciążenie pamięci** – Użyj przeciążeń opartych na strumieniach (`CreateEntry` z `Stream`), aby uniknąć ładowania całych plików do pamięci.  
- **Wyjście gzip jest uszkodzone** – Zweryfikuj, że archiwum jest zamknięte (`using` block) przed wywołaniem `SaveGzipped`.  

## Najczęściej zadawane pytania

**Q: Czy Aspose.Zip for .NET jest kompatybilny ze wszystkimi aplikacjami .NET?**  
A: Tak, działa z projektami .NET Framework, .NET Core oraz .NET 5/6/7.

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Zip for .NET?**  
A: Odwiedź [stronę tymczasowej licencji](https://purchase.aspose.com/temporary-license/), aby poprosić o licencję trial.

**Q: Czy istnieją ograniczenia rozmiaru plików?**  
A: Biblioteka jest zoptymalizowana pod kątem dużych plików; nie ma sztywnego limitu rozmiaru poza dostępną pamięcią systemową.

**Q: Gdzie mogę uzyskać wsparcie?**  
A: Skorzystaj z forum wsparcia prowadzonego przez społeczność [tutaj](https://forum.aspose.com/c/zip/37), aby uzyskać pomoc od inżynierów Aspose i innych deweloperów.

**Q: Czy mogę wypróbować Aspose.Zip for .NET za darmo?**  
A: Oczywiście — pobierz bezpłatną wersję próbną z [strony wydań Aspose Zip](https://releases.aspose.com/zip/net).

## Zakończenie

Teraz wiesz, **jak utworzyć archiwum tar**, dodać do niego pliki i skompresować je do **tar.gz** przy użyciu Aspose.Zip dla .NET. To podejście eliminuje zależności zewnętrzne, daje precyzyjną kontrolę nad zawartością archiwum i skaluje się do dużych zestawów danych. Zachęcamy do eksploracji dodatkowych funkcji Aspose.Zip, takich jak szyfrowanie, niestandardowe atrybuty wpisów i API strumieniowe, aby jeszcze bardziej usprawnić proces archiwizacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-02-20  
**Testowano z:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose