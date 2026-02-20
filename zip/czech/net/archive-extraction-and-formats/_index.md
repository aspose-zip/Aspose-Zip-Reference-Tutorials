---
date: 2026-02-20
description: Naučte se, jak komprimovat soubory tar.bz2, jak vytvářet archivy tar.gz
  a jak extrahovat .NET archivy s chráněnými zip soubory pomocí Aspose.Zip pro .NET.
  Zvyšte efektivitu úložiště a bezpečnost.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat soubory TarBz2 pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat soubory TarBz2 pomocí Aspose.Zip pro .NET

## Úvod

V tomto průvodci se naučíte **jak komprimovat tarbz2 soubory** pomocí Aspose.Zip pro .NET a zároveň objevíte, jak vytvořit archivy TarGz a provést .net extrakci archivů zip chráněných heslem. Efektivní práce se soubory je základním kamenem moderního vývoje v .NET a zvládnutí těchto formátů vám umožní snížit náklady na úložiště, urychlit přenos dat a udržet citlivé informace v bezpečí. Ať už budujete zálohovací službu, klienta cloud‑storage nebo datový zpracovatelský řetězec, techniky zde popsané učiní vaše úkoly správy souborů plynulejšími a spolehlivějšími.

## Rychlé odpovědi
- **What is TarBz2?** Komprimovaný archiv, který kombinuje balení TAR s kompresí BZIP2 pro vysoký kompresní poměr.  
- **Why choose Aspose.Zip for .NET?** Nabízí jednotné, plynulé API pro vytváření a extrahování mnoha archivních formátů bez externích závislostí.  
- **Can I create a TarGz archive?** Ano – Aspose.Zip podporuje TarGz, TarLz, TarXz, TarZ a další.  
- **How do I extract a password‑protected zip archive?** Použijte vlastnost `Password` na objektu `ArchiveEntry` při extrakci.  
- **Do I need a license for production use?** Pro produkční použití je vyžadována komerční licence; k hodnocení je k dispozici bezplatná zkušební verze.

## Jak komprimovat soubory TarBz2
Komprese souborů do TarBz2 znamená nejprve seskupit více souborů a adresářů do jediného **TAR** kontejneru a poté na něj aplikovat **BZIP2** kompresi. Výsledkem je jediný soubor `.tar.bz2`, který je snadno přenositelný a silně komprimovaný.

