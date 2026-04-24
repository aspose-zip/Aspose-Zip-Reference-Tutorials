---
date: 2026-04-24
description: Dowiedz się, jak kompresować tar i tworzyć archiwum TarBz2 w .NET przy
  użyciu Aspose.Zip. Ten przewodnik krok po kroku pokazuje, jak dodawać pliki do tar
  i efektywnie generować pliki tarbz2.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: Kompresowanie do TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak skompresować tar i utworzyć TarBz2 przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak skompresować tar i utworzyć TarBz2 przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

W tym samouczku dowiesz się **jak kompresować archiwa tar** i przekształcić je w kompaktowy plik **TarBz2** przy użyciu biblioteki **Aspose.Zip** dla .NET. Niezależnie od tego, czy tworzysz narzędzie do tworzenia kopii zapasowych, publikujesz pakiety wdrożeniowe, czy po prostu potrzebujesz lekkiego pakietu do dystrybucji, poniższe kroki poprowadzą Cię przez dodawanie plików do tar, stosowanie kompresji Bzip2 oraz tworzenie gotowego do udostępnienia archiwum.

Zanim zaczniemy, upewnij się, że masz wymagane elementy wymienione później w tym przewodniku, aby móc podążać bez problemów.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip for .NET  
- **Jak długo trwa implementacja?** Około 5‑10 minut  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa licencja do produkcji; dostępna jest darmowa wersja próbna  
- **Czy mogę kompresować wiele plików?** Tak – dodaj dowolną liczbę wpisów do archiwum tar  
- **Czy jest kompatybilny z .NET 6+?** Absolutnie, Aspose.Zip obsługuje .NET Framework oraz .NET Core/5/6  

## Co to jest archiwum TarBz2?

Plik **TarBz2** łączy tradycyjny kontener **tar** (który zachowuje strukturę katalogów i metadane plików) z kompresją **Bzip2**, tworząc silnie skompresowany pakiet `.tar.bz2`. Ten format jest popularny w systemach podobnych do Unix, ponieważ zapewnia dobrą równowagę między współczynnikiem kompresji a szybkością dekompresji.

## Dlaczego kompresować pliki do TarBz2 przy użyciu Aspose.Zip?

- **Szybkość i prostota** – Jednolinijkowe wywołania API obsługują zarówno tworzenie tar, jak i kompresję Bzip2.  
- **Wieloplatformowość** – Działa na środowiskach .NET w Windows, Linux i macOS.  
- **Precyzyjna kontrola** – Wybierz, które pliki uwzględnić, ustaw własne nazwy wpisów i strumieniuj bezpośrednio na dysk.  
- **Solidne wsparcie .NET** – Idealne dla scenariuszy **tar archive .net**, od aplikacji konsolowych po usługi sieciowe.  

## Prerequisites

- **Aspose.Zip for .NET** – Pobierz najnowszy pakiet ze strony oficjalnej: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Katalog dokumentów** – Folder zawierający pliki, które chcesz zarchiwizować. W przykładach odwołujemy się do niego zmienną `dataDir`.

> **Porada:** Przechowuj pliki źródłowe w dedykowanym folderze, aby uniknąć przypadkowego dołączenia niechcianych plików.

## Importowanie przestrzeni nazw

Najpierw zaimportuj wymagane przestrzenie nazw, aby uzyskać dostęp do klas Tar i Bzip2 biblioteki Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Krok 1: Ustaw katalog dokumentów

Zdefiniuj ścieżkę wskazującą na folder zawierający pliki, które chcesz zarchiwizować.

```csharp
string dataDir = "Your Document Directory";
```

> Zastąp `"Your Document Directory"` absolutną lub względną ścieżką do folderu źródłowego.

## Krok 2: Dodaj pliki do tar i utwórz archiwum TarBz2

Główną częścią procesu jest utworzenie `TarArchive`, dodanie wpisów, a następnie opakowanie go w `Bzip2Archive`. Poniższy kod demonstruje **jak utworzyć tar** i skompresować go do **TarBz2** w czystym stylu wzorca disposable.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **dodaje pliki do tar** – możesz wywołać tę metodę dla każdego pliku, który ma się znaleźć w archiwum.  
- `bz2.SetSource(archive)` informuje archiwum Bzip2, aby skompresować cały strumień tar.  
- `bz2.Save(...)` zapisuje końcowy plik **TarBz2** na dysku.

**Wskazówka:** Aby **dodać pliki do tar** hurtowo, po prostu powtórz `archive.CreateEntry` dla każdego pliku przed wywołaniem `bz2.Save`.

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| **Błąd: plik nie znaleziony** | Nieprawidłowa ścieżka `dataDir` lub brak rozszerzenia pliku | Sprawdź pełną ścieżkę i upewnij się, że plik istnieje. |
| **Puste archiwum** | Nie dodano żadnych wpisów przed wywołaniem `bz2.Save` | Dodaj przynajmniej jedno wywołanie `CreateEntry`. |
| **Odmowa dostępu** | Aplikacja nie ma uprawnień do zapisu w folderze wyjściowym | Uruchom aplikację z odpowiednimi uprawnieniami lub wybierz folder z prawem zapisu. |

## Najczęściej zadawane pytania

**P:** Czy Aspose.Zip jest kompatybilny ze wszystkimi aplikacjami .NET?  
**O:** Tak. Działa z .NET Framework, .NET Core, .NET 5/6 oraz nowszymi środowiskami uruchomieniowymi.

**P:** Czy mogę kompresować wiele plików jednocześnie?  
**O:** Oczywiście. Wywołaj `CreateEntry` dla każdego pliku przed zapisaniem archiwum.

**P:** Gdzie mogę znaleźć dodatkową dokumentację?  
**O:** Szczegółowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/zip/net/).

**P:** Jak uzyskać tymczasową licencję dla Aspose.Zip?  
**O:** Możesz ją zamówić [tutaj](https://purchase.aspose.com/temporary-license/).

**P:** Czy dostępna jest darmowa wersja próbna?  
**O:** Tak, wersję próbną można pobrać [tutaj](https://releases.aspose.com/).

## Zakończenie

Teraz już wiesz **jak kompresować tar**, dodawać do niego pliki i opakować wynik w strumień Bzip2, aby uzyskać archiwum **TarBz2** przy użyciu Aspose.Zip dla .NET. To podejście jest szybkie, niezawodne i działa na wszystkich nowoczesnych platformach .NET. Śmiało eksperymentuj z większymi zestawami plików, własnymi nazwami wpisów lub zintegrować kod z własnymi procesami tworzenia kopii zapasowych lub wdrożeń.

Jeśli napotkasz jakiekolwiek problemy, społeczność Aspose.Zip jest gotowa pomóc — wystarczy przejść na [forum wsparcia Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Ostatnia aktualizacja:** 2026-04-24  
**Testowano z:** Aspose.Zip for .NET (najnowsze wydanie)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}