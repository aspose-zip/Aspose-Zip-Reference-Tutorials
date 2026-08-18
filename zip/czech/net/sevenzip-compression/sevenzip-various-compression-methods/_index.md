---
date: 2026-06-29
description: Naučte se, jak komprimovat složku do 7z pomocí Aspose.Zip pro .NET, zahrnující
  metody komprese Seven Zip jako LZMA2, BZip2 a Store. Ideální pro programové vytváření
  archivů 7z.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip s různými metodami komprese
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat složku do 7z – tutoriál Aspose.Zip pro .NET
url: /cs/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat složku do 7z – Aspose.Zip pro .NET tutoriál

## Úvod

Pokud potřebujete **komprimovat složku do 7z** archivů programově v aplikaci .NET, jste na správném místě. Aspose.Zip pro .NET usnadňuje generování Seven Zip archivů s jakýmkoli z podporovaných kompresních algoritmů, ať už chcete zabalit celý adresář pro distribuci nebo jen potřebujete spolehlivé **seven zip archive .net** řešení. V tomto průvodci projdeme tři oblíbené kompresní metody — LZMA2, BZip2 a Store (bez komprese) — a ukážeme vám přesně, jak vytvořit soubor 7z během několika řádků C# kódu.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip pro .NET poskytuje nejkompletnější sadu funkcí Seven Zip.  
- **Která kompresní metoda dává nejlepší poměr?** LZMA2 obvykle poskytuje nejvyšší kompresi pro smíšená data.  
- **Mohu vytvořit 7z bez jakékoli komprese?** Ano — použijte metodu Store (bez komprese).  
- **Potřebuji licenci pro vývoj?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Je to kompatibilní s .NET 6/7?** Rozhodně — Aspose.Zip podporuje .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 a .NET 5–10.

## Jaké jsou kompresní metody Seven Zip?

Seven Zip podporuje několik algoritmů, z nichž každý je optimalizován pro jiné scénáře. **LZMA2** nabízí nejvyšší kompresní poměr (často o 30‑40 % menší než BZip2), **BZip2** poskytuje solidní kompresi s širší podporou starších nástrojů a **Store** jednoduše archivuje soubory bez jejich zmenšování, přičemž perfektně zachovává původní časová razítka.

## Předpoklady

Než se pustíme dál, ujistěte se, že máte:

- Základní znalosti C# a Visual Studio.  
- Knihovnu Aspose.Zip pro .NET nainstalovanou. Stáhněte ji z oficiální stránky **[zde](https://releases.aspose.com/zip/net/)**.  
- Složku (`dataDir`) obsahující soubory, které chcete archivovat.

## Import Namespaces

Nejprve přidejte požadované jmenné prostory do vašeho C# souboru:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Tyto třídy vám umožní přístup k nastavením komprese a manipulaci s archivy.

## LZMA2 Compression – Jak vytvořit 7z s maximálním poměrem

Třída `Archive` představuje 7z archiv, který může obsahovat více souborů.  
Algoritmus LZMA2 poskytuje nejvyšší kompresní poměr mezi podporovanými metodami. Pracuje tak, že vstup rozdělí do bloků a použije sofistikovanou kompresi slovníku. V Aspose.Zip nastavíte `CompressionMethod` na `CompressionMethod.Lzma2` na objektu `Archive` před přidáním souborů.

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

## BZip2 Compression – Vyvážená volba

Třída `Archive` představuje 7z archiv, který může obsahovat více souborů.  
BZip2 nabízí solidní kompresi s dobrou kompatibilitou pro starší nástroje. Používá transformaci Burrows‑Wheeler a Huffmanovo kódování ke snížení velikosti. V Aspose.Zip vyberete `CompressionMethod.BZip2` při konfiguraci instance `Archive`, což vyvažuje rychlost a kompresní poměr pro většinu textových a binárních souborů.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 poskytuje solidní kompresi při zachování rozumné rychlosti, což z něj činí dobrý fallback, když LZMA2 není podporována cílovým prostředím.

## Store (Bez komprese) – Když velikost není důležitá

Třída `Archive` představuje 7z archiv, který může obsahovat více souborů.  
Metoda Store vytváří archiv bez komprese dat. Jednoduše zkopíruje původní soubory do kontejneru 7z, zachovává časová razítka a strukturu adresářů. Pro použití v Aspose.Zip nastavte `CompressionMethod.Store` na `Archive` před přidáním souborů, které chcete zabalit.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Použijte metodu Store, pokud potřebujete jen sloučit soubory dohromady bez změny jejich velikosti — ideální pro zachování původních časových razítek nebo když bude archiv rozbalován za běhu.

## Jak přidat soubory do 7z?

Přidejte soubory do 7z archivu vytvořením instance `Archive`, nastavením požadované `CompressionMethod` a voláním `AddAllFiles(dataDir)`. Metoda rekurzivně prohledá zadanou složku a zachová hierarchii adresářů uvnitř archivu. Tento přístup vám umožní **komprimovat složku do 7z** jedním řádkem kódu po úvodním nastavení.

## Běžné scénáře použití

| Scénář | Doporučená metoda |
|----------|--------------------|
| Distribuovat velké instalátory | LZMA2 |
| Sdílet logy se staršími nástroji | BZip2 |
| Zabalit soubory pro rychlé rozbalení | Store (bez komprese) |
| Potřebujete **komprimovat složku do 7z** za běhu ve webové službě | LZMA2 (pro nejlepší poměr) |

## Řešení problémů a tipy

- **Chybějící soubory v archivu?** Ověřte, že `dataDir` ukazuje na správný adresář a že proces má oprávnění ke čtení.  
- **Archiv se neotevírá ve starších verzích 7‑Zip?** Držte se BZip2 nebo Store, protože LZMA2 může vyžadovat novější dekompresní knihovny.  
- **Úzké hrdlo výkonu?** Pro masivní datové sady zvažte streamování archivu místo načítání všech položek do paměti.

## Často kladené otázky

**Q: Mohu použít Aspose.Zip pro .NET s jakýmkoli typem souboru?**  
A: Ano, Aspose.Zip podporuje širokou škálu formátů souborů, což vám umožní komprimovat a dekomprimovat prakticky jakýkoli typ souboru.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Zip pro .NET?**  
A: Ano, bezplatnou zkušební verzi získáte **[zde](https://releases.aspose.com/)**.

**Q: Kde najdu dokumentaci k Aspose.Zip pro .NET?**  
A: Kompletní reference API je dostupná **[zde](https://reference.aspose.com/zip/net/)**.

**Q: Jak získat dočasné licence pro Aspose.Zip pro .NET?**  
A: Dočasné licence lze získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Kde mohu získat podporu pro Aspose.Zip pro .NET?**  
A: Podporu můžete hledat na **[fóru Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

---

**Poslední aktualizace:** 2026-06-29  
**Testováno s:** Aspose.Zip pro .NET 24.12  
**Autor:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [compress files c# – Create 7z archive with Aspose.Zip for .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [How to Zip Folder Using Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [How to Compress LZMA in Aspose.Zip for .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}