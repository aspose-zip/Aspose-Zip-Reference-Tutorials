---
date: 2026-02-28
description: Naučte se, jak přidat složku do zipu a přidat soubory do zipu pomocí
  Aspose.Zip pro .NET. Tento krok‑za‑krokem průvodce ukazuje, jak komprimovat soubory
  pomocí FileInfo v projektech ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak přidat složku do ZIP pomocí Aspose.Zip pro .NET – Komprimovat soubory pomocí
  FileInfo
url: /cs/net/file-compression/compress-files-fileinfo/
weight: 11
---

 final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat složku do ZIP pomocí Aspose.Zip pro .NET

## Úvod

Pokud potřebujete **programově vytvořit ZIP archiv**, Aspose.Zip pro .NET vám poskytuje čisté, vysoce výkonné API, které funguje v jakékoli .NET aplikaci (včetně ASP.NET). V tomto tutoriálu si projdeme kompresi souborů pomocí třídy `FileInfo`, ukážeme vám, jak **přidat soubory do ZIP**, a vysvětlíme, proč je tento přístup ideální pro moderní .NET projekty. Také se podíváme na to, jak **přidat složku do ZIP**, abyste mohli v jednom kroku zabalit celé adresáře. Pojďme na to!

## Rychlé odpovědi
- **Jaký je nejjednodušší způsob, jak vytvořit ZIP archiv?** Použijte třídu `Archive` z Aspose.Zip spolu s objekty `FileInfo`.  
- **Mohu přidat více souborů najednou?** Ano – stačí vytvořit `FileInfo` pro každý soubor a zavolat `CreateEntry`.  
- **Potřebuji speciální licenci pro ASP.NET?** Pro produkci je vyžadována komerční licence Aspose.Zip; pro hodnocení stačí bezplatná zkušební verze.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Je API thread‑safe?** Ano, pokud každý vlákno pracuje se svou vlastní instancí `Archive`.

## Co je ZIP archiv a proč jej vytvořit?
ZIP archiv slouží ke spojení jednoho nebo více souborů do jediného komprimovaného kontejneru. To šetří úložný prostor, urychluje přenosy po síti a zjednodušuje distribuci. Ať už dodáváte logy, exportujete zprávy nebo balíte zdroje pro klienta, schopnost **programově vytvořit ZIP archiv** je cenná dovednost pro každého .NET vývojáře.

## Proč použít Aspose.Zip pro přidání souborů do ZIP?
- **Žádné externí závislosti** – čistá .NET implementace.  
- **Plná kontrola nad úrovní komprese a kódováním** (ASCII, UTF‑8 atd.).  
- **Podporuje velké soubory** (> 4 GB) a ochranu heslem.  
- **Konzistentní API napříč .NET Framework, .NET Core a .NET 5+**.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte:

