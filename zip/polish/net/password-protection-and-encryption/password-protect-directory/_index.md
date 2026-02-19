---
date: 2025-12-21
description: Dowiedz się, jak tworzyć pliki zip chronione hasłem w .NET, szyfrować
  foldery i zmieniać hasło zip przy użyciu Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Utwórz chroniony hasłem plik zip dla katalogów .NET – Poradnik Aspose.Zip
url: /pl/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie archiwum zip chronionego hasłem dla katalogów .NET – Poradnik Aspose.Zip

W tym przewodniku **utworzysz archiwa zip chronione hasłem** dla całych katalogów przy użyciu biblioteki Aspose.Zip dla .NET. Niezależnie od tego, czy potrzebujesz **zaszyfrować folder**, zabezpieczyć pliki kopii zapasowych, czy po prostu ograniczyć dostęp do wrażliwych danych, ten krok‑po‑kroku tutorial pokaże Ci dokładnie, jak to zrobić przy użyciu czystego kodu C#.

## Szybkie odpowiedzi
- **Jakiej biblioteki używać?** Aspose.Zip dla .NET  
- **Czy mogę zaszyfrować cały folder?** Tak – wystarczy wskazać API folder, który ma zostać spakowany.  
- **Czy zmiana hasła zip jest obsługiwana?** Oczywiście, użyj `TraditionalEncryptionSettings`.  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest ważna licencja Aspose.Zip do użytku komercyjnego.  
- **Działa z .NET Core/5/6?** Tak, API jest w pełni kompatybilne z nowoczesnymi środowiskami .NET.  

## Co to jest „create password protected zip”?
Tworzenie archiwum zip chronionego hasłem oznacza kompresję plików lub katalogów do archiwum ZIP przy jednoczesnym zastosowaniu szyfrowania, tak aby archiwum mogło być otwarte wyłącznie po podaniu prawidłowego hasła. Chroni to zawartość przed nieautoryzowanym dostępem.

## Dlaczego warto używać Aspose.Zip do ochrony katalogów .NET hasłem?
Aspose.Zip oferuje prostą, wysokowydajną API, która obsługuje **c# zip password protection**, tradycyjne szyfrowanie ZipCrypto oraz szyfrowanie AES. Efektywnie radzi sobie z dużymi katalogami i integruje się bezproblemowo z każdym projektem .NET.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Podstawową znajomość programowania w C#.  
- Visual Studio (dowolna aktualna edycja).  
- Bibliotekę Aspose.Zip dla .NET – pobierz ją **[tutaj](https://releases.aspose.com/zip/net/)**.  
- Katalog na dysku, który chcesz zabezpieczyć hasłem.

## Importowanie przestrzeni nazw
Dodaj wymagane przestrzenie nazw do swojego pliku C#, aby kompilator wiedział, gdzie znaleźć klasy Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Krok 1: Ustaw ścieżkę do katalogu zasobów
Zdefiniuj ścieżkę, która wskazuje na katalog, który zamierzasz spakować i zabezpieczyć.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Zabezpiecz katalog hasłem
Użyj `TraditionalEncryptionSettings`, aby określić hasło i utworzyć zaszyfrowane archiwum. To jest sedno **c# zip password protection**.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Krok 3: Wyjaśnienie kodu
- **Tworzenie pliku wyjściowego:** `File.Open(..., FileMode.Create)` otwiera (lub tworzy) plik ZIP, w którym zostaną zapisane zaszyfrowane dane.  
- **Wybór folderu źródłowego:** `new DirectoryInfo(".\\CanterburyCorpus")` informuje Aspose.Zip, który katalog ma zostać skompresowany.  
- **Ustawienie hasła:** `new TraditionalEncryptionSettings("p@s$")` definiuje hasło chroniące archiwum.  
- **Dodawanie wpisów i zapisywanie:** `archive.CreateEntries(corpus)` dodaje każdy plik z folderu, a `archive.Save(zipFile)` zapisuje zaszyfrowany ZIP na dysku.

## Jak zmienić hasło zip później?
Jeśli potrzebujesz **change zip password**, po prostu odtwórz archiwum z nową instancją `TraditionalEncryptionSettings` zawierającą nowe hasło, a następnie ponownie je zapisz.

## Typowe problemy i wskazówki
- **Duże foldery:** Aspose.Zip strumieniuje dane, więc zużycie pamięci pozostaje niskie nawet przy bardzo dużych katalogach.  
- **Złożoność hasła:** Używaj silnego hasła (mieszanka liter, cyfr, znaków specjalnych), aby zwiększyć bezpieczeństwo.  
- **Błędy licencyjne:** Upewnij się, że zastosowano prawidłowy plik licencji; w przeciwnym razie biblioteka działa w trybie ewaluacyjnym z ograniczeniami.

## Najczęściej zadawane pytania

### Czy Aspose.Zip dla .NET nadaje się do dużych katalogów?
Tak, Aspose.Zip dla .NET został zaprojektowany tak, aby efektywnie obsługiwać duże katalogi, zapewniając optymalną wydajność.

### Czy mogę zmienić hasło już zabezpieczonego katalogu?
Tak, możesz zmodyfikować hasło, dostosowując `TraditionalEncryptionSettings` w kodzie odpowiednio.

### Czy istnieją wymagania licencyjne przy używaniu Aspose.Zip dla .NET?
Tak, wymagana jest ważna licencja do używania Aspose.Zip dla .NET w środowisku produkcyjnym. Licencję możesz uzyskać **[tutaj](https://purchase.aspose.com/buy)**.

### Czy dostępna jest darmowa wersja próbna Aspose.Zip dla .NET?
Tak, darmową wersję próbną znajdziesz **[tutaj](https://releases.aspose.com/)**.

### Gdzie mogę uzyskać dodatkowe wsparcie dla Aspose.Zip dla .NET?
Możesz odwiedzić **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**, aby uzyskać pomoc lub zadać pytania.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowano z:** Aspose.Zip dla .NET (najnowsze wydanie)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}