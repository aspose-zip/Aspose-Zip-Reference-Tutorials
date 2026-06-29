---
date: 2026-06-29
description: Dowiedz się, jak skompresować folder do 7z przy użyciu Aspose.Zip dla
  .NET, obejmując siedem metod kompresji zip, takich jak LZMA2, BZip2 i Store. Idealne
  do programowego tworzenia archiwów 7z.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip z różnymi metodami kompresji
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak skompresować folder do 7z – Aspose.Zip dla .NET Samouczek
url: /pl/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak skompresować folder do 7z – Aspose.Zip dla .NET Tutorial

## Wprowadzenie

Jeśli potrzebujesz **skompresować folder do 7z** archiwów programowo w aplikacji .NET, trafiłeś we właściwe miejsce. Aspose.Zip dla .NET umożliwia łatwe generowanie archiwów Seven Zip przy użyciu dowolnego z obsługiwanych algorytmów kompresji, niezależnie od tego, czy chcesz spakować cały katalog do dystrybucji, czy po prostu potrzebujesz niezawodnego **seven zip archive .net** rozwiązania. W tym przewodniku przejdziemy przez trzy popularne metody kompresji — LZMA2, BZip2 i Store (bez kompresji) — i pokażemy dokładnie, jak w kilku linijkach kodu C# wygenerować plik 7z.

## Szybkie odpowiedzi
- **Jaką bibliotekę powinienem używać?** Aspose.Zip dla .NET zapewnia najbardziej kompletny zestaw funkcji Seven Zip.  
- **Która metoda kompresji daje najlepszy współczynnik?** LZMA2 zazwyczaj zapewnia najwyższą kompresję dla mieszanych danych.  
- **Czy mogę utworzyć 7z bez kompresji?** Tak — użyj metody Store (bez kompresji).  
- **Czy potrzebna jest licencja do rozwoju?** Dostępna jest darmowa wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy jest kompatybilny z .NET 6/7?** Absolutnie — Aspose.Zip obsługuje .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 oraz .NET 5–10.

## Jakie są metody kompresji Seven Zip?

Seven Zip obsługuje kilka algorytmów, z których każdy jest zoptymalizowany pod różne scenariusze. **LZMA2** oferuje najwyższy współczynnik kompresji (często 30‑40 % mniejszy niż BZip2), **BZip2** zapewnia solidną kompresję z szerszym wsparciem starszych narzędzi, a **Store** po prostu archiwizuje pliki bez ich zmniejszania, zachowując oryginalne znaczniki czasu w pełni.

## Wymagania wstępne

Zanim przejdziemy dalej, upewnij się, że masz:

