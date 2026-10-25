---
date: 2026-10-25
description: Naučte se, jak extrahovat heslo zip a nastavit kompresní algoritmus při
  kompresi souborů tar pomocí Aspose.Zip pro .NET, což zvyšuje efektivitu úložiště
  a bezpečnost.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Extrahování archivů a formáty
og_description: Naučte se, jak extrahovat heslo zip a nastavit kompresní algoritmus
  při kompresi souborů tar pomocí Aspose.Zip pro .NET, což zvyšuje efektivitu úložiště
  a bezpečnost.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Extrahovat heslo zip a komprimovat soubory tar pomocí Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Extrahovat heslo zip a komprimovat soubory tar pomocí Aspose.Zip
url: /cs/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahování hesla zip a komprese tar souborů pomocí Aspose.Zip

## Úvod

V tomto průvodci objevíte techniky **extract zip password**, naučíte se, jak nastavit kompresní algoritmus při vytváření archivů založených na tar, a uvidíte, jak vytvořit formáty TarGz, TarBz2 a další pomocí Aspose.Zip pro .NET. Ať už vytváříte zálohovací službu, klienta cloud‑úložiště nebo datové zpracovatelské potrubí, zvládnutí těchto operací snižuje náklady na úložiště, urychluje přenosy a zabezpečuje citlivé soubory.

## Rychlé odpovědi
- **Co je TarBz2?** Komprimovaný archiv, který kombinuje balení TAR s kompresí BZIP2 pro vysoký kompresní poměr.  
- **Proč zvolit Aspose.Zip pro .NET?** Podporuje více než 50 archivních a kompresních formátů, běží na Windows, Linuxu a macOS a udržuje využití paměti pod 10 MB pro archivy o velikosti stovek megabajtů.  
- **Mohu vytvořit archiv TarGz?** Ano – Aspose.Zip nabízí TarGz, TarLz, TarXz, TarZ a další.  
- **Jak extrahovat zip archiv chráněný heslem?** Nastavte vlastnost `Password` u každého `ArchiveEntry` před voláním `Extract`.  
- **Potřebuji licenci pro produkční použití?** Pro produkci je vyžadována komerční licence; k vyhodnocení je k dispozici bezplatná zkušební verze.

## Co je komprese tar?

Komprese tar kombinuje kontejner TAR s kompresním algoritmem, jako je BZIP2, GZIP, LZMA nebo XZ. Výsledkem je jediný soubor (např. `.tar.gz`, `.tar.bz2`), který lze rozbalit na Linuxu, macOS i Windows. Zachovává původní hierarchii adresářů, umožňuje náhodný přístup k extrakci a je široce podporována příkazovými řádky i programovacími knihovnami, což ji činí ideální pro multiplatformní distribuci a archivní úložiště.

## Proč používat Aspose.Zip pro .NET k práci s těmito formáty?

Aspose.Zip poskytuje jednotné, bezzávislé API, které podporuje **50+** archivních a kompresních formátů, včetně všech hlavních typů založených na tar. Jeho streamingová architektura zpracovává archivy větší než 10 GB při využití RAM pod 10 MB, což je ideální pro vysokovýkonné serverové úlohy.  

**Přímá odpověď:** Používáte Aspose.Zip, protože vám umožňuje vytvářet, komprimovat a extrahovat tar‑založené archivy a zip soubory chráněné heslem pomocí jediné plynulé API, bez externích nástrojů, a to při zpracování více gigabajtových archivů v paměťově úsporném streamingovém režimu.

## Požadavky
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, or .NET 5–10.  
- Aspose.Zip for .NET NuGet package (`Install-Package Aspose.Zip`).  
- Základní znalost souborového I/O v C# a systému .NET projektů.

## Průvodce krok za krokem

### Jak komprimovat tar soubory – přímá odpověď
Vytvořte instanci `Archive`, přidejte soubory, které chcete zabalit, nastavte `CompressionType.BZip2` (nebo jiný algoritmus) a zavolejte `Save` s `ArchiveFormat.TarBz2`. Knihovna zapíše kontejner TAR a komprimuje jej v jednom streamingovém průchodu, takže nikdy nenačtete celý archiv do paměti.

### Krok 1: Vyberte požadovaný formát archivu
Rozhodněte se, který formát založený na tar nejlépe odpovídá vašemu kompromisu mezi kompresí a rychlostí:

- **TarBz2** – Nejvyšší kompresní poměr (≈30 % menší než TarGz), ale pomalejší.  
- **TarGz** – Dobrá rovnováha mezi rychlostí a velikostí; ideální pro většinu scénářů cloud‑úložiště.  
- **TarLz / TarXz** – Velmi vysoká komprese při střední rychlosti, užitečná pro archivní úložiště.  
- **TarZ** – Starší formát pro kompatibilitu se staršími Unixovými nástroji.

### Krok 2: Vytvořte novou instanci `Archive`
`Archive` představuje jeden archivní soubor a poskytuje metody pro přidání položek a uložení archivu.  
Třída `Archive` řídí proces balení a komprese, poskytuje metody pro přidání položek a zápis výsledného souboru.

### Krok 3: Přidejte soubory a složky
Můžete přidat celý strom adresářů pomocí `AddAll` nebo jednotlivé soubory pomocí `AddFile`.  

