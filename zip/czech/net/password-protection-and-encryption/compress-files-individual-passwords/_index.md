---
date: 2026-05-15
description: Zjistěte, jak vytvořit zip soubory chráněné heslem a komprimovat soubory
  s hesly pomocí Aspose.Zip pro .NET během několika jednoduchých kroků.
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: Komprimujte soubory s individuálními hesly
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořte ZIP chráněný heslem v .NET pomocí Aspose.Zip
url: /cs/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření ZIP souboru chráněného heslem v .NET s Aspose.Zip

## Úvod

V tomto tutoriálu se naučíte, jak **vytvořit ZIP soubory chráněné heslem** v .NET aplikaci pomocí Aspose.Zip. Bezpečná komprese je nezbytná, když potřebujete přenášet důvěrná data nebo ukládat citlivé dokumenty, aniž byste je vystavili neoprávněnému přístupu.

**Aspose.Zip** je .NET knihovna, která umožňuje programově vytvářet, číst a šifrovat ZIP archivy. Podporuje šifrování AES‑256 a umožňuje přiřadit jedinečné heslo každému záznamu v archivu.

## Rychlé odpovědi
- **Co dělá Aspose.Zip?** Vytváří a manipuluje ZIP archivy, včetně ochrany heslem na úrovni souboru.  
- **Kolik hesel mohu přiřadit?** Jedno jedinečné heslo na soubor; neomezený počet záznamů.  
- **Jaký šifrovací algoritmus se používá?** AES‑256, poskytující 256‑bitové zabezpečení.  
- **Potřebuji licenci pro testování?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Požadavky

Před tím, než se pustíte do tutoriálu, ujistěte se, že máte následující požadavky:

- Aspose.Zip pro .NET: Ujistěte se, že máte knihovnu Aspose.Zip nainstalovanou ve vašem .NET projektu. Potřebnou dokumentaci najdete [zde](https://reference.aspose.com/zip/net/).
- Stažení: Pokud jste ještě nestáhli, stáhněte si knihovnu Aspose.Zip pro .NET z [tohoto odkazu](https://releases.aspose.com/zip/net/).
- Adresář s dokumenty: Připravte adresář obsahující soubory, které chcete komprimovat.

## Importování jmenných prostorů

Ve vašem .NET projektu se ujistěte, že importujete potřebné jmenné prostory:

`ZipFile` je hlavní třída Aspose.Zip pro vytváření ZIP archivů a přiřazování individuálních hesel ke každému záznamu.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Jak vytvořit ZIP soubory chráněné heslem v .NET?

Načtěte cílovou složku, vytvořte objekt `ZipFile`, přidejte každý soubor s vlastním heslem a nakonec zavolejte `Save` pro zápis archivu. Tento celý proces vyžaduje jen několik řádků kódu a zajišťuje, že každý záznam je šifrován heslem, které zadáte.

### Krok 1: Nastavte cestu ke zdrojovému adresáři

Definujte cestu ke zdrojovému adresáři, kde se nacházejí vaše soubory.

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Komprimujte soubory s individuálními hesly

Nyní komprimujeme soubory s individuálními hesly. Použijeme tři ukázkové soubory (`alice29.txt`, `asyoulik.txt` a `fields.c`) s odlišnými hesly pro každý.

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

## Proč používat ochranu heslem pro ZIP archivy?

Aspose.Zip podporuje **více než 30 kompresních algoritmů** a může šifrovat archivy pomocí AES‑256, poskytující až **256‑bitové zabezpečení**. Dokáže zpracovávat archivy o velikosti stovek megabajtů, aniž by načítal celý soubor do paměti, což je ideální pro vysoce výkonné serverové scénáře. Navíc ochrana heslem pomáhá splňovat regulatorní požadavky jako GDPR a HIPAA tím, že zajišťuje, že citlivá data jsou šifrována jak v klidu, tak během přenosu.

## Závěr

Gratuluji! Úspěšně jste se naučili, jak **vytvořit ZIP soubory chráněné heslem** a **komprimovat soubory s hesly** pomocí Aspose.Zip pro .NET. Tato funkce přidává další vrstvu zabezpečení vašim komprimovaným souborům, zajišťuje důvěrnost a soulad s politikami ochrany dat.

## Často kladené otázky

**Q: Mohu pro každý soubor použít různé šifrovací metody?**  
A: Ano, Aspose.Zip vám umožňuje vybrat šifrovací algoritmus (např. AES‑256) pro každý záznam při jeho přidání do archivu.

**Q: Je k dispozici zkušební verze?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Zip pro .NET [zde](https://releases.aspose.com/).

**Q: Jak mohu získat podporu, pokud narazím na problémy?**  
A: Navštivte [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pro pomoc od komunity a podpory Aspose.

**Q: Kde najdu podrobnou dokumentaci k Aspose.Zip pro .NET?**  
A: Dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/).

**Q: Mohu zakoupit dočasnou licenci pro testovací účely?**  
A: Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-05-15  
**Testováno s:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvoření ZIP souboru chráněného heslem s Aspose.Zip pro .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Ochrana ZIP souborů heslem pomocí AES šifrování s Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Komprese více souborů s šifrováním v Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}