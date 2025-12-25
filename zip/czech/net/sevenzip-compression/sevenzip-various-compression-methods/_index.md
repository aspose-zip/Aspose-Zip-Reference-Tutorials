---
date: 2025-12-25
description: Naučte se, jak vytvářet soubory 7z pomocí Aspose.Zip pro .NET, zahrnující
  sedm metod komprese zip, jako jsou LZMA2, BZip2 a Store. Ideální pro scénáře komprese
  složky do formátu 7z.
linktitle: SevenZip with Various Compression Methods
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak vytvořit soubory 7z – Tutoriál Aspose.Zip pro .NET
url: /cs/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit soubory 7z – tutoriál Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **jak vytvořit 7z** archivy programově v aplikaci .NET, jste na správném místě. Aspose.Zip pro .NET usnadňuje generování Seven Zip archivů s libovolným z podporovaných kompresních algoritmů, ať už chcete **komprimovat složku do 7z** pro distribuci nebo jen spolehlivé **seven zip archive .net** řešení. V tomto průvodci projdeme tři oblíbené kompresní metody – LZMA2, BZip2 a Store (bez komprese) – a ukážeme vám, jak vytvořit 7z soubor během několika řádků C# kódu.

## Rychlé odpovědi
- **Jakou knihovnu použít?** Aspose.Zip pro .NET poskytuje nejkompletnější sadu funkcí Seven Zip.  
- **Která kompresní metoda dává nejlepší poměr?** LZMA2 obvykle poskytuje nejvyšší kompresi pro smíšená data.  
- **Mohu vytvořit 7z bez jakékoli komprese?** Ano – použijte metodu Store (bez komprese).  
- **Potřebuji licenci pro vývoj?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Je to kompatibilní s .NET 6/7?** Naprosto – Aspose.Zip podporuje .NET Framework, .NET Core i .NET 5+.

## Jaké jsou kompresní metody Seven Zip?

Seven Zip podporuje několik algoritmů, z nichž každý je optimalizován pro jiné scénáře:

* **LZMA2** – vysoký kompresní poměr, ideální pro velké soubory smíšených typů.  
* **BZip2** – solidní komprese, ale pomalejší než LZMA2; užitečná, když je vyžadována kompatibilita se staršími nástroji.  
* **Store** – žádná komprese; perfektní, když potřebujete jen archivaci bez zmenšení velikosti (např. při zachování původních časových razítek souborů).

Porozumění těmto **seven zip compression methods** vám pomůže vybrat správné nastavení pro váš projekt.

## Předpoklady

Než se pustíme dál, ujistěte se, že máte:

- Základní znalosti C# a Visual Studia.  
- Nainstalovanou knihovnu Aspose.Zip pro .NET. Stáhněte ji z oficiální stránky **[zde](https://releases.aspose.com/zip/net/)**.  
- Složku (`dataDir`) obsahující soubory, které chcete archivovat.

## Import jmenných prostorů

Nejprve přidejte požadované jmenné prostory do vašeho C# souboru:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Tyto třídy vám poskytují přístup k nastavením komprese a manipulaci s archivy.

## Komprese LZMA2 – Jak vytvořit 7z s maximálním poměrem

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Tip:** LZMA2 funguje nejlépe, když jsou zdrojové soubory větší než 1 MB. Pro mnoho malých souborů může být BZip2 rychlejší.

## Komprese BZip2 – Vyvážená volba

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 nabízí solidní kompresi při zachování rozumné rychlosti, což z něj dělá dobrý záložní řešení, když LZMA2 není podporováno cílovým prostředím.

## Store (bez komprese) – Když velikost není důležitá

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Použijte metodu Store, pokud potřebujete jen seskupit soubory dohromady bez změny jejich velikosti – ideální pro zachování původních časových razítek nebo když bude archiv rozbalen za běhu.

## Běžné případy použití

| Scénář | Doporučená metoda |
|----------|--------------------|
| Distribuce velkých instalátorů | LZMA2 |
| Sdílení logů se staršími nástroji | BZip2 |
| Balíček souborů pro rychlé rozbalení | Store (bez komprese) |
| Potřeba **komprimovat složku do 7z** za běhu ve webové službě | LZMA2 (pro nejlepší poměr) |

## Řešení problémů a tipy

- **Chybějící soubory v archivu?** Ověřte, že `dataDir` ukazuje na správný adresář a že proces má oprávnění ke čtení.  
- **Archiv se nepodaří otevřít ve starších verzích 7‑Zip?** Držte se BZip2 nebo Store, protože LZMA2 může vyžadovat novější dekompresní knihovny.  
- **Úzké hrdlo výkonu?** Pro masivní datové sady zvažte streamování archivu místo načítání všech položek do paměti.

## Často kladené otázky

**Q: Mohu použít Aspose.Zip pro .NET s jakýmkoli typem souboru?**  
A: Ano, Aspose.Zip podporuje širokou škálu formátů souborů, což vám umožní komprimovat a dekomprimovat prakticky jakýkoli typ souboru.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Zip pro .NET?**  
A: Ano, bezplatnou zkušební verzi získáte **[zde](https://releases.aspose.com/)**.

**Q: Kde najdu dokumentaci pro Aspose.Zip pro .NET?**  
A: Kompletní referenci API najdete **[zde](https://reference.aspose.com/zip/net/)**.

**Q: Jak získat dočasné licence pro Aspose.Zip pro .NET?**  
A: Dočasné licence lze získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Kde mohu získat podporu pro Aspose.Zip pro .NET?**  
A: Podporu můžete hledat na **[fóru Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Poslední aktualizace:** 2025-12-25  
**Testováno s:** Aspose.Zip pro .NET 24.12  
**Autor:** Aspose  

---