- Podstawową znajomość C# i Visual Studio.  
- Zainstalowaną bibliotekę Aspose.Zip dla .NET. Pobierz ją ze strony **[tutaj](https://releases.aspose.com/zip/net/)**.  
- Folder (`dataDir`) zawierający pliki, które chcesz zarchiwizować.

## Importowanie przestrzeni nazw

Najpierw dodaj wymagane przestrzenie nazw do swojego pliku C#:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Te klasy dają dostęp do ustawień kompresji i obsługi archiwów.

## Kompresja LZMA2 – Jak utworzyć 7z z maksymalnym współczynnikiem

Klasa `Archive` reprezentuje archiwum 7z, które może zawierać wiele plików.  
Algorytm LZMA2 zapewnia najwyższy współczynnik kompresji spośród obsługiwanych metod. Działa, dzieląc dane wejściowe na bloki i stosując zaawansowaną kompresję słownikową. W Aspose.Zip ustawiasz `CompressionMethod` na `CompressionMethod.Lzma2` w obiekcie `Archive` przed dodaniem plików.

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

> **Pro tip:** LZMA2 działa najlepiej, gdy pliki źródłowe mają rozmiar większy niż 1 MB. Dla wielu małych plików BZip2 może być szybszy.

## Kompresja BZip2 – Zrównoważony wybór

Klasa `Archive` reprezentuje archiwum 7z, które może zawierać wiele plików.  
BZip2 oferuje solidną kompresję z dobrą kompatybilnością ze starszymi narzędziami. Wykorzystuje transformację Burrows‑Wheeler oraz kodowanie Huffmana, aby zmniejszyć rozmiar. W Aspose.Zip wybierasz `CompressionMethod.BZip2` przy konfigurowaniu instancji `Archive`, co zapewnia równowagę między szybkością a współczynnikiem kompresji dla większości plików tekstowych i binarnych.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 zapewnia solidną kompresję przy zachowaniu rozsądnej szybkości, co czyni go dobrym rozwiązaniem awaryjnym, gdy LZMA2 nie jest obsługiwane w docelowym środowisku.

## Store (bez kompresji) – Gdy rozmiar nie ma znaczenia

Klasa `Archive` reprezentuje archiwum 7z, które może zawierać wiele plików.  
Metoda Store tworzy archiwum bez kompresowania danych. Po prostu kopiuje oryginalne pliki do kontenera 7z, zachowując znaczniki czasu i strukturę katalogów. Aby użyć jej w Aspose.Zip, ustaw `CompressionMethod.Store` w obiekcie `Archive` przed dodaniem plików, które chcesz spakować.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Użyj metody Store, jeśli potrzebujesz po prostu połączyć pliki bez zmiany ich rozmiaru — idealne do zachowania oryginalnych znaczników czasu lub gdy archiwum będzie dekompresowane „w locie”.

## Jak dodać pliki do 7z?

Dodaj pliki do archiwum 7z, tworząc instancję `Archive`, ustawiając żądaną `CompressionMethod` i wywołując `AddAllFiles(dataDir)`. Metoda skanuje określony folder rekurencyjnie, zachowując hierarchię katalogów wewnątrz archiwum. To podejście pozwala **skompresować folder do 7z** jedną linią kodu po wstępnej konfiguracji.

## Typowe przypadki użycia

| Scenariusz | Zalecana metoda |
|------------|-----------------|
| Dystrybucja dużych instalatorów | LZMA2 |
| Udostępnianie logów starszym narzędziom | BZip2 |
| Pakowanie plików do szybkiego wyodrębniania | Store (bez kompresji) |
| Potrzeba **skompresować folder do 7z** w locie w usłudze webowej | LZMA2 (dla najlepszego współczynnika) |

## Rozwiązywanie problemów i wskazówki

- **Brak plików w archiwum?** Sprawdź, czy `dataDir` wskazuje na właściwy katalog i czy proces ma uprawnienia odczytu.  
- **Archiwum nie otwiera się w starszych wersjach 7‑Zip?** Trzymaj się BZip2 lub Store, ponieważ LZMA2 może wymagać nowszych bibliotek dekompresujących.  
- **Wąskie gardło wydajności?** Dla ogromnych zestawów danych rozważ strumieniowanie archiwum zamiast ładowania wszystkich wpisów do pamięci.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Zip dla .NET z dowolnym typem pliku?**  
O: Tak, Aspose.Zip obsługuje szeroką gamę formatów plików, umożliwiając kompresję i dekompresję praktycznie każdego typu pliku.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Zip dla .NET?**  
O: Tak, darmową wersję próbną można uzyskać **[tutaj](https://releases.aspose.com/)**.

**P: Gdzie mogę znaleźć dokumentację Aspose.Zip dla .NET?**  
O: Pełna referencja API jest dostępna **[tutaj](https://reference.aspose.com/zip/net/)**.

**P: Jak mogę uzyskać tymczasowe licencje dla Aspose.Zip dla .NET?**  
O: Tymczasowe licencje można uzyskać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**P: Gdzie mogę uzyskać wsparcie dla Aspose.Zip dla .NET?**  
O: Wsparcie dostępne jest na **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

---

**Ostatnia aktualizacja:** 2026-06-29  
**Testowano z:** Aspose.Zip dla .NET 24.12  
**Autor:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [compress files c# – Create 7z archive with Aspose.Zip for .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [How to Zip Folder Using Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [How to Compress LZMA in Aspose.Zip for .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}