## Proč použít Aspose.Zip pro .NET k práci s těmito formáty?
- **Unified API** – Jedna knihovna, mnoho formátů (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Funguje na Windows, Linuxu i macOS bez dalších instalací.  
- **Password support** – Bezpečně chráníte a extrahujete archivy s hesly na úrovni jednotlivých položek.  
- **Performance‑focused** – Zpracování založené na streamech minimalizuje paměťovou stopu.

## Požadavky
- .NET 6.0 nebo novější (nebo .NET Core 3.1+ / .NET Framework 4.5+).  
- NuGet balíček Aspose.Zip pro .NET nainstalovaný (`Install-Package Aspose.Zip`).  
- Základní znalost C# a práce se soubory.

## Průvodce krok za krokem

### Krok 1: Vyberte formát archivu, který potřebujete
Rozhodněte se, zda **TarBz2**, **TarGz**, **TarLz**, **TarXz** nebo **TarZ** nejlépe vyhovuje vašim požadavkům na kompresní poměr a kompatibilitu.  
- **TarBz2** – Nejvyšší komprese, pomalejší zpracování.  
- **TarGz** – Dobrá rovnováha mezi rychlostí a velikostí (pokrývá sekundární klíčové slovo *how to create targz*).  
- **TarZ** – Legacy formát, užitečný pro kompatibilitu se staršími Unix nástroji.

### Krok 2: Vytvořte novou instanci `Archive`
Instancujte třídu `Archive` a nasměrujte ji na cestu výstupního souboru. Tento objekt bude řídit proces balení a komprese.

### Krok 3: Přidejte soubory a složky
Použijte metody `AddAll` nebo `AddFile` k zahrnutí souborů, které chcete komprimovat. Strukturu adresářů můžete zachovat přidáním základní složky.

### Krok 4: Nastavte požadovaný typ komprese
Při ukládání archivu specifikujte kompresní algoritmus (`CompressionType.BZip2`, `CompressionType.GZip` atd.). Zde skutečně **compress files to TarBz2** nebo jiný formát.

### Krok 5: Uložte archiv
Zavolejte `Save` s odpovídajícím enumem formátu (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz` atd.). Knihovna zapíše TAR kontejner a aplikuje zvolenou kompresi v jediném průchodu.

### Krok 6: Extrahování archivů s hesly
Pokud potřebujete **extract archive entries with different passwords** (sekundární klíčové slovo *password protected zip extraction*), otevřete archiv, najděte každou položku, přiřaďte jí heslo a poté ji extrahujte.

### Krok 7: Ověřte výsledek
Po extrakci porovnejte velikosti souborů a kontrolní součty, abyste se ujistili, že archiv byl vytvořen a rozbalen správně.

## Běžné případy použití
- **Zálohovací utility** – Ukládejte denní zálohy jako `.tar.bz2` pro minimalizaci nákladů na úložiště.  
- **Cross‑platform výměna dat** – Formáty založené na TAR jsou univerzálně podporovány na Linuxu, macOS i Windows.  
- **Bezpečná distribuce** – Chraňte jednotlivé položky hesly pro prostředí vyžadující soulad s předpisy.

## Řešení problémů a tipy
- **Large archives** – Používejte streaming API (`Archive.CreateEntryFromFile`) k zabránění načítání celých souborů do paměti.  
- **Password mismatches** – Ujistěte se, že heslo nastavené na každém `ArchiveEntry` odpovídá heslu použitému při extrakci; jinak dojde k `InvalidPasswordException`.  
- **Unsupported compression level** – BZIP2 nepodporuje vlastní úrovně komprese; pokud potřebujete jemnější kontrolu, zvažte TarLz nebo TarXz.

## Často kladené otázky

**Q: How do I create a TarGz archive?**  
A: Nastavte typ komprese na `CompressionType.GZip` a formát na `ArchiveFormat.TarGz` při volání `Save`.

**Q: Can I extract a password‑protected archive without knowing the password?**  
A: Ne. Každá položka musí být doplněna správným heslem, jinak extrakce selže.

**Q: Does Aspose.Zip support extracting archives with different passwords per entry?**  
A: Ano. Heslo můžete přiřadit každému `ArchiveEntry` individuálně před extrakcí.

**Q: Which format gives the best compression?**  
A: TarBz2 obvykle poskytuje nejvyšší kompresní poměr, následuje TarLz a TarXz. TarGz nabízí dobrý poměr rychlosti a velikosti.

**Q: Is there a limit to the number of files I can add to a TAR archive?**  
A: Prakticky ne, ale extrémně velké archivy mohou těžit ze rozdělení na více částí pro snazší správu.

## Tutoriály k extrakci archivů a formátům
### [File Compressing to TarBz2 with Aspose.Zip for .NET](./compress-to-tar-bz2/)
Naučte se komprimovat soubory do formátu TarBz2 v .NET pomocí Aspose.Zip. Sledujte náš krok‑za‑krokem průvodce pro efektivní kompresi souborů.  
### [Compressing to TarGz with Aspose.Zip for .NET](./compress-to-tar-gz/)
Prozkoumejte efektivní kompresi souborů v .NET s Aspose.Zip. Komprimujte do TarGz bez námahy.  
### [Compressing to TarLz with Aspose.Zip for .NET](./compress-to-tar-lz/)
Jednoduše komprimujte soubory v .NET s Aspose.Zip. Naučte se krok za krokem vytvářet archivy TarLz.  
### [Compressing to TarXz with Aspose.Zip for .NET](./compress-to-tar-xz/)
Naučte se komprimovat soubory do formátu TarXz v .NET pomocí Aspose.Zip. Sledujte náš podrobný průvodce pro efektivní úložiště a přenos dat.  
### [Compressing to TarZ with Aspose.Zip for .NET](./compress-to-tar-z/)
Prozkoumejte krok‑za‑krokem kompresi do TarZ pomocí Aspose.Zip pro .NET. Efektivní správa souborů pro vaše .NET projekty.  
### [Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET](./extract-archive-different-passwords/)
Naučte se extrahovat položky archivu s různými hesly v Aspose.Zip pro .NET. Zvyšte bezpečnost a flexibilitu ve svých aplikacích.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

---