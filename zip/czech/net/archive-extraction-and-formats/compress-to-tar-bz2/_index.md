---
date: 2026-10-31
description: Naučte se, jak vytvořit tar archiv a komprimovat jej do souboru TarBz2
  v .NET pomocí Aspose.Zip. Průvodce krok za krokem ukazuje tvorbu tar, kompresi Bzip2
  a tipy na osvědčené postupy.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: Komprese do TarBz2
og_description: Naučte se, jak vytvořit tar archiv a komprimovat jej do souboru TarBz2
  pomocí Aspose.Zip pro .NET. Průvodce krok za krokem pokrývá tvorbu tar, kompresi
  Bzip2 a tipy na osvědčené postupy.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: Vytvořte tar archiv a komprimujte do TarBz2 pomocí .NET
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Jak vytvořit tar archiv a komprimovat do TarBz2 pomocí .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit tar archiv a komprimovat do TarBz2 pomocí .NET

V tomto tutoriálu se naučíte **jak vytvořit tar archiv** soubory a poté je komprimovat do kompaktního **TarBz2** balíčku pomocí knihovny **Aspose.Zip** pro .NET. Ať už vytváříte nástroj pro zálohování, připravujete balíčky pro nasazení, nebo potřebujete lehký distribuční formát, níže uvedené kroky vás provedou přidáním souborů do tar kontejneru, aplikací Bzip2 komprese a zápisem finálního souboru `.tar.bz2`.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip for .NET  
- **Jak dlouho trvá implementace?** About 5‑10 minutes  
- **Potřebuji licenci?** A temporary license is required for production; a free trial is available  
- **Mohu komprimovat více souborů?** Yes – add as many entries as you like to the tar archive  
- **Je kompatibilní s .NET 6+?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## Co je TarBz2 archiv?

Soubor TarBz2 kombinuje tradiční **tar** kontejner (který zachovává strukturu adresářů a metadata souborů) s kompresí **Bzip2**, což vede k vysoce komprimovanému balíčku `.tar.bz2`. Tento formát je populární na Unix‑like systémech, protože nabízí dobrý poměr mezi kompresním poměrem a rychlostí dekomprese.

## Proč komprimovat soubory do TarBz2 pomocí Aspose.Zip?

Aspose.Zip může vytvořit TarBz2 archiv pomocí **dvou volání API**, přičemž efektivně pracuje se streamy. Podporuje **více než 50 formátů archivů a komprese**, zpracovává soubory až do **2 GB** bez načítání celého archivu do paměti a běží na .NET runtime pro Windows, Linux a macOS. Knihovna vám také poskytuje detailní kontrolu nad názvy položek, časovými razítky a úrovněmi komprese, což ji činí ideální pro konzolové nástroje i webové služby.

## Požadavky

- **Aspose.Zip for .NET** – stáhněte nejnovější balíček z oficiálního webu: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – složka, která obsahuje soubory, které chcete archivovat. V příkladech na ni odkazujeme pomocí proměnné `dataDir`.

> **Tip:** Uchovávejte své zdrojové soubory v samostatné složce, abyste se vyhnuli neúmyslnému zahrnutí nežádoucích souborů.

## Importujte jmenné prostory

Nejprve importujte požadované jmenné prostory, abyste mohli přistupovat ke třídám Tar a Bzip2 z Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Krok 1: nastavení adresáře dokumentů

Definujte cestu, která ukazuje na složku obsahující soubory, které chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

> Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou k vaší zdrojové složce.

## Krok 2: přidání souborů do tar a vytvoření TarBz2 archivu

Třída `TarArchive` představuje tar kontejner v paměti, zatímco `Bzip2Archive` komprimuje streamy pomocí algoritmu Bzip2.  
Metoda `CreateEntry` přidá nový souborový záznam do tar archivu.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **přidává soubory do tar** – můžete tuto metodu volat pro každý soubor, který potřebujete v archivu.  
- `bz2.SetSource(archive)` říká archivu Bzip2, aby komprimoval celý tar stream.  
- `bz2.Save(...)` zapíše finální **TarBz2** soubor na disk.

**Tip:** Pro **hromadné přidání souborů do tar** jednoduše opakujte `archive.CreateEntry` pro každý soubor před voláním `bz2.Save`.

## Jak přidat soubory do tar?

Načtěte zdrojový adresář, vytvořte instanci `TarArchive`, přidejte každý soubor pomocí `CreateEntry`, poté zabalte tar stream do `Bzip2Archive` a zavolejte `Save`. Tento dvoukrokový vzor přidá libovolný počet souborů a vytvoří soubor `.tar.bz2` v jedné plynulé sekvenci, čímž eliminuje potřebu dočasných souborů nebo externích nástrojů.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Soubor nenalezen** chyba | Špatná cesta `dataDir` nebo chybějící přípona souboru | Ověřte úplnou cestu a ujistěte se, že soubor existuje. |
| **Prázdný archiv** | Žádné položky nebyly přidány před `bz2.Save` | Přidejte alespoň jedno volání `CreateEntry`. |
| **Přístup odmítnut** | Aplikace nemá oprávnění k zápisu do výstupní složky | Spusťte aplikaci s odpovídajícími právy nebo vyberte zapisovatelný adresář. |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET aplikacemi?**  
A: Ano. Funguje s .NET Framework, .NET Core, .NET 5/6 a novějšími runtime.

**Q: Mohu komprimovat více souborů současně?**  
A: Rozhodně. Zavolejte `CreateEntry` pro každý soubor před uložením archivu.

**Q: Kde mohu najít další dokumentaci?**  
A: Podrobné dokumenty jsou k dispozici v **Aspose.Zip .NET API reference**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Jak získám dočasnou licenci pro Aspose.Zip?**  
A: Můžete **požádat o dočasnou licenci** zde: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, **stáhněte si zkušební verzi z Aspose releases**: [download a trial version](https://releases.aspose.com/).

Můžete také [stáhnout zkušební verzi](https://releases.aspose.com/).

## Závěr

Nyní víte **jak vytvořit tar archiv**, komprimovat tar stream pomocí Bzip2 a vytvořit **TarBz2** archiv pomocí Aspose.Zip pro .NET. Tento přístup je rychlý, paměťově úsporný a funguje na všech moderních .NET platformách. Klidně experimentujte s většími sadami souborů, vlastními názvy položek nebo integrujte kód do vlastních zálohovacích či nasazovacích pipeline.

Pokud narazíte na jakékoli potíže, komunita Aspose.Zip je připravena pomoci – stačí navštívit **Aspose.Zip support forum**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Poslední aktualizace:** 2026-10-31  
**Testováno s:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

## Související tutoriály

- [Vytvořit tar archiv a přidat soubory do tar pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Přidat soubory do tar a vytvořit tarxz archiv pomocí Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Přidat soubory do tar a komprimovat do TarZ pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}