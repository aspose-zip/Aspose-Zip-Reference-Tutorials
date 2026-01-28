---
date: 2026-01-28
description: Naučte se, jak rozbalit archiv s heslem, komprimovat soubory do TarBz2
  a vytvářet archivy TarGz pomocí Aspose.Zip pro .NET. Zvyšte efektivitu úložiště
  a bezpečnost.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Rozbalit archiv s heslem a komprimovat do TarBz2 (.NET)
url: /cs/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahování archivu s heslem a komprese do TarBz2 (.NET)

V tomto průvodci se dozvíte **jak extrahovat archiv s heslem** a také ovládnete **kompresi souborů do TarBz2** pomocí Aspose.Zip pro .NET. Ať už vytváříte zálohovací službu, klienta cloud‑storage nebo datové zpracovatelské potrubí, tyto techniky vám umožní zmenšit objem úložiště, urychlit přenosy a udržet citlivá data chráněná.

## Rychlé odpovědi
- **Co je TarBz2?** Komprimovaný archiv, který kombinuje balení TAR s kompresí BZIP2 pro vysoký kompresní poměr.  
- **Proč zvolit Aspose.Zip pro .NET?** Poskytuje jednotné, plynulé API pro mnoho formátů archivů bez nativních závislostí.  
- **Mohu vytvořit archiv TarGz?** Ano – Aspose.Zip podporuje TarGz, TarLz, TarXz, TarZ a další.  
- **Jak extrahovat archiv chráněný heslem?** Nastavte vlastnost `Password` u každého `ArchiveEntry` před extrakcí.  
- **Potřebuji licenci pro produkční použití?** Pro produkci je vyžadována komerční licence; k vyzkoušení je k dispozici bezplatná zkušební verze.

## Jak extrahovat archiv s heslem pomocí Aspose.Zip pro .NET
Extrahování archivu, který je **password protect zip archive** chráněn, je jednoduché. Otevřete archiv, najdete požadovanou položku, přiřadíte jí heslo a zavoláte `Extract`. Tento postup funguje pro TarBz2, TarGz i další podporované formáty.

## Co vlastně znamená „komprese souborů do TarBz2“?
Komprese souborů do TarBz2 nejprve spojí více souborů a adresářů do jediného **TAR** kontejneru a následně na něj použije **BZIP2** kompresi. Výsledkem je soubor `.tar.bz2`, který je snadno přenositelný a silně komprimovaný.

