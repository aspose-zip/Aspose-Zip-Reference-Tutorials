---
date: 2025-12-10
description: Naučte se, jak ukládat soubory bez komprese pomocí Aspose.Zip pro .NET.
  Tento průvodce vám ukáže, jak vytvořit nekomprimovaný zip, uložit soubory do zipu
  a efektivně spravovat archivy.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak ukládat soubory nekomprimovaně pomocí Aspose.Zip pro .NET
url: /cs/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ukládat soubory bez komprese pomocí Aspose.Zip pro .NET

V moderním vývoji .NET může **jak ukládat soubory** efektivně znamenat velký rozdíl ve výkonu a nákladech na úložiště. Když potřebujete zachovat sou tak, jak jsou – bez jakékoli komprese – Aspose.Zip pro .NET poskytuje čisté a jednoduché API. V tomto tutoriálu vás provedeme kroky k vytvoření nekomprimovaného ZIP archivu, uložení souborů do ZIP a integraci řešení do vaší aplikace.

## Rychlé odpovědi
- **Co znamená „nekomprimovaný zip“?** Jedná se o ZIP archiv, kde je každý záznam uložen metodou „store“, takže původní bajty souboru zůstávají nedotčeny.  
- **Proč se vyhýbat kompresi?** Pro zrychlení archivace, zachování původních velikostí souborů pro následné zpracování nebo splnění regulačních požadavků, které zakazují úpravu dat.  
- **Která třída Aspose.Zip to řeší?** `ArchiveEntrySettings` v kombinaci s `StoreCompressionSettings`.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework, .NET Core, .NET 5/6/7 a novější.

## Co je ukládání více souborů bez komprese?
Ukládání více souborů bez komprese znamená přidání každého souboru do ZIP kontejneru pomocí *store* kompresní metody. Soubory zůstávají bajt‑po‑bajtu identické s originály, což je ideální, když chcete rychlou archivaci nebo potřebujete data ponechat nezměněná.

## Proč použít Aspose.Zip pro nekomprimované archivy?
- **Rychlost:** Nespouští se žádné CPU‑intenzivní kompresní algoritmy.  
- **Předvídatelná velikost:** Velikost archivu se rovná součtu původních souborů plus minimální režii ZIP.  
- **Kompatibilita:** Výsledný ZIP funguje s jakýmkoli standardním nástrojem pro rozbalování.  
- **Flexibilita:** V případě potřeby můžete v jednom archivu kombinovat komprimované i nekomprimované položky.

## Předpoklady
- **Aspose.Zip for .NET** – integrováno do vašeho projektu. Viz oficiální [dokumentace](https://reference.aspose.com/zip/net/) pro kroky instalace.  
- **Vývojové prostředí .NET** – Visual Studio, VS Code nebo jakékoli IDE, které preferujete.  
- **Adresář dokumentů** – složka ve vašem počítači obsahující soubory, které chcete archivovat (např. „Your Document Directory“).

## Importujte jmenné prostory
Před psaním jakéhokoli kódu importujte požadované jmenné prostory, aby kompilátor věděl, kde najít třídy Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Krok 1: Nastavte adresář dokumentů
Definujte cestu, kde se nacházejí vaše zdrojové soubory. Nahraďte zástupný text skutečnou složkou ve vašem systému.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte ZIP archiv bez komprese
Jádro tutoriálu – vytvoříme instanci `Archive` nakonfigurovanou pomocí `StoreCompressionSettings`. Tím říkáme Aspose.Zip, aby *uložil* (tj. nekomprimoval) každý záznam.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Pro tip:** Pokud potřebujete **uložit soubory do zip** při kompresi některých a ponechání jiných nekomprimovaných, vytvořte samostatné instance `ArchiveEntrySettings` pro každý soubor a přidejte je do stejného `Archive`.

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **Soubor nenalezen** | Nesprávná cesta `dataDir` nebo chybějící přípona souboru. | Ověřte cestu a ujistěte se, že soubory existují. Použijte `Path.Combine` pro bezpečnější spojování. |
| **Přístup odmítnut** | Proces nemá oprávnění číst zdrojové soubory nebo zapisovat ZIP. | Spusťte aplikaci s odpovídajícími právy nebo vyberte složku s právy zápisu. |
| **Neočekávaná velikost souboru v ZIP** | Archiv byl vytvořen s výchozí kompresí. | Ujistěte se, že `new StoreCompressionSettings()` je předáno do `ArchiveEntrySettings`. |

## Často kladené otázky

**Q: Mohu komprimovat konkrétní typy souborů a jiné ukládat bez komprese?**  
A: Ano, můžete vytvořit různé `ArchiveEntrySettings` pro každý soubor a v jednom archivu kombinovat komprimované i nekomprimované položky.

**Q: Je Aspose.Zip pro .NET kompatibilní s .NET Core a .NET 5/6?**  
A: Rozhodně. Knihovna podporuje .NET Framework, .NET Core, .NET Standard i nejnovější verze .NET.

**Q: Jak mám zacházet s výjimkami během procesu archivace?**  
A: Zabalte kód archivace do bloku `try‑catch` a zaznamenejte podrobnosti výjimky. To zajišťuje elegantní selhání a usnadňuje ladění.

**Q: Podporuje Aspose.Zip vícevláknovou archivaci?**  
A: Ano, můžete zpracovávat více souborů paralelně a přidávat je do archivu, ale pamatujte, že objekt `Archive` není thread‑safe; při přidávání položek synchronizujte přístup.

**Q: Můžu integrovat Aspose.Zip do existujícího projektu bez velkých změn kódu?**  
A: Určitě. API je navrženo pro jednoduché „drop‑in“ použití. Viz oficiální [dokumentace](https://reference.aspose.com/zip/net/) pro pokyny k migraci.

**Poslední aktualizace:** 2025-12-10  
**Testováno s:** Aspose.Zip for .NET 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}