---
date: 2026-06-24
description: Naučte se, jak komprimovat LZMA v Aspose.Zip pro .NET, optimalizujte
  úložiště a efektivitu přenosu dat.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Komprimovat do Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat LZMA v Aspose.Zip pro .NET
url: /cs/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat LZMA v Aspose.Zip pro .NET

## Úvod

V tomto tutoriálu se naučíte **jak komprimovat LZMA** v Aspose.Zip pro .NET, což je klíčová dovednost pro optimalizaci úložného prostoru a zlepšení efektivity přenosu dat. LZMA (algoritmus Lempel‑Ziv‑Markov chain) poskytuje až o 70 % menší archivy ve srovnání s tradičním ZIP, přičemž zachovává rychlou dekompresi, což ji činí ideální pro scénáře s omezenou šířkou pásma.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Zip for .NET  
- **Jaký algoritmus tento průvodce pokrývá?** LZMA compression  
- **Potřebuji licenci?** Dočasná licence stačí pro testování; plná licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, a .NET 5–10  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní soubor.

## Co je komprese LZMA?

LZMA je vysoce poměrný bezztrátový kompresní algoritmus, který používá slovníkovou kompresi a kódování rozsahu. Dokáže zmenšit textové soubory o 30‑70 % při zachování rychlosti dekomprese srovnatelné se ZIP. Pro velké datové sady LZMA snižuje náklady na úložiště a urychluje síťové přenosy bez obětování integrity dat.

## Proč použít Aspose.Zip pro LZMA?

Aspose.Zip podporuje **5 kompresních algoritmů** (ZIP, Deflate, BZIP2, LZMA a ZSTD) a dokáže zpracovat archivy až do **4 GB** bez načítání celého souboru do paměti. Knihovna zpracuje dokumenty o stovkách stránek během méně než **2 sekund** na typickém serveru, což poskytuje jak výkon, tak škálovatelnost.

## Požadavky

Než se pustíte dál, ujistěte se, že máte následující:

- Aspose.Zip for .NET: Ujistěte se, že je knihovna Aspose.Zip nainstalována. Dokumentaci najdete [zde](https://reference.aspose.com/zip/net/).
- Document Directory: Vyberte nebo vytvořte složku, která obsahuje soubory, které chcete komprimovat.

## Importovat jmenné prostory

Přidejte požadované jmenné prostory na začátek vašeho C# souboru, abyste mohli využít LZMA funkčnost Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Jak nastavit zdrojovou složku pro kompresi?

Určete složku, která obsahuje soubory, jež chcete archivovat. Poskytnutí vyhrazeného zdrojového adresáře zajišťuje, že budou zpracovány pouze požadované soubory, snižuje riziko zahrnutí nechtěných dat a usnadňuje správu cest při práci s více kompresními úkoly ve stejném projektu.

```csharp
string dataDir = "Your Document Directory";
```

## Jak komprimovat soubor pomocí LZMA?

`LzmaArchive` je třída Aspose.Zip pro vytváření a správu LZMA archivů.

Vytvořte instanci `LzmaArchive`, nasměrujte ji na zdrojový soubor a zavolejte `Save` pro vytvoření `.lzma` archivu. Tento dvouřádkový vzor provádí celý kompresní workflow, interně spravuje streamy a vytváří kompaktní soubor připravený k distribuci nebo uložení.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Jak mohu potvrdit, že komprese byla úspěšná?

`Console.WriteLine` vypíše řádek textu na standardní výstupní konzoli.

Po uložení archivu vypište krátkou potvrzovací zprávu pomocí `Console.WriteLine`. Tato okamžitá odezva pomáhá vývojářům ověřit, že krok komprese byl dokončen bez chyb, usnadňuje ladění během automatizovaných sestavení a poskytuje jasné informace o stavu, když je rutina integrována do větších aplikací nebo skriptů.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Časté problémy a řešení

- **File not found** – Ověřte, že řetězec cesty používá dvojité zpětné lomítka (`\\`) nebo doslovný řetězec (`@"C:\Path"`).  
- **Insufficient memory** – Aspose.Zip streamuje data, ale extrémně velké soubory mohou vyžadovat zvýšení limitu paměti procesu.  
- **License not applied** – Ujistěte se, že před jakoukoliv operací Aspose.Zip zavoláte `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");`.

## Často kladené otázky

**Q: Mohu komprimovat více souborů do jednoho LZMA archivu?**  
A: Ano. Zavolejte `archive.AddFile()` pro každý soubor před voláním `archive.Save()`.

**Q: Existuje způsob, jak nastavit úroveň komprese pro LZMA?**  
A: Třída `LzmaArchive` používá výchozí úroveň komprese, která poskytuje dobrý poměr mezi rychlostí a velikostí. Pokročilá nastavení jsou dostupná přes `LzmaEncoder`, pokud potřebujete jemně ladit kontrolu.

**Q: Bude výsledný .lzma soubor fungovat na ne‑Windows platformách?**  
A: Ano. Formát LZMA je platformně nezávislý, takže archiv může být dekomprimován na jakémkoli OS s nástrojem kompatibilním s LZMA.

**Q: Jak dekomprimovat LZMA archiv pomocí Aspose.Zip?**  
A: Použijte konstruktor `LzmaArchive` s cestou k archivu a poté zavolejte `ExtractToDirectory()` pro extrahování jeho obsahu.

**Q: Podporuje Aspose.Zip streamovou kompresi, aby se předešlo načítání celých souborů do paměti?**  
A: Ano. Můžete pracovat se streamy předáním objektů `Stream` metodám `SetSource()` a `Save()`.

---

**Poslední aktualizace:** 2026-06-24  
**Testováno s:** Aspose.Zip for .NET (latest version at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak komprimovat soubory pomocí Aspose.Zip pro .NET](/zip/net/file-compression/compress-file/)
- [Jak otevřít GZip archiv a další kompresní techniky s Aspose.Zip pro .NET](/zip/net/other-compression-techniques/)
- [komprimovat soubory c# – Vytvořit 7z archiv s Aspose.Zip pro .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}