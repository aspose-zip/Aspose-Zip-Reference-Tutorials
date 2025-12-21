---
date: 2025-12-21
description: Naučte se, jak v .NET vytvářet zip soubory chráněné heslem, šifrovat
  složky a měnit heslo zipu pomocí Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořte zip chráněný heslem pro .NET adresáře – tutoriál Aspose.Zip
url: /cs/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření zip souboru chráněného heslem pro .NET adresáře – Aspose.Zip Tutorial

V tomto průvodci **vytvoříte zip archiv chráněný heslem** pro celé adresáře pomocí knihovny Aspose.Zip pro .NET. Ať už potřebujete **zašifrovat složku**, zabezpečit záložní soubory, nebo jen omezit přístup k citlivým datům, tento krok‑za‑krokem tutoriál vám ukáže, jak to udělat čistým C# kódem.

## Rychlé odpovědi
- **Jaká knihovna se doporučuje?** Aspose.Zip pro .NET  
- **Mohu zašifrovat celou složku?** Ano – stačí nasměrovat API na složku, kterou chcete zkomprimovat.  
- **Je podporována změna hesla zipu?** Rozhodně, použijte `TraditionalEncryptionSettings`.  
- **Potřebuji licenci pro produkci?** Pro komerční použití je vyžadována platná licence Aspose.Zip.  
- **Funguje s .NET Core/5/6?** Ano, API je plně kompatibilní s moderními .NET runtimey.  

## Co znamená „vytvořit zip chráněný heslem“?
Vytvoření zip souboru chráněného heslem znamená kompresi souborů nebo adresářů do ZIP archivu s aplikovaným šifrováním, takže archiv lze otevřít pouze se správným heslem. Tím se chrání obsah před neoprávněným přístupem.

## Proč použít Aspose.Zip pro ochranu adresáře heslem v .NET?
Aspose.Zip nabízí přímé, výkonné API, které podporuje **c# zip password protection**, tradiční šifrování ZipCrypto i AES šifrování. Efektivně pracuje s velkými adresáři a snadno se integruje do jakéhokoli .NET projektu.

## Předpoklady
Než začnete, ujistěte se, že máte:

- Základní znalosti programování v C#.  
- Visual Studio (libovolná aktuální edice).  
- Knihovnu Aspose.Zip pro .NET – stáhněte ji **[zde](https://releases.aspose.com/zip/net/)**.  
- Složku na disku, kterou chcete chránit heslem.

## Import Namespaces
Přidejte požadované jmenné prostory do svého C# souboru, aby kompilátor věděl, kde najít třídy Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Krok 1: Nastavte cestu k adresáři zdrojů
Definujte cestu, která ukazuje na adresář, který chcete zkomprimovat a chránit.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Ochrana adresáře heslem
Použijte `TraditionalEncryptionSettings` k určení hesla a vytvoření šifrovaného archivu. Toto je jádro **c# zip password protection**.

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

## Krok 3: Vysvětlení kódu
- **Vytvoření výstupního souboru:** `File.Open(..., FileMode.Create)` otevře (nebo vytvoří) ZIP soubor, který bude obsahovat šifrovaná data.  
- **Výběr zdrojové složky:** `new DirectoryInfo(".\\CanterburyCorpus")` říká Aspose.Zip, který adresář má komprimovat.  
- **Aplikace hesla:** `new TraditionalEncryptionSettings("p@s$")` nastaví heslo, které archiv ochrání.  
- **Přidání položek a uložení:** `archive.CreateEntries(corpus)` přidá každý soubor ve složce a `archive.Save(zipFile)` zapíše šifrovaný ZIP na disk.

## Jak později změnit heslo zipu?
Pokud potřebujete **změnit heslo zipu**, jednoduše vytvořte archiv znovu s novou instancí `TraditionalEncryptionSettings`, která obsahuje nové heslo, a pak jej opět uložte.

## Časté problémy a tipy
- **Velké složky:** Aspose.Zip streamuje data, takže i při obrovských adresářích zůstává využití paměti nízké.  
- **Složitost hesla:** Použijte silné heslo (kombinace písmen, čísel, symbolů) pro zvýšení bezpečnosti.  
- **Chyby licence:** Ujistěte se, že jste aplikovali platný licenční soubor; jinak knihovna běží v režimu hodnocení s omezeními.

## Často kladené otázky

### Je Aspose.Zip pro .NET vhodný pro velké adresáře?
Ano, Aspose.Zip pro .NET je navržen tak, aby efektivně zpracovával velké adresáře a poskytoval optimální výkon.

### Mohu změnit heslo již chráněného adresáře?
Ano, heslo můžete upravit úpravou `TraditionalEncryptionSettings` v kódu.

### Jaké jsou licenční požadavky pro používání Aspose.Zip pro .NET?
Ano, pro používání Aspose.Zip pro .NET v produkčním prostředí je vyžadována platná licence. Licenci můžete získat **[zde](https://purchase.aspose.com/buy)**.

### Je k dispozici bezplatná zkušební verze Aspose.Zip pro .NET?
Ano, bezplatnou zkušební verzi získáte **[zde](https://releases.aspose.com/)**.

### Kde najdu další podporu pro Aspose.Zip pro .NET?
Navštivte **[Aspose.Zip fórum](https://forum.aspose.com/c/zip/37)** pro jakoukoli podporu nebo dotazy.

---

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** Aspose.Zip pro .NET (nejnovější verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}