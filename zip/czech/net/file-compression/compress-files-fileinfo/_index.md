---
date: 2025-12-05
description: Naučte se, jak vytvořit zip archiv a přidávat soubory do zipu pomocí
  Aspose.Zip pro .NET. Tento krok‑za‑krokem průvodce ukazuje, jak komprimovat soubory
  pomocí FileInfo v projektech ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak vytvořit ZIP archiv pomocí Aspose.Zip pro .NET – Komprimovat soubory pomocí
  FileInfo
url: /cs/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit zip archiv pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **programově vytvořit zip archiv**, Aspose.Zip pro .NET vám poskytuje čisté, výkonné API, které funguje v jakékoli aplikaci .NET (včetně ASP.NET). V tomto tutoriálu vás provedeme kompresí souborů pomocí třídy `FileInfo`, ukážeme vám, jak **přidat soubory do zipu**, a vysvětlíme, proč je tento přístup ideální pro moderní .NET projekty. Pojďme na to!

## Rychlé odpovědi
- **Jaký je nejjednodušší způsob, jak vytvořit zip archiv?** Použijte třídu `Archive` z Aspose.Zip spolu s objekty `FileInfo`.  
- **Mohu najednou přidat více souborů?** Ano – stačí vytvořit `FileInfo` pro každý soubor a zavolat `CreateEntry`.  
- **Potřebuji speciální licenci pro ASP.NET?** Pro produkční nasazení je vyžadována komerční licence Aspose.Zip; pro hodnocení stačí bezplatná zkušební verze.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Je API thread‑safe?** Ano, pokud každé vlákno pracuje se svou vlastní instancí `Archive`.

## Co je zip archiv a proč jej vytvořit?
Zip archiv slouží ke spojení jednoho nebo více souborů do jediného komprimovaného kontejneru. To šetří úložný prostor, zrychluje přenosy po síti a zjednodušuje distribuci. Ať už doručujete logy, exportujete zprávy nebo balíte assety pro klienta, schopnost **programově vytvořit zip archiv** je cenná dovednost pro každého .NET vývojáře.

## Proč použít Aspose.Zip k přidání souborů do zipu?
- **Žádné externí závislosti** – čistá .NET implementace.  
- **Plná kontrola nad úrovní komprese a kódováním** (ASCII, UTF‑8, atd.).  
- **Podporuje velké soubory** (> 4 GB) a ochranu heslem.  
- **Konzistentní API napříč .NET Framework, .NET Core a .NET 5+**.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte:

1. **Aspose.Zip pro .NET** nainstalovaný. Stáhněte si nejnovější balíček ze [stránky ke stažení Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Složku na vašem počítači obsahující soubory, které chcete komprimovat (např. `alice29.txt` a `fields.c`).  

## Import jmenných prostorů

V jakémkoli C# souboru, kde budete pracovat se zip archivy, přidejte následující `using` direktivy:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Tyto jmenné prostory vám poskytují přístup ke třídě `Archive`, možnostem ukládání a standardním I/O utilitám.

## Průvodce krok za krokem

### Krok 1: Nastavte adresář s dokumenty

Nejprve definujte složku, která obsahuje zdrojové soubory. Nahraďte zástupný text absolutní nebo relativní cestou ve vašem systému:

```csharp
string dataDir = "Your Document Directory";
```

> **Tip:** Použijte `Path.Combine` pro tvorbu cest platformově nezávislým způsobem.

### Krok 2: Otevřete zip soubor pro zápis

Vytvořte `FileStream`, který ukazuje na výstupní zip soubor. Proud je otevřen v režimu **Create**, což přepíše jakýkoli existující soubor se stejným názvem:

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

> **Proč použít `FileInfo`?** Zabraňuje načítání celého souboru do paměti, což je zvláště užitečné u velkých souborů.

### Krok 4: Vytvořte archiv a přidejte položky

Instancujte objekt `Archive` a poté zavolejte `CreateEntry` pro každý `FileInfo`. První argument je název, pod kterým bude soubor v zipu, druhý argument je zdrojový `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Krok 5: Uložte zip archiv s požadovaným kódováním

Nakonec uložte archiv do `FileStream`, který jste otevřeli dříve. Zde používáme ASCII kódování pro názvy položek, ale můžete přepnout na UTF‑8, pokud vaše názvy souborů obsahují ne‑ASCII znaky:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Když se ukončí bloky `using`, proudy se automaticky uzavřou a zip soubor je připraven k použití.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| **Prázdný zip soubor** | `FileInfo` ukazuje na neexistující cestu | Ověřte `dataDir` a názvy souborů; použijte `File.Exists` k kontrolě před vytvořením položek. |
| **Nesprávné kódování názvu souboru** | Použití výchozího kódování u ne‑ASCII názvů | Nastavte `Encoding = Encoding.UTF8` v `ArchiveSaveOptions`. |
| **OutOfMemoryException u velkých souborů** | Načítání celého souboru do paměti | `FileInfo` streamuje soubor; ujistěte se, že jinde soubor nečtete do pole bajtů. |
| **Přístup zamítnut** | Aplikace nemá oprávnění zapisovat do výstupní složky | Spusťte aplikaci s potřebnými právy nebo vyberte zapisovatelný adresář. |

## Často kladené otázky

**Q: Mohu přidat ochranu heslem k zip archivu?**  
A: Ano. Po vytvoření `Archive` nastavte `archive.Password = "yourPassword"` před voláním `Save`.

**Q: Je možné aktualizovat existující zip soubor?**  
A: Aspose.Zip podporuje otevření existujícího archivu pomocí `Archive.Open` a následné přidání nových položek.

**Q: Jak komprimovat soubory v ASP.NET MVC kontroleru?**  
A: Stejný kód funguje; jen zajistěte, aby výstupní proud byl vrácen jako `FileResult` klientovi.

**Q: Podporuje Aspose.Zip šifrovací algoritmy?**  
A: Podporuje standardní ZipCrypto a AES‑256 šifrování.

**Q: Co když potřebuji rekurzivně komprimovat složku?**  
A: Procházejte `Directory.GetFiles` (a podadresáře), vytvořte `FileInfo` pro každý soubor a přidejte jej do archivu.

## Existující sekce FAQ (zůstává beze změny)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Závěr

Nyní víte, **jak vytvořit zip archiv** pomocí Aspose.Zip pro .NET, **jak přidat soubory do zipu** a proč je tato metoda ideální pro ASP.NET i další .NET aplikace. Experimentujte s různými úrovněmi komprese, kódováními a šifrovacími možnostmi, abyste archiv přizpůsobili přesně svým potřebám. Šťastnou kompresi!

---

**Poslední aktualizace:** 2025-12-05  
**Testováno s:** Aspose.Zip pro .NET 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}