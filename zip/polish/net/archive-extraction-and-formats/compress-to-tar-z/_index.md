---
date: 2026-02-15
description: Dowiedz się, jak dodawać pliki do archiwum tar i kompresować je do formatu
  TarZ przy użyciu Aspose.Zip dla .NET – krok po kroku przewodnik po efektywnym zarządzaniu
  plikami w .NET.
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dodaj pliki do tar i skompresuj do TarZ przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj pliki do tar i skompresuj do TarZ przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

Jeśli potrzebujesz **dodać pliki do tar** i następnie skompresować archiwum do formatu TarZ, Aspose.Zip dla .NET sprawia, że cały proces jest bezproblemowy. W tym samouczku przeprowadzimy Cię przez każdy krok — od konfiguracji projektu po utworzenie archiwum tar, dodanie plików i ostateczne zapisanie skompresowanego pliku .tar.z. Po zakończeniu będziesz mieć ponownie używalny fragment kodu, który możesz wstawić do dowolnej aplikacji .NET.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje tworzenie tar?** Aspose.Zip for .NET  
- **Ile linii kodu?** Około 15 linii (bez komentarzy)  
- **Czy potrzebna jest licencja do testów?** Dostępna jest darmowa wersja próbna; licencja jest wymagana w produkcji.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Czy mogę kompresować foldery, a nie tylko pliki?** Tak — możesz dodać całe katalogi za pomocą pętli.

## Co to jest **add files to tar**?

Dodawanie plików do archiwum tar łączy je w jeden, nieskompresowany kontener, który zachowuje strukturę katalogów oraz metadane plików. Tar jest klasycznym formatem Unix i stanowi podstawę wielu procesów kompresji, w tym formatu TarZ używanego w tym przewodniku.

## Dlaczego dodawać pliki do tar przed kompresją do TarZ?
- **Portability** – Archiwum tar działa na różnych platformach bez konieczności zarządzania pojedynczymi plikami.  
- **Speed** – Tworzenie kontenera tar jest szybkie; kolejna kompresja Z skupia się wyłącznie na zmniejszeniu rozmiaru.  
- **Compatibility** – Wiele starszych narzędzi oczekuje pliku `.tar` przed zastosowaniem kompresji w stylu gzip, co dokładnie zapewnia `.tar.z`.  

### Dlaczego ma to znaczenie dla programistów .NET
Użycie kontenera tar pozwala utrzymać kod .NET prosty i deterministyczny. Możesz generować archiwum w pamięci, strumieniować je bezpośrednio w odpowiedzi lub zapisać na dysku, nie zajmując się tymczasowymi plikami zip. Ten wzorzec jest szczególnie przydatny w pipeline'ach budowania, agregacji logów lub gdy musisz przesłać zestaw plików konfiguracyjnych do usługi opartej na Linuksie.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnij się, że masz:

