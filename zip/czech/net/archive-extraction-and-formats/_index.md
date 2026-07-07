---
date: 2026-06-19
description: Naučte se, jak komprimovat tar soubory, vytvářet targz archivy a extrahovat
  password‑protected zip soubory pomocí Aspose.Zip pro .NET – zvyšování efektivity
  úložiště a bezpečnosti.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Extrahování archivů a formáty
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat tar soubory pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat soubory Tar pomocí Aspose.Zip pro .NET

## Úvod

Cílem tohoto průvodce je ukázat, **jak komprimovat tar** soubory pomocí Aspose.Zip pro .NET, naučit se vytvářet archivy TarGz a ukázat, jak rozbalit zip archivy chráněné heslem. Efektivní práce s archivy je základní dovedností moderních .NET vývojářů – ať už vytváříte zálohovací službu, klienta cloud‑storage nebo datové zpracování, ovládnutí těchto formátů snižuje náklady na úložiště, urychluje přenosy a chrání citlivá data.

## Rychlé odpovědi
- **Co je TarBz2?** Komprimovaný archiv, který kombinuje balení TAR s kompresí BZIP2 pro vysoký poměr komprese.  
- **Proč zvolit Aspose.Zip pro .NET?** Poskytuje jednotné, plynulé API pro vytváření a rozbalování mnoha formátů archivů bez externích závislostí.  
- **Mohu vytvořit archiv TarGz?** Ano – Aspose.Zip podporuje TarGz, TarLz, TarXz, TarZ a další.  
- **Jak rozbalit zip archiv chráněný heslem?** Použijte vlastnost `Password` na objektu `ArchiveEntry` při rozbalování.  
- **Potřebuji licenci pro produkční použití?** Pro produkci je vyžadována komerční licence; pro hodnocení je k dispozici bezplatná zkušební verze.

## Co je komprese Tar?
Tar (Tape Archive) je kontejnerový formát, který spojuje více souborů a adresářů do jednoho proudu bez komprese. Když použijete kompresní algoritmus jako BZIP2, GZip, LZMA nebo XZ, výsledkem je **tar‑based archiv** jako `.tar.bz2`, `.tar.gz`, `.tar.lz` atd. Tyto formáty jsou široce podporovány na Linuxu, macOS a Windows, což je činí ideálními pro výměnu dat napříč platformami.

## Proč použít Aspose.Zip pro .NET k práci s těmito formáty?
Aspose.Zip poskytuje **jednotné, bezzávislé API**, které podporuje více než 50 formátů archivů a komprese, včetně TarBz2, TarGz, TarLz, TarXz a TarZ. Běží na Windows, Linuxu i macOS a jeho architektura založená na streamech udržuje využití paměti pod 10 MB i u archivů o velikosti stovek megabajtů. Ochrana heslem je vestavěná, což umožňuje šifrování jednotlivých položek bez dalších knihoven.

## Požadavky
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 nebo .NET 5–10.  
- NuGet balíček Aspose.Zip pro .NET nainstalován (`Install-Package Aspose.Zip`).  
- Základní znalost C# souborového I/O a systému .NET projektů.

## Průvodce krok za krokem

### Jak komprimovat soubory Tar – Přímá odpověď
`Archive` představuje archivní soubor a poskytuje metody pro přidání položek a uložení.  
Vytvořte instanci `Archive`, přidejte soubory, které chcete spojit, nastavte `CompressionType.BZip2` a zavolejte `Save` s `ArchiveFormat.TarBz2`. Knihovna zapíše kontejner TAR a komprimuje jej v jediném průchodu streamem, takže nikdy nenačítáte celý archiv do paměti.

### Krok 1: Vyberte požadovaný formát archivu
Rozhodněte, který tar‑based formát nejlépe vyhovuje vašemu kompromisu mezi kompresí a rychlostí:

- **TarBz2** – Nejvyšší poměr komprese (≈30 % menší než TarGz), ale pomalejší.  
- **TarGz** – Dobrá rovnováha mezi rychlostí a velikostí; ideální pro většinu scénářů cloud‑storage.  
- **TarLz / TarXz** – Velmi vysoká komprese při střední rychlosti, užitečné pro archivní úložiště.  
- **TarZ** – Starší formát pro kompatibilitu se staršími Unixovými nástroji.

### Krok 2: Vytvořte novou instanci `Archive`
`Archive` je objekt nejvyšší úrovně, který v paměti představuje jeden archivní soubor.  
Třída `Archive` řídí workflow balení a komprese, poskytuje metody pro přidání položek a zápis finálního souboru.

### Krok 3: Přidejte soubory a složky
Můžete přidat celý strom adresářů pomocí `AddAll` nebo jednotlivé soubory pomocí `AddFile`. Zachování původní hierarchie složek je tak jednoduché, jako předat cestu k základnímu adresáři.

### Krok 4: Nastavte požadovaný typ komprese
`CompressionType` vyjmenovává podporované algoritmy.  
`CompressionType` určuje algoritmus (BZip2, GZip, LZMA, XZ atd.), který bude během ukládání aplikován na TAR stream.