## Proč použít Aspose.Zip pro .NET k práci s těmito formáty?
- **Jednotné API** – Jedna knihovna, mnoho formátů (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Žádné nativní závislosti** – Funguje na Windows, Linuxu i macOS bez dalších úprav.  
- **Podpora hesel** – Bezpečně chráníte a extrahujete archivy s hesly na úrovni jednotlivých položek.  
- **Výkonnostně orientované** – Zpracování na základě streamů minimalizuje využití paměti.

## Předpoklady
- .NET 6.0 nebo novější (nebo .NET Core 3.1+ / .NET Framework 4.5+).  
- Nainstalovaný NuGet balíček Aspose.Zip pro .NET (`Install-Package Aspose.Zip`).  
- Základní znalost C# a práce se soubory.

## Průvodce krok za krokem

### Krok 1: Vyberte požadovaný formát archivu
Rozhodněte, zda **TarBz2**, **TarGz**, **TarLz**, **TarXz** nebo **TarZ** nejlépe vyhovuje vašim požadavkům na kompresní poměr a kompatibilitu.  
- **TarBz2** – Nejvyšší komprese, pomalejší zpracování.  
- **TarGz** – Dobrá rovnováha mezi rychlostí a velikostí (pokrývá sekundární klíčové slovo *compress files to targz*).  
- **TarZ** – Legacy formát pro starší Unixové nástroje.

### Krok 2: Vytvořte novou instanci `Archive`
Instanciujte třídu `Archive` a nasměrujte ji na výstupní cestu souboru. Tento objekt bude řídit proces balení a komprese.

### Krok 3: Přidejte soubory a složky
Použijte metody `AddAll` nebo `AddFile` k zahrnutí souborů, které chcete komprimovat. Zachovejte strukturu adresářů přidáním základní složky.

### Krok 4: Nastavte požadovaný typ komprese
Při ukládání archivu specifikujte kompresní algoritmus (`CompressionType.BZip2`, `CompressionType.GZip` atd.). Zde skutečně **compress files to tarbz2** nebo jiný formát.

### Krok 5: Uložte archiv
Zavolejte `Save` s odpovídajícím enumem formátu (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz` atd.). Knihovna zapíše TAR kontejner a aplikuje zvolenou kompresi v jediném průchodu.

### Krok 6: Extrahujte archivy s hesly
Pokud potřebujete **extract archive entries with different passwords** (sekundární klíčové slovo *how to extract password protected archive*), otevřete archiv, najděte každou položku, přiřaďte jí heslo a poté ji extrahujte.

### Krok 7: Ověřte výsledek
Po extrakci porovnejte velikosti souborů a kontrolní součty, abyste se ujistili, že archiv byl vytvořen a rozbalen správně.

## Běžné scénáře použití
- **Zálohovací utility** – Ukládejte denní zálohy jako `.tar.bz2` pro snížení nákladů na úložiště.  
- **Cross‑platform výměna dat** – Formáty založené na TAR jsou univerzálně podporovány na Linuxu, macOS i Windows.  
- **Bezpečná distribuce** – Chraňte jednotlivé položky hesly pro prostředí s přísnými požadavky na soulad.

## Řešení problémů a tipy
- **Velké archivy** – Používejte streaming API (`Archive.CreateEntryFromFile`), abyste se vyhnuli načítání celých souborů do paměti.  
- **Neshoda hesel** – Ujistěte se, že heslo nastavené u každého `ArchiveEntry` odpovídá heslu použitému při extrakci; jinak dojde k `InvalidPasswordException`.  
- **Nedostupná úroveň komprese** – BZIP2 nepodporuje vlastní úrovně komprese; pokud potřebujete jemnější kontrolu, zvažte TarLz nebo TarXz.  
- **Tip pro výkon** – Při vytváření **create tarbz2 archive** povolte bufferování na podkladovém streamu, aby se zvýšila rychlost zápisu.

## Často kladené otázky

**Q: Jak vytvořím archiv TarGz?**  
A: Nastavte typ komprese na `CompressionType.GZip` a formát na `ArchiveFormat.TarGz` při volání `Save`.

**Q: Můžu extrahovat archiv chráněný heslem bez znalosti hesla?**  
A: Ne. Každá položka musí být doplněna správným heslem, jinak extrakce selže.

**Q: Podporuje Aspose.Zip extrakci archivů s různými hesly pro jednotlivé položky?**  
A: Ano. Heslo můžete přiřadit každému `ArchiveEntry` samostatně před extrakcí.

**Q: Který formát poskytuje nejlepší kompresi?**  
A: TarBz2 obvykle nabízí nejvyšší kompresní poměr, následují TarLz a TarXz. TarGz poskytuje dobrý poměr rychlosti a velikosti.

**Q: Existuje limit na počet souborů, které mohu přidat do TAR archivu?**  
A: Prakticky žádný, ale extrémně velké archivy mohou mít výhodu v rozdělení na více částí pro snazší manipulaci.

## Tutoriály k extrakci archivů a formátům
### [File Compressing to TarBz2 with Aspose.Zip for .NET](./compress-to-tar-bz2/)
Naučte se komprimovat soubory do formátu TarBz2 v .NET pomocí Aspose.Zip. Postupujte podle našeho krok‑za‑krokem průvodce pro efektivní kompresi souborů.
### [Compressing to TarGz with Aspose.Zip for .NET](./compress-to-tar-gz/)
Prozkoumejte efektivní kompresi souborů v .NET s Aspose.Zip. Komprimujte do TarGz snadno.
### [Compressing to TarLz with Aspose.Zip for .NET](./compress-to-tar-lz/)
Jednoduše komprimujte soubory v .NET s Aspose.Zip. Naučte se vytvářet TarLz archivy krok za krokem.
### [Compressing to TarXz with Aspose.Zip for .NET](./compress-to-tar-xz/)
Naučte se komprimovat soubory do formátu TarXz v .NET pomocí Aspose.Zip. Sledujte náš podrobný průvodce pro efektivní ukládání a přenos dat.
### [Compressing to TarZ with Aspose.Zip for .NET](./compress-to-tar-z/)
Prozkoumejte krok‑za‑krokem kompresi do TarZ pomocí Aspose.Zip pro .NET. Efektivní manipulace se soubory pro vaše .NET projekty.
### [Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET](./extract-archive-different-passwords/)
Naučte se extrahovat položky archivu s různými hesly v Aspose.Zip pro .NET. Zvyšte bezpečnost a flexibilitu ve svých aplikacích.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-28  
**Testováno s:** Aspose.Zip pro .NET 24.11  
**Autor:** Aspose  

---