- **Aspose.Zip for .NET** zainstalowany. Pobierz go z oficjalnej strony [here](https://releases.aspose.com/zip/net/).  
- Folder na swoim komputerze, który zawiera pliki, które chcesz zarchiwizować. Zamień ścieżkę zastępczą na swoją rzeczywistą lokalizację.

## Importowanie przestrzeni nazw

Add the required `using` statements at the top of your C# file:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Wskazówka:** Użyj `Path.Combine`, jeśli musisz dynamicznie budować ścieżki; zapobiega to brakującym separatorom ścieżek na różnych systemach operacyjnych.

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj katalog dokumentów

```csharp
string dataDir = "Your Document Directory";
```

> **Dlaczego ten krok jest ważny:** `dataDir` pełni funkcję podstawowej lokalizacji dla każdego pliku, który dodasz. Przechowywanie go w jednej zmiennej ułatwia utrzymanie kodu i ponowne użycie w wielu archiwach.

### Krok 2: Utwórz archiwum Tar i dodaj pliki

#### 2.1: Utwórz instancję archiwum Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> Blok `using` zapewnia, że obiekt `TarArchive` zostanie prawidłowo zwolniony, uwalniając wszelkie uchwyty plików lub bufory pamięci.

#### 2.2: Add files to the archive  

Inside the `using` block, add each file you want to include:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Możesz powtórzyć `CreateEntry` dla dowolnej liczby plików lub przejść pętlą po katalogu, aby dodać je programowo. Na przykład pętla `foreach (var file in Directory.GetFiles(dataDir))` pozwoli obsłużyć dowolną liczbę plików, zachowując ich względne ścieżki.

#### 2.3: Save the compressed TarZ file  

After adding all entries, compress the tar archive to the `.tar.z` format:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

Powstały plik `archive.tar.z` znajdzie się w tym samym folderze, który określiłeś w `dataDir`. Teraz możesz wysłać ten pojedynczy, skompresowany pakiet do dowolnego systemu, który rozumie TarZ.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **Plik nie znaleziony** | Nieprawidłowa ścieżka lub brak rozszerzenia pliku | Sprawdź, czy `dataDir` kończy się separatorem ścieżki i czy nazwy plików są poprawne. |
| **Odmowa dostępu** | Niewystarczające uprawnienia w docelowym folderze | Uruchom aplikację z odpowiednimi uprawnieniami lub wybierz katalog zapisu. |
| **Skompresowany plik jest większy niż oczekiwano** | Oryginalne pliki już są skompresowane (np. obrazy, wideo) | TarZ najlepiej działa na plikach tekstowych lub logach; rozważ pozostawienie już skompresowanych plików bez zmian. |

### Typowe pułapki, na które należy uważać
- **Brak końcowego ukośnika** – Jeśli `dataDir` nie kończy się `\` lub `/`, konkatenacja ciągów utworzy nieprawidłową ścieżkę.  
- **Duże katalogi** – Dodawanie tysięcy plików może zużywać pamięć; rozważ strumieniowanie wpisów lub użycie przeciążenia `TarArchive`, które zapisuje bezpośrednio do strumienia pliku.  
- **Problemy z kodowaniem** – Nazwy plików nie‑ASCII mogą wymagać explicite obsługi kodowania; Aspose.Zip domyślnie obsługuje UTF‑8, ale zweryfikuj to na docelowej platformie.

## Najczęściej zadawane pytania

**Q: Czy mogę kompresować całe foldery przy użyciu Aspose.Zip for .NET?**  
A: Oczywiście. Użyj pętli `Directory.GetFiles` i wywołaj `CreateEntry` dla każdego pliku, zachowując względne ścieżki.

**Q: Czy dostępna jest wersja próbna Aspose.Zip for .NET?**  
A: Tak, możesz zapoznać się z możliwościami Aspose.Zip for .NET, pobierając darmową wersję próbną [here](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć pełną dokumentację Aspose.Zip for .NET?**  
A: Dokumentacja jest dostępna [here](https://reference.aspose.com/zip/net/), oferując szczegółowe informacje o funkcjach i użyciu biblioteki.

**Q: Jak mogę uzyskać wsparcie dla Aspose.Zip for .NET?**  
A: Odwiedź [forum Aspose.Zip](https://forum.aspose.com/c/zip/37), aby uzyskać pomoc, podzielić się doświadczeniami i połączyć się ze społecznością.

**Q: Czy mogę uzyskać tymczasową licencję dla Aspose.Zip for .NET?**  
A: Tak, jeśli potrzebujesz tymczasowej licencji, możesz ją uzyskać [here](https://purchase.aspose.com/temporary-license/).

## Podsumowanie

Teraz wiesz, jak **dodać pliki do tar** i skompresować wynik do archiwum TarZ przy użyciu Aspose.Zip for .NET. To podejście zapewnia czysty, przenośny pakiet, który można łatwo przenieść, przechowywać lub dalej przetwarzać. Śmiało dostosuj fragment kodu do przetwarzania wsadowego katalogów, integracji w pipeline'ach budowania lub połączenia z innymi komponentami Aspose w celu uzyskania bardziej rozbudowanych przepływów dokumentów.

---

**Ostatnia aktualizacja:** 2026-02-15  
**Testowano z:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}