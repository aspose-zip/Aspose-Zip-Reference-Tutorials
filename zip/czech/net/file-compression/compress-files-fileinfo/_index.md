---
date: 2026-07-18
description: Naučte se, jak přidat složku do ZIP a přidat soubory do ZIP pomocí Aspose.Zip
  pro .NET. Tento podrobný návod ukazuje, jak komprimovat soubory pomocí FileInfo
  v projektech ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Komprimování souborů pomocí FileInfo
og_description: Přidání složky do ZIP pomocí Aspose.Zip pro .NET. Naučte se, jak vytvořit
  ZIP archiv, přidat soubory do ZIP a efektivně komprimovat složky v ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Přidání složky do ZIP – Komprimování souborů s Aspose.Zip pro .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Přidání složky do ZIP pomocí Aspose.Zip pro .NET – Komprimování souborů pomocí
  FileInfo
url: /cs/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání složky do zipu pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **přidat složku do zipu** programově, Aspose.Zip pro .NET nabízí čisté, vysoce výkonné API, které funguje v jakékoli .NET (včetně ASP.NET) aplikaci. V tomto tutoriálu projdeme kompresi souborů pomocí třídy `FileInfo`, ukážeme vám, jak **přidat soubory do zipu**, a vysvětlíme, proč je tento přístup ideální pro moderní .NET projekty. Také se podíváme na přesné kroky k **přidání složky do zipu**, abyste mohli zabalit celé adresáře jedním operací. Pojďme na to!

## Rychlé odpovědi
- **Jaký je nejjednodušší způsob, jak vytvořit zip archiv?** Použijte třídu `Archive` z Aspose.Zip spolu s objekty `FileInfo`.  
- **Mohu přidat více souborů najednou?** Ano – stačí vytvořit `FileInfo` pro každý soubor a zavolat `CreateEntry`.  
- **Potřebuji speciální licenci pro ASP.NET?** Pro produkční nasazení je vyžadována komerční licence Aspose.Zip; pro hodnocení stačí bezplatná zkušební verze.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 a .NET 5–10.  
- **Je API thread‑safe?** Ano, pokud každý vlákno pracuje se svou vlastní instancí `Archive`.

## Co je zip archiv a proč jej vytvořit?
Zip archiv slouží ke spojení jednoho nebo více souborů do jediného komprimovaného kontejneru. To šetří úložný prostor, urychluje přenosy po síti a zjednodušuje distribuci. Ať už doručujete logy, exportujete zprávy nebo balíte zdroje pro klienta, schopnost **vytvořit zip archiv** programově je cenná dovednost pro každého .NET vývojáře.

## Proč použít Aspose.Zip pro přidání souborů do zipu?
Aspose.Zip poskytuje čisté .NET řešení, které eliminuje externí závislosti a zároveň vývojářům dává detailní kontrolu nad kompresí, kódováním a zabezpečením. Podporuje velké soubory, ochranu heslem a funguje konzistentně napříč všemi podporovanými verzemi .NET, což z něj činí spolehlivou volbu jak pro starší, tak pro moderní aplikace.  

- **Žádné externí závislosti** – čistá .NET implementace.  
- **Plná kontrola nad úrovní komprese a kódováním** (ASCII, UTF‑8, atd.).  
- **Podporuje soubory větší než 4 GB** a ochranu heslem.  
- **Konzistentní API napříč více než 50 verzemi .NET** – od .NET Framework 2.0 až po .NET 10.  

## Požadavky

Předtím, než se ponoříme do kódu, ujistěte se, že máte:

