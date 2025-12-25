---
date: 2025-12-25
description: Dowiedz się, jak tworzyć pliki 7z przy użyciu Aspose.Zip dla .NET, obejmując
  siedem metod kompresji 7z, takich jak LZMA2, BZip2 i Store. Idealne do scenariuszy
  kompresji folderu do formatu 7z.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak tworzyć pliki 7z – Poradnik Aspose.Zip dla .NET
url: /pl/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć pliki 7z – Samouczek Aspose.Zip dla .NET

## Wstęp

Jeśli potrzebujesz **tworzyć archiwa 7z** programowo w aplikacji .NET, trafiłeś we właściwe miejsce. Aspose.Zip dla .NET umożliwia łatwe generowanie archiwów Seven Zip przy użyciu dowolnego z obsługiwanych algorytmów kompresji, niezależnie od tego, czy chcesz **skompresować folder do 7z** w celu dystrybucji, czy po prostu potrzebujesz niezawodnego rozwiązania **seven zip archive .net**. W tym przewodniku przejdziemy przez trzy popularne metody kompresji — LZMA2, BZip2 i Store (bez kompresji) — i pokażemy, jak w kilku linijkach kodu C# stworzyć plik 7z.

## Szybkie odpowiedzi
- **Jakiej biblioteki użyć?** Aspose.Zip dla .NET oferuje najbardziej kompletny zestaw funkcji Seven Zip.  
- **Która metoda kompresji daje najlepszy współczynnik?** LZMA2 zazwyczaj zapewnia najwyższą kompresję dla mieszanych danych.  
- **Czy mogę stworzyć 7z bez kompresji?** Tak — użyj metody Store (bez kompresji).  
- **Czy potrzebna jest licencja do rozwoju?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy to działa z .NET 6/7?** Oczywiście — Aspose.Zip obsługuje .NET Framework, .NET Core oraz .NET 5+.

## Jakie są metody kompresji Seven Zip?

Seven Zip obsługuje kilka algorytmów, z których każdy jest zoptymalizowany pod kątem innych scenariuszy:

* **LZMA2** – wysoki współczynnik kompresji, idealny dla dużych plików o mieszanym typie.  
* **BZip2** – solidna kompresja, ale wolniejsza niż LZMA2; przydatna, gdy wymagana jest kompatybilność ze starszymi narzędziami.  
* **Store** – brak kompresji; doskonała, gdy potrzebujesz jedynie archiwizacji bez zmniejszania rozmiaru (np. przy zachowywaniu oryginalnych znaczników czasu plików).

Zrozumienie tych **seven zip compression methods** pomaga wybrać właściwe ustawienie dla Twojego projektu.

## Wymagania wstępne

Zanim przejdziesz dalej, upewnij się, że masz:

- Podstawową znajomość C# i Visual Studio.  
- Zainstalowaną bibliotekę Aspose.Zip dla .NET. Pobierz ją ze strony **[tutaj](https://releases.aspose.com/zip/net/)**.  
- Folder (`dataDir`) zawierający pliki, które chcesz zarchiwizować.

## Importowanie przestrzeni nazw

Najpierw dodaj wymagane przestrzenie nazw do swojego pliku C#:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Te klasy dają dostęp do ustawień kompresji i obsługi archiwów.

## Kompresja LZMA2 – Jak stworzyć 7z z maksymalnym współczynnikiem

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Wskazówka:** LZMA2 działa najlepiej, gdy pliki źródłowe mają rozmiar większy niż 1 MB. Dla wielu małych plików BZip2 może być szybszy.

## Kompresja BZip2 – Zrównoważony wybór

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 oferuje solidną kompresję przy zachowaniu rozsądnej prędkości, co czyni go dobrą alternatywą, gdy LZMA2 nie jest obsługiwane w docelowym środowisku.

## Store (bez kompresji) – Gdy rozmiar nie ma znaczenia

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Użyj metody Store, jeśli po prostu potrzebujesz połączyć pliki bez zmiany ich rozmiaru — idealne do zachowania oryginalnych znaczników czasu lub gdy archiwum będzie dekompresowane w locie.

## Typowe przypadki użycia

| Scenariusz | Zalecana metoda |
|------------|-----------------|
| Dystrybucja dużych instalatorów | LZMA2 |
| Udostępnianie logów starszym narzędziom | BZip2 |
| Pakowanie plików do szybkiego wyodrębniania | Store (bez kompresji) |
| Potrzeba **compress folder to 7z** w czasie rzeczywistym w usłudze webowej | LZMA2 (dla najlepszego współczynnika) |

## Rozwiązywanie problemów i wskazówki

- **Brak plików w archiwum?** Sprawdź, czy `dataDir` wskazuje na właściwy katalog i czy proces ma uprawnienia odczytu.  
- **Archiwum nie otwiera się w starszych wersjach 7‑Zip?** Trzymaj się BZip2 lub Store, ponieważ LZMA2 może wymagać nowszych bibliotek dekompresyjnych.  
- **Wąskie gardło wydajności?** Dla bardzo dużych zestawów danych rozważ strumieniowanie archiwum zamiast ładowania wszystkich wpisów do pamięci.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Zip dla .NET z dowolnym typem pliku?**  
O: Tak, Aspose.Zip obsługuje szeroką gamę formatów plików, umożliwiając kompresję i dekompresję praktycznie każdego typu.

**P: Czy dostępna jest bezpłatna wersja próbna Aspose.Zip dla .NET?**  
O: Tak, bezpłatną wersję próbną można pobrać **[tutaj](https://releases.aspose.com/)**.

**P: Gdzie znajdę dokumentację Aspose.Zip dla .NET?**  
O: Pełna referencja API jest dostępna **[tutaj](https://reference.aspose.com/zip/net/)**.

**P: Jak mogę uzyskać tymczasowe licencje dla Aspose.Zip dla .NET?**  
O: Tymczasowe licencje można uzyskać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**P: Gdzie mogę uzyskać wsparcie dla Aspose.Zip dla .NET?**  
O: Wsparcie dostępne jest na **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Ostatnia aktualizacja:** 2025-12-25  
**Testowano z:** Aspose.Zip dla .NET 24.12  
**Autor:** Aspose  

---