### Krok 5: Uložte archiv
`ArchiveFormat` je výčtová sada (např. `TarBz2`, `TarGz`), která říká zapisovači, který kontejner a kompresi použít.  
Volání `Save` zapíše archiv na disk pomocí vybraného formátu.

### Krok 6: Rozbalování archivů s hesly
`ArchiveEntry` představuje jeden soubor nebo položku adresáře uvnitř archivu.  
Pro rozbalení zip archivu chráněného heslem otevřete archiv, najděte každou `ArchiveEntry`, přiřaďte jí vlastnost `Password` a zavolejte `Extract`. Tento model hesla na úrovni položky vám umožní chránit jednotlivé soubory uvnitř jednoho zipu.

### Krok 7: Ověřte výsledek
Po rozbalení porovnejte velikosti souborů a kontrolní součty SHA‑256, abyste potvrdili, že archivní průchod zachoval integritu dat.

## Běžné případy použití
- **Zálohovací nástroje** – Ukládejte denní zálohy jako `.tar.bz2` a snižte náklady na úložiště až o 30 %.  
- **Výměna dat napříč platformami** – Formáty založené na Tar jsou nativně podporovány nástroji na Linuxu, macOS a Windows.  
- **Bezpečná distribuce** – Přiřaďte hesla citlivým položkám, čímž splníte požadavky na shodu bez dalších šifrovacích nástrojů.

## Řešení problémů a tipy
- **Velké archivy** – Upřednostněte streaming API (`Archive.CreateEntryFromFile`) pro udržení nízké spotřeby paměti.  
- **Neshoda hesel** – Heslo nastavené na každém `ArchiveEntry` musí být přesně shodné; jinak je vyvolána `InvalidPasswordException`.  
- **Úroveň komprese** – BZIP2 neumožňuje nastavit vlastní úrovně; pokud potřebujete jemnější kontrolu, přepněte na LZMA (`CompressionType.LZMA`) nebo XZ (`CompressionType.XZ`).  

## Často kladené otázky

**Q: Jak vytvořím archiv TarGz?**  
A: Nastavte `CompressionType.GZip` a při volání `Save` použijte `ArchiveFormat.TarGz`. Tím vznikne soubor `.tar.gz` v jednom kroku.

**Q: Mohu rozbalit archiv chráněný heslem, aniž bych znal heslo?**  
A: Ne. Každá položka musí být doplněna správným heslem; jinak rozbalení selže s `InvalidPasswordException`.

**Q: Podporuje Aspose.Zip rozbalování archivů s různými hesly pro jednotlivé položky?**  
A: Ano. Přiřaďte heslo každému `ArchiveEntry` samostatně před voláním `Extract`.

**Q: Který formát poskytuje nejlepší kompresi?**  
A: TarBz2 obvykle dává nejmenší velikost, následovaný TarLz a TarXz. TarGz nabízí rychlejší, stále efektivní alternativu.

**Q: Existuje limit na počet souborů, které mohu přidat do TAR archivu?**  
A: Prakticky žádný, ale extrémně velké archivy (>10 GB) mohou mít výhodu rozdělení na více částí pro snazší správu.

## Tutoriály pro rozbalování archivů a formáty

### [Komprese souborů do TarBz2 pomocí Aspose.Zip pro .NET](./compress-to-tar-bz2/)
Naučte se komprimovat soubory do formátu TarBz2 v .NET pomocí Aspose.Zip. Postupujte podle našeho krok‑za‑krokem průvodce pro efektivní kompresi souborů.  

### [Komprese do TarGz pomocí Aspose.Zip pro .NET](./compress-to-tar-gz/)
Prozkoumejte efektivní kompresi souborů v .NET s Aspose.Zip. Komprimujte do TarGz bez námahy.  

### [Komprese do TarLz pomocí Aspose.Zip pro .NET](./compress-to-tar-lz/)
Jednoduše komprimujte soubory v .NET s Aspose.Zip. Naučte se vytvářet archivy TarLz krok za krokem.  

### [Komprese do TarXz pomocí Aspose.Zip pro .NET](./compress-to-tar-xz/)
Naučte se komprimovat soubory do formátu TarXz v .NET pomocí Aspose.Zip. Postupujte podle našeho průvodce pro efektivní úložiště a přenos.  

### [Komprese do TarZ pomocí Aspose.Zip pro .NET](./compress-to-tar-z/)
Prozkoumejte krok‑za‑krokem kompresi do TarZ pomocí Aspose.Zip pro .NET. Efektivní práce se soubory pro vaše .NET projekty.  

### [Rozbalování položek archivu s různými hesly v Aspose.Zip pro .NET](./extract-archive-different-passwords/)
Naučte se rozbalovat položky archivu s různými hesly v Aspose.Zip pro .NET. Zvyšte bezpečnost a flexibilitu ve svých aplikacích.

---

**Poslední aktualizace:** 2026-06-19  
**Testováno s:** Aspose.Zip pro .NET 24.11  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit tar archiv a přidat soubory do tar pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak komprimovat tar a vytvořit TarBz2 s Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Přidat soubory do tar a vytvořit tarxz archiv s Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}