---
date: 2025-12-20
description: Naučte se, jak vytvářet chráněné zip archivy s heslem v .NET pomocí Aspose.Zip.
  Tento krok‑za‑krokem průvodce ukazuje, jak komprimovat soubory s hesly, nastavit
  heslo pro zip položku a použít AES šifrování.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořte ZIP soubory chráněné heslem v .NET s Aspose.Zip
url: /cs/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření chráněných ZIP souborů heslem v .NET s Aspose.Zip

## Úvod

Pokud potřebujete **vytvořit chráněné zip** archivy v .NET aplikaci, Aspose.Zip to usnadňuje. Přiřazením jedinečného hesla ke každému záznamu můžete uchovat citlivé dokumenty v bezpečí a zároveň využívat výhod ZIP komprese. V tomto tutoriálu se naučíte, jak komprimovat soubory s individuálními hesly, vybrat různé šifrovací metody a nastavit heslo pro zip záznam – vše s přehledným, připraveným k nasazení kódem.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip pro .NET.  
- **Mohu přiřadit různé heslo pro každý soubor?** Ano, každý záznam může mít své vlastní heslo.  
- **Jaké šifrovací algoritmy jsou podporovány?** Tradiční ZipCrypto, AES‑128 a AES‑256.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Je to kompatibilní s .NET 6+?** Naprosto – API cílí na .NET Standard 2.0 a novější.

## Co znamená „vytvořit chráněný zip“?
Vytvoření chráněného zipu znamená přidání šifrování k jednomu nebo více záznamům uvnitř ZIP archivu, takže obsah nelze otevřít bez správného hesla. To je ideální pro přenos důvěrných souborů, ukládání záloh nebo dodržování zásad ochrany dat.

## Proč použít Aspose.Zip pro archivy chráněné heslem?
- **Detailní kontrola** – nastavení odlišného hesla pro každý soubor.  
- **Více šifrovacích možností** – od staršího ZipCrypto po silné AES‑128/256.  
- **Žádné externí závislosti** – čistá .NET knihovna, snadná integrace.  
- **Komplexní dokumentace** – obsahuje **aspose zip tutorial** pro pokročilejší scénáře.

## Požadavky

Než se ponoříte do tutoriálu, ujistěte se, že máte následující požadavky:

- Aspose.Zip pro .NET: Ujistěte se, že máte knihovnu Aspose.Zip nainstalovanou ve svém .NET projektu. Potřebnou dokumentaci najdete [zde](https://reference.aspose.com/zip/net/).
- Stažení: Pokud jste tak ještě neučinili, stáhněte knihovnu Aspose.Zip pro .NET z [tohoto odkazu](https://releases.aspose.com/zip/net/).
- Adresář s dokumenty: Připravte adresář obsahující soubory, které chcete komprimovat.

## Importování jmenných prostor

Ve svém .NET projektu se ujistěte, že importujete potřebné jmenné prostory:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Krok 1: Nastavte cestu ke zdrojovému adresáři

Definujte cestu ke zdrojovému adresáři, kde se nacházejí vaše vstupní soubory.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Komprimujte soubory s individuálními hesly

Nyní komprimujeme soubory s individuálními hesly. Použijeme tři ukázkové soubory (`alice29.txt`, `asyoulik.txt` a `fields.c`) s odlišnými hesly pro každý. Toto ukazuje, jak **komprimovat soubory s hesly** a také jak **nastavit heslo pro zip záznam** pomocí různých šifrovacích schémat, včetně **zip archivu s aes**.

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

### Jak to funguje
- **TraditionalEncryptionSettings** používá starší algoritmus ZipCrypto (kompatibilní s většinou ZIP nástrojů).
- **AesEcryptionSettings** vám umožní vybrat AES‑128 nebo AES‑256 pro vyšší zabezpečení.
- Každé volání `CreateEntry` přijímá objekt `ArchiveEntrySettings`, kde specifikujeme jak kompresní metodu, tak šifrovací nastavení, čímž efektivně **chráníme heslem zip archiv** položky.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|---------|-------|--------|
| “Neplatné heslo” při otevírání ZIP | Nesoulad mezi heslem použitém v kódu a heslem zadaným v extraktoru | Ověřte přesný řetězec předaný do `TraditionalEncryptionSettings` nebo `AesEcryptionSettings`. |
| Starší nástroje pro extrakci nemohou otevřít AES‑šifrované položky | Ne všechny ZIP utility podporují AES šifrování | Použijte tradiční metodu ZipCrypto pro maximální kompatibilitu, nebo uživatelům doporučte moderní nástroj (např. 7‑Zip). |
| Velké soubory způsobují `OutOfMemoryException` | Načítání obrovských souborů do paměti před kompresí | Streamujte soubor přímo pomocí `FileStream` bez načítání celého souboru do objektu `FileInfo`. |

## Často kladené otázky (FAQ)

### Mohu pro každý soubor použít různé šifrovací metody?
Ano, Aspose.Zip pro .NET vám umožňuje během komprese použít různé šifrovací metody pro každý soubor.

### Je k dispozici zkušební verze?
Ano, můžete získat bezplatnou zkušební verzi Aspose.Zip pro .NET [zde](https://releases.aspose.com/).

### Jak mohu získat podporu, pokud narazím na problémy?
Navštivte [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37) pro pomoc od komunity a podpory Aspose.

### Kde najdu podrobnou dokumentaci k Aspose.Zip pro .NET?
Dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/).

### Mohu zakoupit dočasnou licenci pro testovací účely?
Ano, můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

## Další rychlé FAQ

**Q: Podporuje knihovna .NET Core a .NET 5/6?**  
A: Ano, Aspose.Zip cílí na .NET Standard, což zajišťuje kompatibilitu s .NET Framework, .NET Core a .NET 5/6.

**Q: Mohu přidat komentář ke každému ZIP záznamu?**  
A: Přestože se Aspose.Zip zaměřuje na kompresi a šifrování, můžete uložit metadata v samostatném manifest souboru uvnitř archivu.

**Q: Je možné zašifrovat celý archiv jedním heslem?**  
A: Můžete nastavit heslo pro každý záznam zvlášť (jak je ukázáno) nebo použít stejné heslo pro všechny záznamy pro jednodušší přístup „zip archiv s aes“.

## Závěr

Nyní ovládáte, jak **vytvořit chráněné zip** soubory v .NET pomocí Aspose.Zip. Přiřazením individuálních hesel a výběrem vhodné šifrovací metody můžete udržet svá data v bezpečí, aniž byste ztratili výhody ZIP komprese. Prozkoumejte další funkce Aspose.Zip, jako je streamování velkých souborů, přidávání vlastních metadat a integrace s cloudovým úložištěm pro ještě výkonnější scénáře.

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Zip pro .NET 23.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}