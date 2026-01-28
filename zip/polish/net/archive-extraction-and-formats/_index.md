---
date: 2026-01-28
description: Dowiedz się, jak wyodrębnić archiwum z hasłem, kompresować pliki do formatu
  TarBz2, tworzyć archiwa TarGz przy użyciu Aspose.Zip dla .NET. Zwiększ efektywność
  przechowywania i bezpieczeństwo.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Rozpakuj archiwum z hasłem i skompresuj do TarBz2 (.NET)
url: /pl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wyodrębnianie archiwum z hasłem i kompresja do TarBz2 (.NET)

W tym przewodniku dowiesz się **jak wyodrębnić archiwum z hasłem** oraz opanujesz **kompresję plików do TarBz2** przy użyciu Aspose.Zip dla .NET. Niezależnie od tego, czy tworzysz usługę backupu, klienta chmury, czy potok przetwarzania danych, te techniki pozwalają zmniejszyć rozmiar przechowywanych danych, przyspieszyć transfery i chronić wrażliwe informacje.

## Szybkie odpowiedzi
- **Co to jest TarBz2?** Skompresowane archiwum, które łączy pakowanie TAR z kompresją BZIP2, zapewniając wysokie współczynniki kompresji.  
- **Dlaczego wybrać Aspose.Zip dla .NET?** Dostarcza jednego, płynnego API dla wielu formatów archiwów bez zależności natywnych.  
- **Czy mogę utworzyć archiwum TarGz?** Tak – Aspose.Zip obsługuje TarGz, TarLz, TarXz, TarZ i inne.  
- **Jak wyodrębnić archiwum chronione hasłem?** Ustaw właściwość `Password` dla każdego `ArchiveEntry` przed wyodrębnieniem.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Licencja komercyjna jest wymagana w środowisku produkcyjnym; dostępna jest bezpłatna wersja próbna do oceny.

## Jak wyodrębnić archiwum z hasłem przy użyciu Aspose.Zip dla .NET
Wyodrębnianie archiwum, które jest **chronione hasłem** (password protect zip archive), jest proste. Otwierasz archiwum, znajdujesz potrzebny wpis, przypisujesz mu hasło, a następnie wywołujesz `Extract`. To podejście działa dla TarBz2, TarGz i innych obsługiwanych formatów.

## Co tak naprawdę oznacza „kompresja plików do TarBz2”?
Kompresja plików do TarBz2 oznacza najpierw zgrupowanie wielu plików i katalogów w pojedynczy kontener **TAR**, a następnie zastosowanie kompresji **BZIP2**. Wynikiem jest plik `.tar.bz2`, który jest zarówno łatwy do przenoszenia, jak i wysoko skompresowany.

