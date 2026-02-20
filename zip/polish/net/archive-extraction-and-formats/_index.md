---
date: 2026-02-20
description: Naucz się kompresować pliki tarbz2, tworzyć archiwa targz oraz wyodrębniać
  archiwa .NET, w tym chronione hasłem pliki zip, przy użyciu Aspose.Zip dla .NET.
  Zwiększ efektywność przechowywania i bezpieczeństwo.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak kompresować pliki TarBz2 przy użyciu Aspose.Zip dla .NET
url: /pl/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak kompresować pliki TarBz2 przy użyciu Aspose.Zip dla .NET

## Wprowadzenie

W tym przewodniku dowiesz się **jak kompresować pliki tarbz2** przy użyciu Aspose.Zip dla .NET, a także jak tworzyć archiwa TarGz oraz wykonywać rozpakowywanie archiwów .net chronionych hasłem. Efektywna obsługa plików jest fundamentem nowoczesnego rozwoju .NET, a opanowanie tych formatów pozwala obniżyć koszty przechowywania, przyspieszyć transfer danych i zabezpieczyć wrażliwe informacje. Niezależnie od tego, czy tworzysz usługę backupu, klienta przechowywania w chmurze, czy pipeline przetwarzania danych, techniki opisane tutaj uczynią zarządzanie plikami płynniejszym i bardziej niezawodnym.

## Szybkie odpowiedzi
- **What is TarBz2?** Skompresowane archiwum łączące pakowanie TAR z kompresją BZIP2, zapewniające wysokie współczynniki kompresji.  
- **Why choose Aspose.Zip for .NET?** Oferuje jednolite, płynne API do tworzenia i rozpakowywania wielu formatów archiwów bez zależności zewnętrznych.  
- **Can I create a TarGz archive?** Tak – Aspose.Zip obsługuje TarGz, TarLz, TarXz, TarZ i inne.  
- **How do I extract a password‑protected zip archive?** Użyj właściwości `Password` obiektu `ArchiveEntry` podczas rozpakowywania.  
- **Do I need a license for production use?** Wymagana jest licencja komercyjna do użytku produkcyjnego; dostępna jest bezpłatna wersja próbna do oceny.

## Jak kompresować pliki TarBz2
Kompresowanie plików do TarBz2 oznacza najpierw zgrupowanie wielu plików i katalogów w jedną **TAR** kontener, a następnie zastosowanie kompresji **BZIP2**. Wynikiem jest pojedynczy plik `.tar.bz2`, który jest łatwy do transportu i wysoko skompresowany.

