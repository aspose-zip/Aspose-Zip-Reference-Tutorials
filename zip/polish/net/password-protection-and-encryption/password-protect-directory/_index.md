---
title: Katalogi chronione hasłem w .NET za pomocą samouczka Aspose.Zip
linktitle: Katalog chroniony hasłem
second_title: Aspose.Zip .NET API do kompresji i archiwizacji plików
description: Dowiedz się, jak chronić katalogi hasłem w .NET przy użyciu Aspose.Zip. Zabezpiecz swoje pliki bez wysiłku, korzystając z tego samouczka krok po kroku.
weight: 10
url: /pl/net/password-protection-and-encryption/password-protect-directory/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Katalogi chronione hasłem w .NET za pomocą samouczka Aspose.Zip


## Wstęp

W świecie programowania .NET zarządzanie i zabezpieczanie katalogów jest kluczowym aspektem obsługi plików. Aspose.Zip dla .NET zapewnia solidne rozwiązanie do ochrony katalogów hasłem, zapewniając poufność i integralność wrażliwych danych. W tym samouczku przeprowadzimy Cię krok po kroku przez proces zabezpieczania katalogu hasłem przy użyciu Aspose.Zip dla .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Program Visual Studio zainstalowany na Twoim komputerze.
-  Biblioteka Aspose.Zip dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/zip/net/).
- Katalog zawierający pliki, które chcesz zabezpieczyć hasłem.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do projektu C#. Te przestrzenie nazw są kluczowe dla wykorzystania funkcjonalności zapewnianej przez Aspose.Zip dla .NET.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Krok 1: Ustaw ścieżkę do katalogu zasobów

Na początek określ ścieżkę do katalogu zawierającego pliki, które chcesz zabezpieczyć hasłem.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Zabezpiecz katalog hasłem

 Zagłębmy się teraz w kod, który zabezpiecza katalog hasłem. Używamy`TraditionalEncryptionSettings` class, aby ustawić hasło i zastosować je do określonego katalogu.

```csharp
//ExStart: Katalog PasswordProtect
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //Rozwiń: Katalog ochrony hasłem
    }
}
```

## Krok 3: Wyjaśnienie Kodeksu

Rozłóżmy kod, aby zrozumieć każdy krok:

-  Ustawianie pliku wyjściowego:`FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create)` tworzy nowy plik ZIP dla zaszyfrowanych danych wyjściowych.

-  Definiowanie katalogu:`DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus")` określa katalog, który ma być chroniony hasłem.

-  Tworzenie i zapisywanie wpisów:`archive.CreateEntries(corpus)` tworzy wpisy dla plików w określonym katalogu i`archive.Save(zipFile)`zapisuje archiwum chronione hasłem.

## Wniosek

W tym samouczku przeszliśmy przez proces zabezpieczania katalogu hasłem przy użyciu Aspose.Zip dla .NET. Wykonując poniższe kroki, możesz zapewnić bezpieczeństwo swoich wrażliwych plików w sposób przyjazny dla użytkownika i skuteczny.

---

## Często Zadawane Pytania

### Czy Aspose.Zip dla .NET nadaje się do dużych katalogów?
Tak, Aspose.Zip dla .NET został zaprojektowany do wydajnej obsługi dużych katalogów, zapewniając optymalną wydajność.

### Czy mogę zmienić hasło do już chronionego katalogu?
 Tak, możesz zmodyfikować hasło, dostosowując`TraditionalEncryptionSettings` odpowiednio w kodzie.

### Czy są jakieś wymagania licencyjne dotyczące korzystania z Aspose.Zip dla .NET?
 Tak, do używania Aspose.Zip dla .NET w środowisku produkcyjnym wymagana jest ważna licencja. Można uzyskać licencję[Tutaj](https://purchase.aspose.com/buy).

### Czy dostępna jest bezpłatna wersja próbna Aspose.Zip dla .NET?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Zip dla .NET?
 Możesz odwiedzić[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) w celu uzyskania wsparcia lub zapytań.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
