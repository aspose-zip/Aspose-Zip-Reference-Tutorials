---
date: 2026-02-05
description: Dowiedz się, jak dodawać pliki do archiwum tar i tworzyć archiwa tarxz
  w .NET przy użyciu Aspose.Zip. Ten przewodnik pokazuje, jak kompresować pliki do
  formatu tarxz z wysoką wydajnością.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dodaj pliki do tar, utwórz archiwum tarxz w .NET przy użyciu Aspose.Zip
url: /pl/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać pliki do tar, utworzyć archiwum tarxz w .NET z Aspise.Zip

## Wprowadzenie

Jeśli potrzebujesz **dodawania plików do tar** i następnie skompresowania ich do archiwum tarxz przy użyciu .NET, Aspose.Zip for .NET upraszcza ten proces, czyniąc go prostym i niezawodnym. Niezależnie od tego, czy pakujesz logi, pliki konfiguracyjne, czy inne zasoby do przechowywania lub transmisji, kompresja do formatu TarXz zapewnia wysoki współczynnik kompresji, zachowując jednocześnie znaną strukturę tar. W tym samouczku przeprowadzimy Cię krok po kroku – wraz z fragmentami kodu – abyś mógł z pewnością zintegrować tworzenie tarxz w swoich aplikacjach .NET.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa?** `TarArchive` z `Aspose.Zip.Tar`
- **Jak skompresować tarxz?** Użyj `SaveXzCompressed` po dodaniu wpisów
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Czy wymagana licencja?** Tak, ważna licencja Aspose.Zip do produkcji
- **Typowy czas implementacji?** ~5‑10 minut

## Co to jest archiwum TarXz?

**TarXz archive** łączy tradycyjny kontener Unix `tar` z kompresją XZ. Część tar grupuje wiele plików w jeden strumień, podczas gdy XZ zapewnia silną, bezstratną kompresję. Ten format jest popularny przy dystrybucji kodu źródłowego, kopii zapasowych i dużych zestawów danych, ponieważ zachowuje strukturę katalogów i osiąga mniejsze rozmiary plików niż zwykły tar czy zip.

## Dlaczego dodawać pliki do tar i kompresować do tarxz przy użyciu Aspose.Zip?

- **Wysoki współczynnik kompresji** – XZ często kompresuje o 30‑50 % bardziej niż gzip.  
- **Kompatybilność wieloplatformowa** – Pliki TarXz można otworzyć na Linux, macOS i Windows.  
- **Proste API** – Aspose.Zip abstrahuje szczegóły niskiego poziomu, pozwalając skupić się na logice biznesowej.  
- **Brak zewnętrznych narzędzi** – Wszystko działa wewnątrz procesu .NET, idealne dla chmury lub potoków CI.  

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz:

- **Aspose.Zip for .NET** zainstalowany (pobierz z oficjalnej [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Folder zawierający pliki, które chcesz zarchiwizować. W poniższych przykładach folder ten jest odwoływany zmienną `dataDir`.  
- Ważną licencję Aspose.Zip (opcjonalnie do oceny, wymagana w produkcji).

## Importowanie przestrzeni nazw

Najpierw zaimportuj przestrzenie nazw, które udostępniają funkcjonalność TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak dodać pliki do tar przy użyciu Aspose.Zip

### Krok 1: Zainicjalizuj `TarArchive`

Utwórz nową instancję `TarArchive`, która będzie przechowywać pliki do kompresji.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tip:** Instrukcja `using` zapewnia prawidłowe zwolnienie zasobów archiwum, uwalniając wszelkie niezarządzane zasoby.

### Krok 2: Dodaj pliki do archiwum

Dodaj każdy plik, który chcesz uwzględnić. W tym przykładzie dodajemy dwa pliki tekstowe, ale możesz dodać dowolną liczbę wpisów.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Dlaczego to ważne:** Dodawanie wpisów przed kompresją pozwala Aspose.Zip najpierw zbudować kontener tar, a dopiero potem zastosować kompresję XZ w jednym kroku.

### Krok 3: Zapisz archiwum z kompresją XZ

Na koniec zapisz archiwum tar na dysku, używając kompresji XZ. Powstały plik będzie miał rozszerzenie `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Wynik:** Masz teraz w pełni skompresowany plik `archive.tar.xz`, który może być przesyłany, przechowywany lub rozpakowywany na dowolnej platformie obsługującej TarXz.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **„File not found” exception** | Nieprawidłowa ścieżka `dataDir` | Sprawdź, czy ścieżka katalogu kończy się backslashem (`\`) lub użyj `Path.Combine`. |
| **Duże zużycie pamięci** | Bardzo duże pliki kompresowane w pamięci | Użyj `TarArchive` w trybie strumieniowym (`przeciążenie SaveXzCompressed przyjmujące `Stream`). |
| **Licencja nie zastosowana** | Brak pliku licencji | Załaduj licencję przy starcie aplikacji: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Zip jest kompatybilny ze wszystkimi środowiskami .NET?**  
A: Tak, Aspose.Zip działa z .NET Framework 4.5+, .NET Core 3.1+, oraz .NET 5/6+. Zobacz [documentation](https://reference.aspose.com/zip/net/) po szczegóły.

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Zip?**  
A: Możesz poprosić o tymczasową licencję na [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**Q: Czy istnieją dodatkowe przykłady dla innych formatów archiwów?**  
A: Oczywiście — przeglądaj pełny zestaw przykładów w [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: Gdzie mogę uzyskać pomoc lub dyskutować o problemach?**  
A: Dołącz do dyskusji na [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) dla wsparcia społeczności i oficjalnych odpowiedzi.

**Q: Czy mogę wypróbować Aspose.Zip za darmo przed zakupem?**  
A: Tak, dostępna jest darmowa wersja próbna na [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## Zakończenie

Postępując zgodnie z powyższymi krokami, wiesz już **jak dodać pliki do tar** i **tworzyć archiwa tarxz** przy użyciu Aspose.Zip w .NET. To podejście zapewnia kompaktowy, przenośny pakiet, który można płynnie zintegrować z dowolnym przepływem pracy .NET — niezależnie od tego, czy tworzysz narzędzie desktopowe, usługę webową, czy zautomatyzowany potok CI/CD.

---

**Ostatnia aktualizacja:** 2026-02-05  
**Testowano z:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}