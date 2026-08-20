---
date: 2026-08-07
description: Naučte se, jak přidat soubory do tar a vytvořit archiv TarBz2 v .NET
  pomocí Aspose.Zip. Průvodce krok za krokem ukazuje tvorbu tar, kompresi Bzip2 a
  tipy na osvědčené postupy.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Komprese do TarBz2
og_description: Přidat soubory do tar a vytvořit archiv TarBz2 v .NET pomocí Aspose.Zip.
  Tento průvodce zahrnuje tvorbu tar, kompresi Bzip2 a tipy na řešení problémů.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Přidat soubory do tar a vytvořit archiv TarBz2 pomocí Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
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
title: Přidat soubory do tar a vytvořit archiv TarBz2 pomocí Aspose.Zip
url: /cs/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a vytvoření archivu TarBz2 pomocí Aspose.Zip

V tomto tutoriálu se dozvíte **jak přidat soubory do tar** archivů a převést je na kompaktní soubor **TarBz2** pomocí knihovny **Aspose.Zip** pro .NET. Ať už vytváříte nástroj pro zálohování, publikujete nasazovací balíčky, nebo potřebujete lehký balík pro distribuci, níže uvedené kroky vás provedou přidáním souborů do tar kontejneru, aplikací komprese Bzip2 a vytvořením připraveného k sdílení archivu.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip for .NET  
- **Jak dlouho trvá implementace?** About 5‑10 minutes  
- **Potřebuji licenci?** A temporary license is required for production; a free trial is available  
- **Mohu komprimovat více souborů?** Yes – add as many entries as you like to the tar archive  
- **Je kompatibilní s .NET 6+?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## Co je archiv TarBz2?

Soubor TarBz2 kombinuje tradiční kontejner **tar** (který zachovává strukturu adresářů a metadata souborů) s kompresí **Bzip2**, což vede k vysoce komprimovanému balíčku `.tar.bz2`. Tento formát je populární na Unix‑podobných systémech, protože nabízí dobrý poměr mezi kompresním poměrem a rychlostí dekomprese.

## Proč komprimovat soubory do TarBz2 pomocí Aspose.Zip?

Aspose.Zip může vytvořit archiv TarBz2 pomocí **dvou volání API**, přičemž efektivně pracuje se streamy. Podporuje **více než 50 formátů archivů a komprese**, zpracovává soubory až do **2 GB** bez načítání celého archivu do paměti a běží na .NET runtime pro Windows, Linux a macOS. Knihovna vám také poskytuje detailní kontrolu nad názvy položek, časovými razítky a úrovněmi komprese, což ji činí ideální pro konzolové nástroje i webové služby.

## Požadavky

- **Aspose.Zip for .NET** – stáhněte nejnovější balíček z oficiálního webu: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – složka, která obsahuje soubory, které chcete archivovat. V příkladech na ni odkazujeme proměnnou `dataDir`.

> **Tip:** Uchovávejte své zdrojové soubory v samostatné složce, aby nedošlo k neúmyslnému zahrnutí nežádoucích souborů.

## Importovat jmenné prostory

Nejprve importujte požadované jmenné prostory, abyste mohli přistupovat ke třídám Tar a Bzip2 z Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Krok 1: nastavit adresář dokumentů

Definujte cestu, která ukazuje na složku obsahující soubory, které chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

> Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou k vaší zdrojové složce.

## Krok 2: přidat soubory do tar a vytvořit archiv TarBz2

`TarArchive` představuje v‑paměti tar kontejner, který může obsahovat více souborových položek.  
`Bzip2Archive` komprimuje stream pomocí algoritmu Bzip2.  
Metoda `CreateEntry` přidá soubor do tar archivu jako novou položku.

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
- `bz2.Save(...)` zapíše finální soubor **TarBz2** na disk.

**Tip:** Pro **přidání souborů do tar** hromadně stačí opakovat `archive.CreateEntry` pro každý soubor před voláním `bz2.Save`.

## Jak přidat soubory do tar?

Načtěte zdrojový adresář, vytvořte instanci `TarArchive`, přidejte každý soubor pomocí `CreateEntry`, poté zabalte tar stream do `Bzip2Archive` a zavolejte `Save`. Tento dvoustupňový vzor přidá libovolný počet souborů a vytvoří soubor `.tar.bz2` v jedné plynulé sekvenci, čímž eliminuje potřebu dočasných souborů nebo externích nástrojů.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Soubor nebyl nalezen** error | Špatná cesta `dataDir` nebo chybějící přípona souboru | Ověřte úplnou cestu a ujistěte se, že soubor existuje. |
| **Prázdný archiv** | Žádné položky nebyly přidány před `bz2.Save` | Přidejte alespoň jedno volání `CreateEntry`. |
| **Přístup odmítnut** | Aplikace nemá oprávnění zápisu do výstupní složky | Spusťte aplikaci s příslušnými právy nebo vyberte zapisovatelný adresář. |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET aplikacemi?**  
A: Ano. Funguje s .NET Framework, .NET Core, .NET 5/6 a novějšími runtime.

**Q: Mohu komprimovat více souborů najednou?**  
A: Rozhodně. Zavolejte `CreateEntry` pro každý soubor před uložením archivu.

**Q: Kde mohu najít další dokumentaci?**  
A: Podrobné dokumenty jsou k dispozici v **Aspose.Zip .NET API reference**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Jak získám dočasnou licenci pro Aspose.Zip?**  
A: Můžete **požádat o dočasnou licenci** zde: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, **stáhněte si zkušební verzi z Aspose releases**: [download a trial version](https://releases.aspose.com/).

## Závěr

Nyní víte **jak přidat soubory do tar**, komprimovat tar stream pomocí Bzip2 a vytvořit archiv **TarBz2** pomocí Aspose.Zip pro .NET. Tento přístup je rychlý, paměťově úsporný a funguje na všech moderních .NET platformách. Klidně experimentujte s většími sadami souborů, vlastními názvy položek nebo integrujte kód do vlastních zálohovacích či nasazovacích pipeline.

Pokud narazíte na nějaké potíže, komunita Aspose.Zip je připravena pomoci – stačí přejít na **Aspose.Zip support forum**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Poslední aktualizace:** 2026-08-07  
**Testováno s:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvořit tar archiv a přidat soubory do tar pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Přidat soubory do tar a vytvořit archiv tarxz pomocí Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Přidat soubory do tar a komprimovat do TarZ pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}