## Dlaczego używać Aspose.Zip dla .NET do obsługi tych formatów?
- **Unified API** – Jedna biblioteka, wiele formatów (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Działa od razu na Windows, Linux i macOS.  
- **Password support** – Bezpiecznie chroni i wyodrębnia archiwa przy użyciu haseł per‑entry.  
- **Performance‑focused** – Przetwarzanie oparte na strumieniach minimalizuje zużycie pamięci.

## Wymagania wstępne
- .NET 6.0 lub nowszy (lub .NET Core 3.1+ / .NET Framework 4.5+).  
- Zainstalowany pakiet NuGet Aspose.Zip dla .NET (`Install-Package Aspose.Zip`).  
- Podstawowa znajomość C# oraz operacji na plikach I/O.

## Przewodnik krok po kroku

### Krok 1: Wybierz potrzebny format archiwum
Zdecyduj, czy **TarBz2**, **TarGz**, **TarLz**, **TarXz** lub **TarZ** najlepiej odpowiada Twoim wymaganiom dotyczącym współczynnika kompresji i kompatybilności.  
- **TarBz2** – Najlepsza kompresja, wolniejsze przetwarzanie.  
- **TarGz** – Dobry kompromis między szybkością a rozmiarem (obejmuje drugorzędne słowo kluczowe *compress files to targz*).  
- **TarZ** – Starszy format dla starszych narzędzi Unixowych.

### Krok 2: Utwórz nową instancję `Archive`
Zainicjalizuj klasę `Archive` i wskaż ścieżkę pliku wyjściowego. Ten obiekt będzie zarządzał procesem pakowania i kompresji.

### Krok 3: Dodaj pliki i foldery
Użyj metod `AddAll` lub `AddFile`, aby dodać pliki, które chcesz skompresować. Zachowaj strukturę katalogów, dodając folder bazowy.

### Krok 4: Ustaw żądany typ kompresji
Określ algorytm kompresji (`CompressionType.BZip2`, `CompressionType.GZip` itp.) przy zapisywaniu archiwum. To jest miejsce, w którym faktycznie **kompresujesz pliki do tarbz2** lub innego formatu.

### Krok 5: Zapisz archiwum
Wywołaj `Save` z odpowiednim enumem formatu (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz` itp.). Biblioteka zapisuje kontener TAR i stosuje wybraną kompresję w jednym przebiegu.

### Krok 6: Wyodrębniaj archiwa z hasłami
Jeśli musisz **wyodrębnić wpisy archiwum z różnymi hasłami** (drugorzędne słowo kluczowe *how to extract password protected archive*), otwórz archiwum, znajdź każdy wpis, przypisz mu hasło, a następnie wyodrębnij.

### Krok 7: Zweryfikuj wynik
Po wyodrębnieniu porównaj rozmiary plików i sumy kontrolne, aby upewnić się, że archiwum zostało poprawnie utworzone i rozpakowane.

## Typowe przypadki użycia
- **Narzędzia backupowe** – Przechowuj codzienne kopie zapasowe jako `.tar.bz2`, aby zminimalizować koszty przechowywania.  
- **Wymiana danych między platformami** – Formaty oparte na TAR są powszechnie rozumiane na Linux, macOS i Windows.  
- **Bezpieczna dystrybucja** – Chron indywidualne wpisy hasłami w środowiskach wymagających zgodności.

## Rozwiązywanie problemów i wskazówki
- **Duże archiwa** – Używaj API strumieniowych (`Archive.CreateEntryFromFile`), aby uniknąć ładowania całych plików do pamięci.  
- **Niezgodność haseł** – Upewnij się, że hasło ustawione dla każdego `ArchiveEntry` jest takie samo, jak użyte podczas wyodrębniania; w przeciwnym razie napotkasz `InvalidPasswordException`.  
- **Nieobsługiwany poziom kompresji** – BZIP2 nie obsługuje niestandardowych poziomów kompresji; jeśli potrzebna jest większa kontrola, rozważ TarLz lub TarXz.  
- **Wskazówka wydajnościowa** – Podczas tworzenia **create tarbz2 archive**, włącz buforowanie na podstawowym strumieniu, aby zwiększyć prędkość zapisu.

## Najczęściej zadawane pytania

**P: Jak utworzyć archiwum TarGz?**  
O: Ustaw typ kompresji na `CompressionType.GZip` oraz format na `ArchiveFormat.TarGz` przy wywoływaniu `Save`.

**P: Czy mogę wyodrębnić archiwum chronione hasłem bez znajomości hasła?**  
O: Nie. Każdy wpis musi otrzymać właściwe hasło; w przeciwnym razie wyodrębnianie się nie powiedzie.

**P: Czy Aspose.Zip obsługuje wyodrębnianie archiwów z różnymi hasłami dla poszczególnych wpisów?**  
O: Tak. Możesz przypisać hasło do każdego `ArchiveEntry` indywidualnie przed wyodrębnieniem.

**P: Który format zapewnia najlepszą kompresję?**  
O: TarBz2 zazwyczaj daje najwyższy współczynnik kompresji, następnie TarLz i TarXz. TarGz oferuje dobry kompromis między szybkością a rozmiarem.

**P: Czy istnieje limit liczby plików, które mogę dodać do archiwum TAR?**  
O: Praktycznie nie, ale bardzo duże archiwa mogą skorzystać z podziału na wiele części w celu łatwiejszej obsługi.

## Samouczki wyodrębniania archiwów i formatów

### [Kompresja plików do TarBz2 przy użyciu Aspose.Zip dla .NET](./compress-to-tar-bz2/)
Dowiedz się, jak kompresować pliki do formatu TarBz2 w .NET przy użyciu Aspose.Zip. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać efektywną kompresję plików.

### [Kompresja do TarGz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-gz/)
Poznaj efektywną kompresję plików w .NET z Aspose.Zip. Kompresuj do TarGz bez wysiłku.

### [Kompresja do TarLz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-lz/)
Bezproblemowo kompresuj pliki w .NET z Aspose.Zip. Naucz się tworzyć archiwa TarLz krok po kroku.

### [Kompresja do TarXz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-xz/)
Dowiedz się, jak kompresować pliki do formatu TarXz w .NET przy użyciu Aspose.Zip. Skorzystaj z naszego przewodnika krok po kroku, aby uzyskać efektywne przechowywanie i transmisję plików.

### [Kompresja do TarZ przy użyciu Aspose.Zip dla .NET](./compress-to-tar-z/)
Poznaj szczegółowy proces kompresji do TarZ przy użyciu Aspose.Zip dla .NET. Efektywna obsługa plików dla Twoich projektów .NET.

### [Wyodrębnianie wpisów archiwum z różnymi hasłami w Aspose.Zip dla .NET](./extract-archive-different-passwords/)
Dowiedz się, jak wyodrębniać wpisy archiwum z różnymi hasłami w Aspose.Zip dla .NET. Zwiększ bezpieczeństwo i elastyczność w swoich aplikacjach.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-28  
**Testowano z:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose