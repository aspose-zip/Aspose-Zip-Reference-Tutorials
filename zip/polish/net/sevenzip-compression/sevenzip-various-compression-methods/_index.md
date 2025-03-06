---
title: Tworzenie siedmiu plików Zip - samouczek Aspose.Zip dla .NET
linktitle: SevenZip z różnymi metodami kompresji
second_title: Aspose.Zip .NET API do kompresji i archiwizacji plików
description: Dowiedz się, jak tworzyć pliki Seven Zip za pomocą Aspose.Zip dla .NET przy użyciu różnych metod kompresji. Proste kroki dla LZMA2, BZip2 i Store (bez kompresji).
weight: 12
url: /pl/net/sevenzip-compression/sevenzip-various-compression-methods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie siedmiu plików Zip - samouczek Aspose.Zip dla .NET


## Wstęp

dziedzinie programowania .NET zarządzanie i kompresowanie plików jest częstym zadaniem. Aspose.Zip dla .NET zapewnia potężne rozwiązanie do pracy ze skompresowanymi archiwami, oferując różnorodne metody kompresji. W tym samouczku przyjrzymy się, jak używać Aspose.Zip dla .NET do tworzenia plików Seven Zip przy użyciu różnych metod kompresji.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość programowania w języku C#.
- Program Visual Studio zainstalowany na Twoim komputerze.
-  Biblioteka Aspose.Zip dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/zip/net/).

## Importuj przestrzenie nazw

Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do projektu C#. Aby rozpocząć, użyj następującego fragmentu kodu:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Kompresja LZMA2

```csharp
//ExStart: SevenZip z różnymi metodami kompresji

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZip z różnymi metodami kompresji
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## Kompresja BZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Sklep, bez kompresji

```csharp
//Sklep, bez kompresji
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Wniosek

tym samouczku zbadaliśmy wszechstronność Aspose.Zip dla .NET w tworzeniu plików Seven Zip przy użyciu różnych metod kompresji. Niezależnie od tego, czy potrzebujesz wysokich współczynników kompresji, czy wolisz nie stosować jej wcale, Aspose.Zip zapewnia elastyczność, która spełni Twoje wymagania.

## Często zadawane pytania

### Czy mogę używać Aspose.Zip dla .NET z dowolnym typem pliku?
Tak, Aspose.Zip dla .NET obsługuje szeroką gamę typów plików, umożliwiając kompresję i dekompresję różnych formatów.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Zip dla .NET?
 Tak, możesz uzyskać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dokumentację Aspose.Zip dla .NET?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/zip/net/).

### Jak mogę uzyskać tymczasowe licencje na Aspose.Zip dla .NET?
 Można uzyskać licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Zip dla .NET?
 Możesz szukać wsparcia na stronie[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