1. **Aspose.Zip pro .NET** nainstalovaný. Stáhněte nejnovější balíček z [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Složku na vašem počítači obsahující soubory, které chcete komprimovat (např. `alice29.txt` a `fields.c`).  

## Importování jmenných prostorů

V libovolném C# souboru, kde budete pracovat se zip archivy, přidejte následující `using` direktivy:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Tyto jmenné prostory vám poskytují přístup ke třídě `Archive`, možnostem ukládání a standardním I/O utilitám.

## Postupný průvodce

### Krok 1: Nastavte adresář dokumentu

Nejprve definujte složku, která obsahuje zdrojové soubory. Nahraďte zástupný text absolutní nebo relativní cestou ve vašem systému:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Použijte `Path.Combine` k sestavení cest platformově nezávislým způsobem.

### Krok 2: Otevřete zip soubor pro zápis

Vytvořte `FileStream`, který ukazuje na výstupní zip soubor. Proud je otevřen v režimu **Create**, který přepíše jakýkoli existující soubor se stejným názvem:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Krok 3: Připravte objekty `FileInfo` pro každý zdrojový soubor

`FileInfo` poskytuje Aspose.Zip přímý přístup k fyzickým souborům na disku. Vytvořte jednu instanci pro každý soubor, který chcete komprimovat:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Proč používat `FileInfo`?** Zabraňuje načítání celého souboru do paměti, což je zvláště užitečné u velkých souborů.

### Krok 4: Vytvořte archiv a přidejte položky

Třída `Archive` je jádrem Aspose.Zip, představuje zip kontejner v paměti. Vytvořte instanci `Archive` a poté pro každý `FileInfo` zavolejte `CreateEntry`. První argument je název, pod kterým bude soubor uvnitř zipu, druhý argument je zdrojový `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

Metoda `CreateEntry` přidá nový souborový záznam do archivu, propojí název záznamu se zdrojovým `FileInfo`, takže data jsou při ukládání archivu streamována přímo z disku.

### Krok 5: Uložte zip archiv s požadovaným kódováním

Nakonec uložte archiv do `FileStream`, který jste otevřeli dříve. Zde používáme ASCII kódování pro názvy položek, ale můžete přepnout na UTF‑8, pokud vaše názvy souborů obsahují ne‑ASCII znaky:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Když se ukončí bloky `using`, proudy se automaticky uzavřou a zip soubor je připraven k použití.

## Jak přidat složku do zipu pomocí Aspose.Zip?

Načtěte cílový adresář, enumerujte všechny soubory a přidejte každý s relativní cestou, která zahrnuje název složky. Tento přístup vám umožní **přidat složku do zipu** bez ručního výčtu každého souboru. Zachováním hierarchie složek v názvech položek může být výsledný archiv rozbalen se zachovanou původní strukturou, což je nezbytné pro mnoho nasazovacích scénářů.

1. Použijte `DirectoryInfo` k určení složky, kterou chcete komprimovat.  
2. Zavolejte `GetFiles("*", SearchOption.AllDirectories)`, abyste rekurzivně získali všechny soubory.  
3. Pro každý soubor vytvořte `FileInfo` a zavolejte `CreateEntry` s cestou jako `"MyFolder/Report.pdf"`.  

Protože API pracuje s `FileInfo`, každý soubor je streamován přímo z disku, což udržuje nízkou spotřebu paměti i u složek obsahujících stovky megabajtů.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| **Prázdný zip soubor** | `FileInfo` ukazuje na neexistující cestu | Ověřte `dataDir` a názvy souborů; použijte `File.Exists` k kontrole před vytvořením položek. |
| **Nesprávné kódování názvu souboru** | Použití výchozího kódování s ne‑ASCII názvy | Nastavte `Encoding = Encoding.UTF8` v `ArchiveSaveOptions`. |
| **OutOfMemoryException u velkých souborů** | Načítání celého souboru do paměti | `FileInfo` streamuje soubor; ujistěte se, že jinde soubor nečtete do pole bajtů. |
| **Přístup odepřen** | Aplikace nemá oprávnění zapisovat do výstupní složky | Spusťte aplikaci s potřebnými právy nebo zvolte zapisovatelný adresář. |

## Často kladené otázky

**Q: Mohu přidat celou složku do zip archivu jedním voláním?**  
A: Neexistuje metoda jedním voláním, ale enumerace souborů pomocí `DirectoryInfo` a přidání každého přes `CreateEntry` dosáhne stejného výsledku efektivně.

**Q: Podporuje Aspose.Zip ochranu heslem?**  
A: Ano, můžete nastavit heslo na objekt `Archive` před uložením, čímž zašifrujete celý archiv.

**Q: Jak velký zip soubor Aspose.Zip zvládne?**  
A: Knihovna zpracovává soubory větší než 4 GB a může vytvořit archivy přesahující 10 GB, aniž by načítala celý archiv do paměti.

**Q: Je API kompatibilní s .NET 6 a .NET 8?**  
A: Rozhodně. Aspose.Zip podporuje .NET 5 až .NET 10, což zahrnuje všechny současné LTS verze.

**Q: Jaké úrovně komprese jsou k dispozici?**  
A: Můžete zvolit `CompressionLevel.NoCompression`, `Fast`, `Normal` nebo `Maximum` podle požadovaného poměru rychlosti a velikosti.

## Další zdroje

- Stáhněte nejnovější Aspose.Zip balíček: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Zakupte licenci pro produkční použití: [purchase page](https://purchase.aspose.com/buy)  
- Získejte pomoc od komunity: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Vyzkoušejte Aspose.Zip zdarma: [free trial here](https://releases.aspose.com/)  
- Získejte dočasnou licenci pro hodnocení: [this link](https://purchase.aspose.com/temporary-license/)

## Závěr

Nyní víte, **jak přidat složku do zipu** a **jak vytvořit zip archiv** pomocí Aspose.Zip pro .NET, jak **přidat soubory do zipu** a proč je tento postup ideální pro ASP.NET a další .NET aplikace. Experimentujte s různými úrovněmi komprese, kódováními a možnostmi šifrování, abyste archiv přizpůsobili přesně svým potřebám. Šťastnou kompresi!

---

**Poslední aktualizace:** 2026-07-18  
**Testováno s:** Aspose.Zip for .NET 24.12 (latest)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak zkomprimovat složku pomocí Aspose.Zip pro .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Snadná komprese s Aspose.Zip pro .NET](/zip/net/file-compression/compress-multiple-files/)
- [Vytvořit Zip archiv .NET – Komprese souborů s Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}