## Dlaczego używać Aspose.Zip dla .NET do obsługi tych formatów?
- **Unified API** – Jedna biblioteka, wiele formatów (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Działa natywnie na Windows, Linux i macOS.  
- **Password support** – Bezpieczne zabezpieczanie i rozpakowywanie archiwów przy użyciu haseł dla poszczególnych wpisów.  
- **Performance‑focused** – Przetwarzanie oparte na strumieniach minimalizuje zużycie pamięci.

## Wymagania wstępne
- .NET 6.0 lub nowszy (lub .NET Core 3.1+ / .NET Framework 4.5+).  
- Zainstalowany pakiet NuGet Aspose.Zip dla .NET (`Install-Package Aspose.Zip`).  
- Podstawowa znajomość C# i operacji wejścia/wyjścia plików.

## Przewodnik krok po kroku

### Krok 1: Wybierz potrzebny format archiwum
Zdecyduj, czy **TarBz2**, **TarGz**, **TarLz**, **TarXz** lub **TarZ** najlepiej spełnia Twoje wymagania dotyczące współczynnika kompresji i kompatybilności.  
- **TarBz2** – Najlepsza kompresja, wolniejsze przetwarzanie.  
- **TarGz** – Dobry kompromis między szybkością a rozmiarem (obejmuje drugorzędne słowo kluczowe *how to create targz*).  
- **TarZ** – Format starszy, przydatny dla kompatybilności ze starszymi narzędziami Unix.

### Krok 2: Utwórz nową instancję `Archive`
Zainicjalizuj klasę `Archive` i wskaż ścieżkę pliku wyjściowego. Ten obiekt będzie zarządzał procesem pakowania i kompresji.

### Krok 3: Dodaj pliki i foldery
Użyj metod `AddAll` lub `AddFile`, aby dodać pliki, które chcesz skompresować. Możesz zachować strukturę katalogów, dodając folder bazowy.

### Krok 4: Ustaw żądany typ kompresji
Określ algorytm kompresji (`CompressionType.BZip2`, `CompressionType.GZip` itd.) przy zapisywaniu archiwum. To tutaj faktycznie **kompresujesz pliki do TarBz2** lub innego formatu.

### Krok 5: Zapisz archiwum
Wywołaj `Save` z odpowiednim enumem formatu (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz` itd.). Biblioteka zapisuje kontener TAR i stosuje wybraną kompresję w jednym przebiegu.

### Krok 6: Rozpakowywanie archiwów z hasłami
Jeśli musisz **rozpakować wpisy archiwum przy użyciu różnych haseł** (drugorzędne słowo kluczowe *password protected zip extraction*), otwórz archiwum, znajdź każdy wpis, przypisz mu hasło i następnie rozpakuj.

### Krok 7: Zweryfikuj wynik
Po rozpakowaniu porównaj rozmiary plików i sumy kontrolne, aby upewnić się, że archiwum zostało poprawnie utworzone i wypakowane.

## Typowe przypadki użycia
- **Backup utilities** – Przechowuj codzienne kopie zapasowe jako `.tar.bz2`, aby zminimalizować koszty przechowywania.  
- **Cross‑platform data exchange** – Formaty oparte na TAR są powszechnie rozumiane na Linux, macOS i Windows.  
- **Secure distribution** – Zabezpiecz poszczególne wpisy hasłami w środowiskach wymagających zgodności.

## Rozwiązywanie problemów i wskazówki
- **Large archives** – Używaj API strumieniowych (`Archive.CreateEntryFromFile`), aby uniknąć ładowania całych plików do pamięci.  
- **Password mismatches** – Upewnij się, że hasło ustawione dla każdego `ArchiveEntry` jest zgodne z tym używanym podczas rozpakowywania; w przeciwnym razie napotkasz `InvalidPasswordException`.  
- **Unsupported compression level** – BZIP2 nie obsługuje niestandardowych poziomów kompresji; jeśli potrzebujesz większej kontroli, rozważ TarLz lub TarXz.

## Najczęściej zadawane pytania

**Q: Jak utworzyć archiwum TarGz?**  
A: Ustaw typ kompresji na `CompressionType.GZip` i format na `ArchiveFormat.TarGz` przy wywoływaniu `Save`.

**Q: Czy mogę rozpakować archiwum chronione hasłem bez znajomości hasła?**  
A: Nie. Każdy wpis musi mieć podane prawidłowe hasło; w przeciwnym razie rozpakowywanie się nie powiedzie.

**Q: Czy Aspose.Zip obsługuje rozpakowywanie archiwów z różnymi hasłami dla poszczególnych wpisów?**  
A: Tak. Możesz przypisać hasło do każdego `ArchiveEntry` indywidualnie przed rozpakowaniem.

**Q: Który format zapewnia najlepszą kompresję?**  
A: TarBz2 zazwyczaj zapewnia najwyższy współczynnik kompresji, następnie TarLz i TarXz. TarGz oferuje dobry kompromis między szybkością a rozmiarem.

**Q: Czy istnieje limit liczby plików, które mogę dodać do archiwum TAR?**  
A: Praktycznie nie, ale bardzo duże archiwa mogą skorzystać z podziału na wiele części w celu łatwiejszej obsługi.

## Samouczki dotyczące rozpakowywania archiwów i formatów
### [Kompresowanie plików do TarBz2 przy użyciu Aspose.Zip dla .NET](./compress-to-tar-bz2/)
Dowiedz się, jak kompresować pliki do formatu TarBz2 w .NET przy użyciu Aspose.Zip. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby efektywnie kompresować pliki.
### [Kompresowanie do TarGz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-gz/)
Poznaj efektywną kompresję plików w .NET z Aspose.Zip. Kompresuj do TarGz bez wysiłku.
### [Kompresowanie do TarLz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-lz/)
Łatwo kompresuj pliki w .NET z Aspose.Zip. Naucz się tworzyć archiwa TarLz krok po kroku.
### [Kompresowanie do TarXz przy użyciu Aspose.Zip dla .NET](./compress-to-tar-xz/)
Dowiedz się, jak kompresować pliki do formatu TarXz w .NET przy użyciu Aspose.Zip. Skorzystaj z naszego przewodnika krok po kroku, aby efektywnie przechowywać i przesyłać pliki.
### [Kompresowanie do TarZ przy użyciu Aspose.Zip dla .NET](./compress-to-tar-z/)
Poznaj krok po kroku kompresję do TarZ przy użyciu Aspose.Zip dla .NET. Efektywna obsługa plików w Twoich projektach .NET.
### [Rozpakowywanie wpisów archiwum z różnymi hasłami w Aspose.Zip dla .NET](./extract-archive-different-passwords/)
Dowiedz się, jak rozpakowywać wpisy archiwum z różnymi hasłami w Aspose.Zip dla .NET. Zwiększ bezpieczeństwo i elastyczność w swoich aplikacjach.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-02-20  
**Testowano z:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose