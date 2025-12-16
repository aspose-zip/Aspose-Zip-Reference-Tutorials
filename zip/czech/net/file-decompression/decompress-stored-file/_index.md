---
date: 2025-12-16
description: Naučte se, jak vytvořit zip bez komprese a rozbalit více zip souborů
  pomocí Aspose.Zip pro .NET. Tento průvodce popisuje, jak otevřít zip, číst položku
  zip a kroky pro rozbalení zipu v C#.
linktitle: Decompressing a Stored File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořit zip bez komprese a rozbalit soubory – Aspose.Zip
url: /cs/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rozbalení uloženého souboru pomocí Aspose.Zip pro .NET

## Úvod

V moderních .NET aplikacích je **create zip without compression** užitečná technika, když potřebujete rychlé archivování bez režie snížení dat. Aspose.Zip pro .NET usnadňuje jak vytvořit takové archivy, tak později **extract multiple zip files**. V tomto tutoriálu uvidíte, jak otevřít zip, číst data zip entry a provést operaci **C# extract zip** krok za krokem.

## Rychlé odpovědi
- **Co je “create zip without compression”?** Znamená to přidání souborů do ZIP archivu pomocí metody “store”, která ponechává data nezměněná.
- **Která knihovna to v .NET řeší?** Aspose.Zip pro .NET.
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.
- **Mohu extrahovat několik souborů najednou?** Ano – tutoriál ukazuje, jak **extract multiple zip files** ve smyčce.
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je “create zip without compression”?
Když vytvoříte ZIP archiv pomocí kompresní metody **store**, každý soubor je přidán přesně tak, jak je. To vede k většímu archivu ve srovnání s komprimovanými ZIPy, ale operace je mnohem rychlejší a původní bajty souboru zůstávají nedotčeny – ideální pro situace, kde je rychlost nebo integrita dat důležitější než velikost.

## Proč používat Aspose.Zip pro .NET?
- **Plná kontrola** nad úrovní komprese (store vs. deflate).  
- **Jednoduché API** pro čtení položek, otevírání zip souborů a extrahování dat.  
- **Cross‑platform** podpora pro .NET Framework, .NET Core a .NET 5+.

## Požadavky

Než se pustíme do tohoto tutoriálu, ujistěte se, že máte následující požadavky:

- Aspose.Zip pro .NET knihovna: Stáhněte a nainstalujte knihovnu Aspose.Zip pro .NET. Knihovnu najdete [zde](https://releases.aspose.com/zip/net/).
- Adresář dokumentů: Vytvořte v systému adresář, kde budete ukládat potřebné soubory pro tento tutoriál.

## Importování jmenných prostorů

Na úvod importujme požadované jmenné prostory pro náš projekt:

```csharp
using Aspose.Zip;
using System.IO;
```

## Jak vytvořit ZIP bez komprese

Nejprve potřebujeme ZIP archiv, který používá metodu **store** (tj. bez komprese). Vzorový kód níže vytvoří takový archiv a je poskytován Aspose.Zip jako pomocná metoda. Po spuštění vygeneruje `StoreMultipleFilesWithoutCompression_out.zip` ve vašem adresáři dokumentů.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Tip:** Pomocná metoda interně nastavuje `CompressionMethod.Store` pro každou položku, čímž zajišťuje, že archiv je vytvořen bez jakékoli komprese dat.

## Jak otevřít ZIP a extrahovat více souborů

Nyní, když máme uložený ZIP, podívejme se, **jak otevřít zip** a vytáhnout soubory.

### Krok 2.1: Otevření ZIP souboru

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

Objekt `Archive` představuje otevřený ZIP a poskytuje přístup k jednotlivým položkám prostřednictvím kolekce `Entries`.

### Krok 2.2: Vytvoření extrahovaných souborů

```csharp
        using (var extracted = File.Create(dataDir + "alice_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[0].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
```

Zde **čteme zip entry** 0, zkopírujeme jeho bajty do nového souboru a díky `using` blokům se streamy automaticky uzavřou.

### Krok 2.3: Opakování procesu pro další soubor

```csharp
        using (var extracted = File.Create(dataDir + "asyoulik_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[1].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
    }
}
```

Iterací přes `archive.Entries` můžete **extract multiple zip files** (nebo více položek) pomocí jen několika řádků kódu.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| `FileNotFoundException` při otevírání ZIP | Špatná cesta `dataDir` | Ověřte, že `dataDir` končí lomítkem, nebo použijte `Path.Combine`. |
| Extrahovaný soubor je prázdný | Buffer nebyl vyprázdněn | `using` blok automaticky vyprázdní; ujistěte se, že čtete stream až do `bytesRead` rovno 0 (jak je ukázáno). |
| Výjimka licence | Spouštění bez platné licence | Použijte zkušební nebo trvalou licenci před nasazením. |

## Často kladené otázky

### Q1: Je Aspose.Zip pro .NET kompatibilní se všemi .NET frameworky?

**A:** Ano, Aspose.Zip pro .NET je navržen tak, aby byl kompatibilní s různými .NET frameworky, což vývojářům poskytuje flexibilitu.

### Q2: Mohu používat Aspose.Zip pro .NET jak v komerčních, tak nekomerčních projektech?

**A:** Ano, Aspose.Zip pro .NET lze použít jak v komerčních, tak nekomerčních projektech. Viz [stránka nákupu](https://purchase.aspose.com/buy) pro podrobnosti o licencování.

### Q3: Jak mohu získat podporu pro Aspose.Zip pro .NET?

**A:** Pro podporu navštivte [forum Aspose.Zip](https://forum.aspose.com/c/zip/37), kde vám může pomoci komunita vývojářů a odborníků.

### Q4: Je k dispozici bezplatná zkušební verze Aspose.Zip pro .NET?

**A:** Ano, můžete prozkoumat funkce Aspose.Zip pro .NET získáním bezplatné zkušební verze [zde](https://releases.aspose.com/).

### Q5: Mohu získat dočasnou licenci pro testovací účely?

**A:** Ano, můžete získat dočasnou licenci pro testování návštěvou [tohoto odkazu](https://purchase.aspose.com/temporary-license/).

### Q6: Jak přečíst zip entry bez extrahování celého archivu?

**A:** Použijte `archive.Entries[index].Open()` k získání streamu pro konkrétní položku, poté přečtěte potřebné bajty, jak je ukázáno v kódu výše.

### Q7: Jaký je nejlepší způsob, jak **extract multiple zip files** ve smyčce?

**A:** Procházejte `archive.Entries` pomocí `foreach` smyčky, otevřete stream každé položky a zapíšete jej do cílového souboru, podobně jako ve vzoru ukázaném v Krok 2.2 a 2.3.

## Závěr

Ovládnutí **create zip without compression** a následného procesu extrakce je nezbytné pro vysoce výkonné .NET aplikace. Aspose.Zip pro .NET poskytuje čisté, intuitivní API pro **how to open zip**, čtení každého **zip entry** a provedení operace **C# extract zip** s minimálním kódem. Dodržením tohoto návodu jste se naučili, jak vytvořit uložený archiv, otevřít jej a efektivně extrahovat jeho obsah.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-16  
**Testováno s:** Aspose.Zip pro .NET 24.12  
**Autor:** Aspose  

---