1. **Aspose.Zip pro .NET** nainstalovaný. Stáhněte si nejnovější balíček ze [stránky ke stažení Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Složku na vašem počítači obsahující soubory, které chcete komprimovat (např. `alice29.txt` a `fields.c`).  

## Import jmenných prostor

V libovolném C# souboru, kde budete pracovat se ZIP archivy, přidejte následující `using` direktivy:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Tyto jmenné prostory vám poskytují přístup ke třídě `Archive`, možnostem uložení a standardním I/O utilitám.

## Průvodce krok za krokem

### Krok 1: Nastavte adresář dokumentu

Nejprve definujte složku, která obsahuje zdrojové soubory. Nahraďte zástupný text absolutní nebo relativní cestou ve vašem systému:

```csharp
string dataDir = "Your Document Directory";
```

> **Tip:** Použijte `Path.Combine` pro sestavování cest platformově nezávislým způsobem.

### Krok 2: Otevřete ZIP soubor pro zápis

Vytvořte `FileStream`, který ukazuje na výstupní ZIP soubor. Proud je otevřen v režimu **Create**, který přepíše jakýkoli existující soubor se stejným názvem:

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

> **Proč používat `FileInfo`?** Zabraňuje načítání celého souboru do paměti, což je obzvláště užitečné u velkých souborů.

### Krok 4: Vytvořte archiv a přidejte položky

Instancujte objekt `Archive` a poté pro každý `FileInfo` zavolejte `CreateEntry`. První argument je název, pod kterým bude soubor uvnitř ZIPu, druhý argument je zdrojový `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Krok 5: Uložte ZIP archiv s požadovaným kódováním

Nakonec uložte archiv do `FileStream`, který jste otevřeli dříve. Zde používáme ASCII kódování pro názvy položek, ale můžete přepnout na UTF‑8, pokud vaše názvy souborů obsahují ne‑ASCII znaky:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Když se ukončí bloky `using`, proudy se automaticky uzavřou a ZIP soubor je připraven k použití.

## Jak přidat složku do ZIP pomocí Aspose.Zip

Pokud potřebujete **přidat složku do ZIP** místo jednotlivých souborů, postup je jednoduchý:

1. **Procházejte složku** pomocí `DirectoryInfo.GetFiles` (a volitelně `GetDirectories` pro rekurzi).  
2. **Vytvořte `FileInfo`** pro každý nalezený soubor.  
3. **Zavolejte `CreateEntry`** s relativní cestou, která zahrnuje název složky, např. `"MyFolder/Report.pdf"`.

Protože API pracuje s `FileInfo`, nikdy nemusíte načítat celé soubory do paměti, což je bezpečné i pro velké adresáře. Tento postup funguje také pro scénáře **zip multiple files asp.net**, kde na letě generujete sadu zpráv a potřebujete ji doručit jako jeden archiv.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| **Prázdný ZIP soubor** | `FileInfo` ukazuje na neexistující cestu | Ověřte `dataDir` a názvy souborů; použijte `File.Exists` k kontrolě před vytvořením položek. |
| **Nesprávné kódování názvu souboru** | Použití výchozího kódování u ne‑ASCII názvů | Nastavte `Encoding = Encoding.UTF8` v `ArchiveSaveOptions`. |
| **OutOfMemoryException u velkých souborů** | Načítání celého souboru do paměti | `FileInfo` soubor streamuje; ujistěte se, že jinde soubor nečtete do pole bajtů. |
| **Přístup zamítnut** | Aplikace nemá právo zápisu do výstupní složky | Spusťte aplikaci s odpovídajícími právy nebo vyberte zapisovatelný adresář. |

## Často kladené otázky

**Q: Mohu přidat ochranu heslem do ZIP archivu?**  
A: Ano. Po vytvoření `Archive` nastavte `archive.Password = "yourPassword"` před voláním `Save`.

**Q: Je možné aktualizovat existující ZIP soubor?**  
A: Aspose.Zip podporuje otevření existujícího archivu pomocí `Archive.Open` a následné přidání nových položek.

**Q: Jak komprimovat soubory v ASP.NET MVC kontroleru?**  
A: Stejný kód funguje; jen zajistěte, aby výstupní proud byl vrácen jako `FileResult` klientovi.

**Q: Podporuje Aspose.Zip šifrovací algoritmy?**  
A: Podporuje standardní ZipCrypto a AES‑256 šifrování.

**Q: Co když potřebuji rekurzivně komprimovat složku?**  
A: Projděte `Directory.GetFiles` (a podadresáře) a pro každý soubor vytvořte `FileInfo`, poté jej přidejte do archivu.

## Další FAQ

**Q: Jak vytvořit ZIP archiv v .NET pro velké datové sady?**  
A: Použijte objekty `FileInfo` pro streamování dat a nastavte `CompressionLevel` v `ArchiveSaveOptions` pro optimální výkon.

**Q: Můžu použít Aspose.Zip v .NET Core web API (zip files asp.net core)?**  
A: Rozhodně – knihovna je plně kompatibilní s .NET Core 3.1 a novějšími verzemi.

**Q: Existuje způsob, jak přidat složku do ZIP bez psaní vlastního cyklu?**  
A: Aspose.Zip nemá jednorázovou metodu „add folder“, ale iterace pomocí `DirectoryInfo` je nenáročná a dává vám plnou kontrolu nad názvy položek.

**Q: Ovlivňuje ochrana heslem rychlost komprese ZIP archivu?**  
A: Šifrování přidává malou režii, ale dopad je pro většinu případů minimální.

**Q: Jaká licence je potřeba pro komerční nasazení?**  
A: Pro produkci je vyžadována placená licence Aspose.Zip; pro vývoj a testování stačí bezplatná zkušební verze.

## Existující sekce FAQ (zůstává nezměněna)

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

Nyní už víte, **jak přidat složku do ZIP** a **jak vytvořit ZIP archiv** pomocí Aspose.Zip pro .NET, **jak přidat soubory do ZIP** a proč je tato metoda ideální pro ASP.NET i další .NET aplikace. Vyzkoušejte různé úrovně komprese, kódování a šifrovací možnosti, abyste archiv přizpůsobili přesně svým potřebám. Šťastnou kompresi!

---

**Poslední aktualizace:** 2026-02-28  
**Testováno s:** Aspose.Zip pro .NET 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}