`AddAll` přidá celý strom adresářů do archivu a zachová jeho strukturu.  
`AddFile` přidá jeden soubor do archivu. Zachování původní hierarchie složek je tak jednoduché, jako předat cestu k základnímu adresáři.

### Krok 4: Nastavte požadovaný typ komprese
`CompressionType` výčet určuje kompresní algoritmus aplikovaný na TAR stream.  

`CompressionType` vyjmenovává podporované algoritmy (BZip2, GZip, LZMA, XZ, atd.), které budou použity při ukládání.

### Krok 5: Uložte archiv
`ArchiveFormat` výčet vybírá kombinaci kontejneru a komprese pro výstupní soubor.  

Voláním `Save` zapíšete archiv na disk pomocí vybraného formátu.

### Krok 6: Extrahování archivů s hesly
`ArchiveEntry` představuje jeden soubor nebo položku adresáře uvnitř archivu.  

Aby bylo možné extrahovat zip chráněný heslem, otevřete archiv, najděte každou `ArchiveEntry`, přiřaďte jí vlastnost `Password` a zavolejte `Extract`. Vlastnost `Password` nastavuje dešifrovací heslo pro zip položku. Tento model hesla na úrovni položky vám umožňuje chránit jednotlivé soubory uvnitř jednoho zipu.

### Krok 7: Ověřte výsledek
Po extrakci porovnejte velikosti souborů a kontrolní součty SHA‑256, abyste potvrdili, že archivní průchod zachoval integritu dat.

## Běžné případy použití
- **Zálohovací nástroje** – Ukládejte denní zálohy jako `.tar.bz2`, čímž snížíte náklady na úložiště až o 30 %.  
- **Mezi‑platformní výměna dat** – Formáty založené na tar jsou nativně podporovány nástroji na Linuxu, macOS a Windows.  
- **Bezpečná distribuce** – Přidělte hesla citlivým položkám, čímž splníte požadavky na shodu bez dalších šifrovacích nástrojů.

## Řešení problémů a tipy
- **Velké archivy** – Použijte streamingové API (`Archive.CreateEntryFromFile`) pro udržení nízké spotřeby paměti.  
- **Neshoda hesel** – Heslo nastavené u každého `ArchiveEntry` se musí přesně shodovat; jinak je vyvolána výjimka `InvalidPasswordException`.  
- **Úroveň komprese** – BZIP2 neumožňuje nastavit vlastní úrovně; pokud potřebujete jemnější kontrolu, přepněte na LZMA (`CompressionType.LZMA`) nebo XZ (`CompressionType.XZ`).  

## Často kladené otázky

**Q: Jak vytvořit archiv TarGz?**  
A: Nastavte `CompressionType.GZip` a použijte `ArchiveFormat.TarGz` při volání `Save`. Tím vznikne soubor `.tar.gz` v jediném kroku.

**Q: Můžu extrahovat archiv chráněný heslem bez znalosti hesla?**  
A: Ne. Každá položka musí být doplněna správným heslem; jinak extrakce selže s výjimkou `InvalidPasswordException`.

**Q: Podporuje Aspose.Zip extrahování archivů s různými hesly pro jednotlivé položky?**  
A: Ano. Přiřaďte každému `ArchiveEntry` individuálně heslo před voláním `Extract`.

**Q: Který formát poskytuje nejlepší kompresi?**  
A: TarBz2 obvykle dává nejmenší velikost, následován TarLz a TarXz. TarGz nabízí rychlejší, ale stále efektivní alternativu.

**Q: Existuje limit na počet souborů, které mohu přidat do TAR archivu?**  
A: Prakticky žádný, ale extrémně velké archivy (>10 GB) mohou těžit z rozdělení do více částí pro snazší správu.

## Tutoriály pro extrakci archivů a formáty

### [Komprimování souborů do TarBz2 pomocí Aspose.Zip pro .NET](./compress-to-tar-bz2/)
Learn how to compress files to TarBz2 format in .NET using Aspose.Zip. Follow our step‑by‑step guide for efficient file compression.  
### [Komprimování do TarGz pomocí Aspose.Zip pro .NET](./compress-to-tar-gz/)
Explore efficient file compression in .NET with Aspose.Zip. Compress to TarGz effortlessly.  
### [Komprimování do TarLz pomocí Aspose.Zip pro .NET](./compress-to-tar-lz/)
Effortlessly compress files in .NET with Aspose.Zip. Learn to create TarLz archives step‑by‑step.  
### [Komprimování do TarXz pomocí Aspose.Zip pro .NET](./compress-to-tar-xz/)
Learn to compress files to TarXz format in .NET using Aspose.Zip. Follow our guide for efficient storage and transmission.  
### [Komprimování do TarZ pomocí Aspose.Zip pro .NET](./compress-to-tar-z/)
Explore step‑by‑step compression to TarZ using Aspose.Zip for .NET. Efficient file handling for your .NET projects.  
### [Extrahování položek archivu s různými hesly v Aspose.Zip pro .NET](./extract-archive-different-passwords/)
Learn how to extract archive entries with different passwords in Aspose.Zip for .NET. Boost security and flexibility in your applications.

## Související tutoriály

- [Vytvořit tar archiv a přidat soubory do tar pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak komprimovat tar a vytvořit TarBz2 pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Přidat soubory do tar a vytvořit tarxz archiv pomocí Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Last Updated:** 2026-10-25  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}