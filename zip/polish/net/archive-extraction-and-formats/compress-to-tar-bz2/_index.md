---
date: 2026-02-02
description: Dowiedz się, jak dodawać pliki do archiwum tar i kompresować pliki do
  formatu tarbz2 w .NET przy użyciu Aspose.Zip. Ten przewodnik krok po kroku pokazuje,
  jak efektywnie tworzyć archiwa tarbz2.
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Dodaj pliki do tar i skompresuj do TarBz2 przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj pliki do tar i skompresuj do TarBz Aspose.Zip dla .NET

## Wprowadzenie

Witamy w naszym kompleksowym przewodniku dotyczącym **add files to tar** i kompresji do formatu TarBz2 przy użyciu Aspose.Zip dla . pakiety wdrożeniowe, czy po prostu potrzebujesz kompaktowego archiwum do dystrybucji, ten samouczek przeprowadzi Cię przez każdy krok z jasnymi wyjaśnieniami, praktycznymi wskazówkami i scenariuszami użycia.

Zanim zaczniemy, upewnijmy się, że masz wszystko, czego potrzebujesz.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip for .NET  
- **Jak licencji?** Wymagana jest tymczasowa licencja do produkcji; dostępna jest darmowa wersja próbna  
- **Czy mogę kompresować wiele plików?** Tak – możesz dodać dowolną liczbę wpisów, Aspose.Zip obsługuje .NET Framework oraz .NET Core/5/6  

## Co to jest „add files to tar”?
Dodawanie plików do **tar** (Tape Archive) tworzy pojedynczy niekompresowany kontener, który zachowuje strukturę katalogów i metadane plików. Gdy następnie zastosujesz kompresję Bzip2, otrzymasz archiwum **tar.bz2** (TarBz2) — idealne do efektywnego przechowywania i transferu.

## Dlaczego kompresować pliki do TarBz2 przy użyciu Aspose.Zip?
- **Szybkość i prostota** – Jednolinijkowe wywołania API obsługują zarówno tworzenie tar, jak i kompresję Bzip2.  
- **W.  
ględnić, ustaw niestandardowe nazwy wpisów i strumieniuj bezpośrednio na dysk.  

## Wymagania wstępne

- **Aspose.Zip for .NET** – Pobierz najnowszy pakiet ze strony oficjalnej: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – Folder zawierający pliki, które chcesz zarchiwizować. W przykładach odwołujemy się do niego zmienną `dataDir`.

> **Wskazówka:** Przechowuj pliki źródłowe w dedykowanym folderze, aby uniknąć przypadkowego dołączenia niechcianych plików.

## Importowanie dostęp do klas Tar i Bzip2 z Aspose.Zip.

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

Główną częścią procesu jest utworzenie `TarArchive`, dodanie wpisów, a następnie opakowanie go w `Bzip2Archive`. Poniższy kod demonstruje **jak stworzyć tarbz2** w czystym stylu z wzorcem disposable.

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

- `CreateEntry` dodaje każdy plik do kontenera **um Bzip2, aby skompresowało cały strumień tar.  
- `bz2.Save(...)` zapisuje końcowy plik **tar.bz2** na dysku.

**Wskazówka:** Aby **skompresować pliki do tarbz2** hurtowo, po prostu powtórz `archive.CreateEntry` dla każdego potrzebnego pliku.

## Jak utworzyć archiwum tarbz2 – lista kontrolna krok po kroku
1. Przygotuj folder źródłowy (`dataDir`).  
2. Zainicjuj `TarArchive` i dodaj każdy plik przy użyciu `CreateEntry`.  
3..bz2**.  

Stosowanie tej listy kontrolnej zapewnia spójny przepływ pracy **generowania archiwum tarbz2**.

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| **Błąd: plik nie znaleziony** | Nieprawidłowa ścieżka `data i upewnij się, że plik istnieje. |
| **Puste archiwum** | Brak wpisów dodanych przed wywołaniem `bz2.Save` | Dodaj przynajmniej jedno wywołanie `CreateEntry`. |
| **Odmowa dostępu** | Aplikacja nie ma uprawnień do zapisu w folderze wyjściowym | Uruchom aplikację z odpowiednimi uprawnieniami lub wybierz folder, do którego można zapisywać. |

## Najczęściej zadawane pytania

**P:** Czy Aspose.Zip jest kompatybilny ze .NET Framework, .NET Core, .NET 5/6 oraz nowszymi środowiskami uruchomieniowymi.

**P:** Czy mogę kompresować wiele plików jednocześnie?  
**O:** Absolutnie. Wywołaj `CreateEntry` dla każdego pliku przed zapisaniem archiwum.

**P:** Gdzie mogę znaleźć dodatkową dokumentację?  
**O:** Szczegółowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/zip/net/).

**P:** Jak uzyska:** Możesz ją zamówić [tutaj](https://purchase.aspose.com/temporary-license/).

**P:** Czy dostępna jest darmowa wersja próbna?  
**O:** Tak, pobierz wersję próbną [tutaj](https://releases.aspose.com/).

## Podsumowanie

Teraz wiesz, jak **add files to tar**, opakować je w strumień Bzip2 i utworzyć archiwum **TarBz2** przy użyciu Aspose.Zip dla .NET. Ta technika jest szybka, niezawodna i działa na wszystkich nowoczesnych platformach .NET. Śmiało eksperymentuj z większymiandardowymi nazwami wpisów lub zintegrować kod w własnych procesach tworzenia kopii zapasowych lub wdrożeń.

Jeśli napotkasz jakiekolwiek problemy, społeczność Aspose.Zip jest gotowa pomóc — wystarczy przejść na [forum wsparcia Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Ostatnia aktualizacja:** 2026-02-02  
**Testowano z:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}