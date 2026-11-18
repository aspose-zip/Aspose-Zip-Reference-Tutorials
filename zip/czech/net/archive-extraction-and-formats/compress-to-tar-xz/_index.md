---
date: 2026-11-18
description: Zjistěte, jak přidat soubory do tar a komprimovat soubory do archivu
  tarxz v .NET pomocí Aspose.Zip. Postupujte podle tohoto průvodce krok za krokem
  pro efektivní ukládání a přenos.
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: Komprese do TarXz
og_description: Přidejte soubory do tar a vytvořte archiv tarxz pomocí Aspose.Zip.
  Naučte se rychle komprimovat soubory do TarXz v .NET s vysokou účinností komprese
  a multiplatformní kompatibilitou.
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: Přidání souborů do tar a vytvoření archivu tarxz pomocí Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: Přidání souborů do tar a vytvoření archivu tarxz pomocí Aspose.Zip
url: /cs/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a vytvoření tarxz archivu pomocí Aspose.Zip

## Úvod

Pokud potřebujete **add files to tar** a poté **create a tarxz archive .net**, Aspose.Zip pro .NET usnadňuje a zpřehledňuje celý proces. Ať už balíte logy, konfigurační soubory nebo jakékoli jiné zdroje pro ukládání či přenos, komprese do formátu TarXz vám poskytne vysoký kompresní poměr při zachování známé struktury tar. V tomto tutoriálu projdeme přesné kroky – včetně úryvků kódu – abyste mohli integraci tvorby tarxz do svých .NET aplikací provést s jistotou. Na konci pochopíte, proč je “add files to tar” prvním krokem k vytvoření kompaktního, multiplatformního balíčku.

## Rychlé odpovědi
- **Jaká je hlavní třída?** `TarArchive` from `Aspose.Zip.Tar`
- **Jak komprimuji do tarxz?** Call `SaveXzCompressed` after adding entries
- **Které verze .NET jsou podporovány?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
- **Potřebuji licenci?** Yes, a valid Aspose.Zip license is required for production use
- **Doba implementace?** Roughly 5‑10 minutes for a basic archive

## Co je TarXz archiv?

TarXz archiv kombinuje tradiční unixový kontejner `tar` s XZ kompresí. Část tar sbaluje více souborů do jednoho proudu, zatímco XZ poskytuje silnou, bezztrátovou kompresi. Tento formát je populární pro distribuci zdrojového kódu, záloh a velkých datových sad, protože zachovává adresářové struktury a dosahuje menších velikostí souborů než čistý tar nebo zip.

## Proč vytvářet tarxz archiv .net pomocí Aspose.Zip?

Vytvoření TarXz archivu s Aspose.Zip poskytuje rychlé, jednoprosté řešení bez externích nástrojů. Soubory jsou o 30‑50 % menší než gzip a můžete přímo v .NET pracovat s více než 20 formáty archivů. Knihovna zpracovává velké archivy, aniž by načítala celý soubor do paměti, což ji činí ideální pro cloudové služby a CI pipeline. Podporuje také více než 50 vstupních a výstupních formátů.

## Požadavky

Před zahájením se ujistěte, že máte:

- **Aspose.Zip for .NET** nainstalovaný (stáhněte z oficiální [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Složku obsahující soubory, které chcete archivovat. V níže uvedených příkladech je tato složka odkazována proměnnou `dataDir`.  
- Platnou Aspose.Zip licenci (volitelně pro hodnocení, povinně pro produkci).

## Importovat jmenné prostory

Stačí importovat jen ty jmenné prostory, které zpřístupňují funkčnost TarXz. Žádné další balíčky nejsou potřeba nad rámec jádra knihovny Aspose.Zip.

## Jak přidat soubory do tar pomocí Aspose.Zip

`TarArchive` je třída, která v Aspose.Zip představuje tar kontejner. Souborům přidáváte do tar archivu vytvořením instance `TarArchive` a následným voláním metody `AddEntry` pro každý soubor, který chcete zahrnout, s určením zdrojové cesty a volitelného názvu položky. Archiv vytváří tar kontejner v paměti, připravený pro následnou XZ kompresi.

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Tip:** `using` blok zajišťuje, že archiv je řádně uvolněn, čímž se uvolní všechny neřízené prostředky.

### Krok 1: inicializovat `TarArchive`

Vytvořte objekt `TarArchive` uvnitř `using` bloku, aby byly všechny neřízené prostředky automaticky uvolněny po dokončení operace.

```csharp
using (TarArchive archive = new TarArchive())
{
```

### Krok 2: přidat soubory do archivu

Přidejte každý soubor, který chcete zahrnout. V tomto příkladu přidáváme dva textové soubory, ale můžete přidat libovolný počet položek. Metoda `AddEntry` přijímá úplnou cestu k souboru a volitelný název položky, který se objeví uvnitř taru.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Proč je to důležité:** Přidání položek před kompresí umožňuje Aspose.Zip nejprve vytvořit tar kontejner a pak v jednom kroku aplikovat XZ kompresi.

### Krok 3: uložit archiv s XZ kompresí

Metoda `SaveXzCompressed` zapíše tar archiv do souboru a zároveň provede XZ kompresi v jednom kroku, čímž vznikne soubor `.tar.xz` připravený k distribuci.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Výsledek:** Nyní máte plně komprimovaný soubor `archive.tar.xz`, který lze přenášet, ukládat nebo rozbalovat na jakékoli platformě podporující TarXz.

## Jak komprimovat tarxz soubory pomocí Aspose.Zip

Komprese do tarxz s Aspose.Zip je dvoukrokový proces zabalený do jednoho volání metody: nejprve **add files to tar**, poté zavoláte `SaveXzCompressed`. Tím se eliminuje potřeba externích nástrojů příkazové řádky a celý workflow zůstane uvnitř vašeho .NET kódu.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **“File not found” exception** | Incorrect `dataDir` path | Verify the directory path ends with a backslash (`\`) or use `Path.Combine`. |
| **Large memory usage** | Very large files being compressed in memory | Use `TarArchive` in streaming mode (`SaveXzCompressed` overload that accepts a `Stream`). |
| **License not applied** | Missing license file | Load the license at application start: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET prostředími?**  
A: Ano, Aspose.Zip funguje s .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 a .NET 5–10. Viz [documentation](https://reference.aspose.com/zip/net/) pro podrobnosti.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Zip?**  
A: Dočasnou licenci můžete požádat na [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**Q: Existují další příklady pro jiné formáty archivů?**  
A: Rozhodně – prozkoumejte kompletní sadu příkladů v [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: Kde mohu získat pomoc nebo diskutovat o problémech?**  
A: Připojte se k diskuzi na [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) pro komunitní podporu a oficiální odpovědi.

**Q: Mohu vyzkoušet Aspose.Zip zdarma před zakoupením?**  
A: Ano, bezplatná zkušební verze je k dispozici na [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## Závěr

Postupem podle výše uvedených kroků nyní víte, **jak přidat soubory do tar** a **komprimovat tarxz** soubory, a co je ještě důležitější, **jak vytvořit tarxz archiv .net** pomocí Aspose.Zip. Tento přístup vám poskytne kompaktní, přenosný balíček, který lze snadno integrovat do jakéhokoli .NET workflow – ať už vytváříte desktopovou utilitu, webovou službu nebo automatizovaný CI/CD pipeline.

---

**Last Updated:** 2026-11-18  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  



## Související tutoriály

- [Vytvořit tar archiv a přidat soubory do tar pomocí Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Jak komprimovat tar a vytvořit TarBz2 s Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Jak komprimovat více souborů tar s Aspose.Zip pro .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}