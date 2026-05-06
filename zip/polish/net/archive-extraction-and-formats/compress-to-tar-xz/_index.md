---
date: 2026-02-23
description: Dowiedz się, jak dodawać pliki do archiwum tar i kompresować pliki do
  archiwum tarxz w .NET przy użyciu Aspose.Zip. Postępuj zgodnie z tym przewodnikiem
  krok po kroku, aby zapewnić efektywne przechowywanie i transmisję.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dodaj pliki do tar i utwórz archiwum tarxz przy użyciu Aspose.Zip
url: /pl/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj pliki do tar i utwórz archiwum tarxz przy użyciu Aspose.Zip

## Wprowadzenie

Jeśli potrzebujesz **dodać pliki do tar**, a następnie **utworzyć archiwum tarxz w .net**, Aspose.Zip for .NET sprawia, że proces jest prosty i niezawodny. Niezależnie od tego, czy pakujesz logi, pliki konfiguracyjne, czy inne zasoby do przechowywania lub transmisji, kompresja do formatu TarXz zapewnia wysoki współczynnik kompresji przy zachowaniu znanej struktury tar. W tym samouczku przeprowadzimy Cię krok po kroku — wraz z fragmentami kodu — abyś mógł zintegrować tworzenie tarxz w swoich aplikacjach .NET z pełnym przekonaniem.

## Szybkie odpowiedzi
- **Jaka jest główna klasa?** `TarArchive` z `Aspose.Zip.Tar`
- **Jak skompresować tarxz?** Użyj `SaveXzCompressed` po dodaniu wpisów
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Czy wymagana jest licencja?** Tak, ważna licencja Aspose.Zip do produkcji
- **Typowy czas implementacji?** ~5‑10 minut

## Czym jest archiwum TarXz?

**Archiwum TarXz** łączy tradycyjny kontener Unix `tar` z kompresją XZ. Część tar łączy wiele plików w jeden strumień, a XZ zapewnia silną, bezstratną kompresję. Format ten jest popularny przy dystrybucji kodu źródłowego, kopii zapasowych i dużych zestawów danych, ponieważ zachowuje strukturę katalogów i osiąga mniejsze rozmiary plików niż zwykły tar czy zip.

## Dlaczego tworzyć archiwum tarxz w .NET przy użyciu Aspose.Zip?

- **Wysoki współczynnik kompresji** – XZ zazwyczaj kompresuje o 30‑50 % mniej niż gzip.  
- **Kompatybilność międzyplatformowa** – Pliki TarXz można otworzyć w systemach Linux, macOS i Windows.  
- **Proste API** – Aspose.Zip ukrywa szczegóły niskiego poziomu, pozwalając skupić się na logice biznesowej.  
- **Brak zewnętrznych narzędzi** – Wszystko działa wewnątrz procesu .NET, idealne dla chmury lub potoków CI.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

- **Aspose.Zip for .NET** zainstalowany (pobierz z oficjalnej [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Folder zawierający pliki, które chcesz zarchiwizować. W poniższych przykładach folder ten jest odwoływany zmienną `dataDir`.  
- Ważną licencję Aspose.Zip (opcjonalnie do oceny, wymagana w produkcji).

## Importuj przestrzenie nazw

Najpierw zaimportuj przestrzenie nazw, które udostępniają funkcjonalność TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak dodać pliki do tar przy użyciu Aspose.Zip

Poniżej znajduje się przewodnik krok po kroku, który dokładnie pokazuje, jak **dodać pliki do tar** przed ich kompresją.

### Krok 1: Zainicjalizuj `TarArchive`

Utwórz nową instancję `TarArchive`, która będzie przechowywać pliki do skompresowania.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Wskazówka:** Instrukcja `using` zapewnia prawidłowe zwolnienie archiwum, uwalniając wszelkie zasoby niezarządzane.

### Krok 2: Dodaj pliki do archiwum

Dodaj każdy plik, który chcesz uwzględnić. W tym przykładzie dodajemy dwa pliki tekstowe, ale możesz dodać dowolną liczbę wpisów.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Dlaczego to ważne:** Dodawanie wpisów przed kompresją pozwala Aspose.Zip najpierw zbudować kontener tar, a następnie zastosować kompresję XZ w jednym kroku.

### Krok 3: Zapisz archiwum z kompresją XZ

Na koniec zapisz archiwum tar na dysku, używając kompresji XZ. Wynikowy plik będzie miał rozszerzenie `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Wynik:** Masz teraz w pełni skompresowany plik `archive.tar.xz`, który można przenosić, przechowywać lub rozpakowywać na dowolnej platformie obsługującej TarXz.

## Jak kompresować pliki tarxz przy użyciu Aspose.Zip

Proces przedstawiony powyżej to w zasadzie **jak kompresować tarxz**: najpierw dodajesz pliki do kontenera tar (`add files to tar`), a następnie wywołujesz `SaveXzCompressed`. To jednoczesne wywołanie eliminuje potrzebę zewnętrznych narzędzi wiersza poleceń i utrzymuje wszystko wewnątrz Twojego kodu .NET.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **„File not found” exception** | Nieprawidłowa ścieżka `dataDir` | Sprawdź, czy ścieżka katalogu kończy się backslashem (`\`) lub użyj `Path.Combine`. |
| **Large memory usage** | Bardzo duże pliki kompresowane w pamięci | Użyj `TarArchive` w trybie strumieniowym (`SaveXzCompressed` przeciążenie przyjmujące `Stream`). |
| **License not applied** | Brak pliku licencji | Załaduj licencję przy starcie aplikacji: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Najczęściej zadawane pytania

**P: Czy Aspose.Zip jest kompatybilny ze wszystkimi środowiskami .NET?**  
O: Tak, Aspose.Zip działa z .NET Framework 4.5+, .NET Core 3.1+, oraz .NET 5/6+. Zobacz [documentation](https://reference.aspose.com/zip/net/) po szczegóły.

**P: Jak mogę uzyskać tymczasową licencję na Aspose.Zip?**  
O: Tymczasową licencję możesz zamówić na [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**P: Czy istnieją dodatkowe przykłady dla innych formatów archiwów?**  
O: Oczywiście — przeglądaj pełny zestaw przykładów w [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**P: Gdzie mogę uzyskać pomoc lub dyskutować o problemach?**  
O: Dołącz do dyskusji na [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) dla wsparcia społeczności i oficjalnych odpowiedzi.

**P: Czy mogę wypróbować Aspose.Zip za darmo przed zakupem?**  
O: Tak, dostępna jest darmowa wersja próbna na [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## Zakończenie

Postępując zgodnie z powyższymi krokami, wiesz już **jak dodać pliki do tar** i **skompresować tarxz**, a co ważniejsze, **jak utworzyć archiwum tarxz w .net** przy użyciu Aspose.Zip. To podejście daje Ci kompaktowy, przenośny pakiet, który można bezproblemowo zintegrować z dowolnym przepływem pracy .NET — niezależnie od tego, czy tworzysz narzędzie desktopowe, usługę sieciową, czy zautomatyzowany potok CI/CD.

---

**Ostatnia aktualizacja:** 2026-02-23  
**Testowano z:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}