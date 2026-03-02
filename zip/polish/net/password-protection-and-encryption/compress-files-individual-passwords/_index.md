---
date: 2026-03-02
description: Dowiedz się, jak utworzyć archiwum ZIP chronione hasłem i kompresować
  pliki z hasłami w .NET przy użyciu Aspose.Zip. Postępuj zgodnie z naszym przewodnikiem
  krok po kroku.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Utwórz chroniony hasłem archiwum ZIP w .NET przy użyciu Aspose.Zip
url: /pl/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz archiwum ZIP chronione hasłem w .NET przy użyciu Aspose.Zip

## Wprowadzenie

Kiedy musisz udostępnić wrażliwe dane, **archiwum zip chronione hasłem** jest jednym z najprostszych, a jednocześnie najskuteczniejszych sposobów zabezpieczenia informacji. W aplikacjach .NET Aspose.Zip ułatwia **kompresję plików z hasłami**, przydzielając każdemu plikowi własny klucz szyfrowania. W tym samouczku dowiesz się dokładnie, jak stworzyć takie archiwum, dlaczego jest to ważne i gdzie możesz je zastosować w rzeczywistych projektach.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Zip dla .NET zapewnia wbudowane wsparcie dla haseł per‑plik oraz wielu metod szyfrowania.  
- **Ile linii kodu?** Około 30 linii, wliczając konfigurację i zapisywanie archiwum.  
- **Czy każdy plik może mieć inne hasło?** Tak – możesz przypisać unikalne hasło do każdego wpisu.  
- **Jakie metody szyfrowania są dostępne?** Tradycyjny ZipCrypto, AES‑128 i AES‑256.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna do użytku produkcyjnego; dostępna jest darmowa wersja próbna.

## Czym jest archiwum zip chronione hasłem?
Archiwum zip chronione hasłem to skompresowany plik (ZIP), który wymaga podania hasła w celu wyodrębnienia jego zawartości. Hasło może chronić całe archiwum lub poszczególne wpisy, a nowoczesne algorytmy, takie jak AES‑128/256, zapewniają silne szyfrowanie.

## Dlaczego kompresować pliki z hasłami przy użyciu Aspose.Zip?
- **Granularne bezpieczeństwo** – przypisz odrębne hasło do każdego pliku, idealne w scenariuszach wielodzierżawczych.  
- **Wiele standardów szyfrowania** – wybierz pomiędzy starszym ZipCrypto a silnym AES.  
- **Brak zewnętrznych narzędzi** – wszystko jest obsługiwane programowo w Twojej bazie kodu .NET.  
- **Wydajność** – szybka kompresja przy użyciu Deflate przy zachowaniu małego rozmiaru archiwum.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- **Aspose.Zip dla .NET** – zainstaluj bibliotekę w swoim projekcie. Szczegółowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/zip/net/).  
- **Pobierz najnowszy pakiet**, jeśli jeszcze tego nie zrobiłeś, z [tego linku](https://releases.aspose.com/zip/net/).  
- Folder zawierający pliki, które chcesz skompresować.

## Importowanie przestrzeni nazw

Dodaj wymagane przestrzenie nazw na początku pliku C#:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Krok 1: Ustaw ścieżkę katalogu zasobów

Wskaż w kodzie folder, który zawiera pliki źródłowe:

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Kompresuj pliki z indywidualnymi hasłami

Teraz utworzymy **archiwum zip chronione hasłem**, w którym każdy plik używa własnego hasła i metody szyfrowania. Przykład wykorzystuje trzy pliki przykładowe (`alice29.txt`, `asyoulik.txt` i `fields.c`) z różnymi hasłami.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Jak to działa
- **CreateEntry** dodaje plik do archiwum.  
- Czwarty argument (`ArchiveEntrySettings`) pozwala określić zarówno kompresję (`DeflateCompressionSettings`), jak i szyfrowanie (`TraditionalEncryptionSettings` lub `AesEcryptionSettings`).  
- Przekazując inny ciąg hasła dla każdego wpisu, otrzymujesz **archiwum zip chronione hasłem**, w którym każdy plik można odblokować tylko przy użyciu własnego klucza.

## Typowe problemy i rozwiązywanie

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Rozpakowywanie nie powiodło się z komunikatem „Wrong password” | Niezgodność hasła lub nieprawidłowa metoda szyfrowania | Sprawdź dokładny ciąg hasła i upewnij się, że przy rozpakowywaniu użyto tej samej `EncryptionMethod`. |
| Rozmiar archiwum jest większy niż oczekiwano | Użycie AES‑256 na małych plikach tekstowych może zwiększyć narzut | Dla małych plików AES‑128 może być wystarczający i daje mniejsze archiwum. |
| Wyjątek w czasie wykonywania przy `archive.Save` | Brak uprawnień do zapisu w docelowym folderze | Upewnij się, że aplikacja ma dostęp do zapisu w `dataDir` lub użyj innej ścieżki wyjściowej. |

## Najczęściej zadawane pytania (FAQ)

### Czy mogę używać różnych metod szyfrowania dla każdego pliku?
Tak, Aspose.Zip dla .NET pozwala mieszać metody szyfrowania — tradycyjny ZipCrypto, AES‑128 i AES‑256 — na poziomie poszczególnych plików.

### Czy dostępna jest wersja próbna?
Tak, darmową wersję próbną Aspose.Zip dla .NET możesz uzyskać [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie w razie problemów?
Odwiedź [forum Aspose.Zip](https://forum.aspose.com/c/zip/37), aby uzyskać pomoc od społeczności i wsparcia Aspose.

### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Zip dla .NET?
Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/zip/net/).

### Czy mogę kupić tymczasową licencję do celów testowych?
Tak, tymczasową licencję możesz nabyć [tutaj](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-02  
**Testowano z:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

---