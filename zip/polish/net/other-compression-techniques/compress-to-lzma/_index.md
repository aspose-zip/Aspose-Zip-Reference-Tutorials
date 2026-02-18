---
date: 2025-12-17
description: Dowiedz się, jak kompresować LZMA w Aspose.Zip dla .NET, optymalizując
  efektywność przechowywania i transferu danych.
linktitle: Compress to Lzma
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak skompresować LZMA w Aspose.Zip dla .NET
url: /pl/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak kompresować LZMA w Aspose.Zip dla .NET

## Wprowadzenie

W tym samouczku dowiesz się **jak kompresować LZMA** w Aspose.Zip dla .NET, co jest kluczową umiejętnością optymalizacji przestrzeni dyskowej i zwiększania wydajności transferu danych. Aspose.Zip dla .NET zapewnia potężne rozwiązanie do kompresji plików, oferując wiele algorytmów — w tym LZMA — abyś mógł wybrać najlepsze rozwiązanie dla swojego scenariusza.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Zip for .NET  
- **Jakiego algorytmu dotyczy ten przewodnik?** LZMA compression  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do testów; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 10 minut dla podstawowego pliku.

## Jak kompresować LZMA

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

## Krok 1: Ustaw katalog dokumentów

```csharp
string dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` rzeczywistą ścieżką do folderu, który zawiera pliki, które zamierzasz skompresować.

## Krok 2: Kompresuj plik przy użyciu LZMA

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

Tutaj tworzymy instancję `LzmaArchive`, wskazujemy na plik źródłowy (`alice29.txt`) i zapisujemy skompresowany wynik jako `archive.lzma`.

## Krok 3: Wyświetl komunikat o sukcesie

```csharp
Console.WriteLine("Successfully Compressed a File");
```

Po zakończeniu kompresji, ta linia informuje użytkownika, że operacja zakończyła się sukcesem.

## Zakończenie

Gratulacje! Pomyślnie nauczyłeś się **jak kompresować LZMA** przy użyciu Aspose.Zip dla .NET. Ta efektywna technika kompresji pomaga zmniejszyć zużycie pamięci i przyspieszyć transfery danych, czyniąc Twoje aplikacje bardziej responsywnymi i kosztowo‑efektywnymi.

## Najczęściej zadawane pytania

**P: Czy mogę skompresować wiele plików do jednego archiwum LZMA?**  
O: Tak. Wywołaj `archive.AddFile()` dla każdego pliku przed wywołaniem `archive.Save()`.

**P: Czy istnieje sposób ustawienia poziomu kompresji dla LZMA?**  
O: Klasa `LzmaArchive` używa domyślnego poziomu kompresji, który zapewnia dobrą równowagę między szybkością a rozmiarem. Zaawansowane ustawienia są dostępne poprzez `LzmaEncoder`, jeśli potrzebujesz precyzyjnej kontroli.

**P: Czy powstały plik .lzma będzie działał na platformach nie‑Windows?**  
O: Zdecydowanie tak. Format LZMA jest niezależny od platformy, więc archiwum może być rozpakowane na dowolnym systemie operacyjnym z narzędziem kompatybilnym z LZMA.

**P: Jak rozpakować archiwum LZMA przy użyciu Aspose.Zip?**  
O: Użyj konstruktora `LzmaArchive` z ścieżką do archiwum, a następnie wywołaj `ExtractToDirectory()`, aby wyodrębnić jego zawartość.

**P: Czy Aspose.Zip obsługuje kompresję strumieniową, aby uniknąć ładowania całych plików do pamięci?**  
O: Tak. Możesz pracować ze strumieniami, przekazując obiekty `Stream` do metod `SetSource()` i `Save()`.

---

**Ostatnia aktualizacja:** 2025-12-17  
**Testowano z:** Aspose.Zip for .NET (najnowsza wersja w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}