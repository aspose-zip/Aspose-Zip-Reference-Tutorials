---
date: 2026-02-15
description: Naučte se, jak komprimovat soubory v C# pomocí Aspose.Zip pro .NET, upravovat
  zip soubory v C#, extrahovat vnitřní položky zipu a vytvářet ploché archivy v podrobném
  návodu krok za krokem.
linktitle: Modifying Zip Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Komprimujte soubory v C# pomocí Aspose.Zip – Vytváření a úprava ZIP
url: /cs/net/file-compression/modifying-zip-files/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření zip archivu C# pomocí Aspose.Zip pro .NET

## Úvod

Komprimování souborů v C# je běžná potřeba, když potřebujete odesílat data, vytvářet zálohy nebo snižovat náklady na úložiště. Aspose.Zip pro .NET odstraňuje nízkoúrovňové detaily a umožňuje vám soustředit se na **co** chcete dosáhnout – ať už jde o vytvoření zcela nového archivu, zploštění vnořených zip souborů nebo aktualizaci existujícího balíčku.  

V tomto tutoriálu se naučíte, jak **modifikovat zip soubor v C#**, extrahovat vnitřní zip položky, smazat nechtěné položky a nakonec **komprimovat soubory v C#** do čistého, plochého archivu. Tento přístup funguje perfektně pro služby zpracování souborů, automatizované nasazovací pipeline nebo jakýkoli scénář, kde potřebujete programově pracovat se zip archivy.

## Rychlé odpovědi
- **Může Aspose.Zip vytvořit zip archiv v C#?** Ano – třída `Archive` vám umožňuje přímo v C# vytvářet a upravovat zip soubory.  
- **Jak extrahuji vnitřní zip soubory?** Otevřete vnější položku jako stream, vytvořte druhý `Archive` z tohoto streamu a poté projděte jeho položky.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Typický čas běhu ukázky?** Méně než sekunda pro několik megabajtů dat.

## Jak komprimovat soubory C# pomocí Aspose.Zip

Než se ponoříme do kódu, objasněme, proč byste si mohli vybrat Aspose.Zip místo jiných knihoven:

- **Čistá .NET implementace** – žádné nativní DLL, což usnadňuje nasazení do cloudových služeb.  
- **Plná kontrola nad položkami** – můžete přidávat, mazat, přejmenovávat nebo nahrazovat soubory za běhu, což je nezbytné, když potřebujete **modifikovat zip soubor v C#** programově.  
- **Stream‑centrické API** – pracujte přímo s objekty `MemoryStream`, ideální pro in‑memory zpracování nebo serverless funkce.  
- **Podpora vnořených archivů** – extrahování vnitřních zip souborů bez zápisu dočasných souborů na disk.

## Co je „vytvořit zip archiv C#“?

Vytvoření zip archivu v C# znamená programově vygenerovat soubor `.zip`, který může obsahovat libovolný počet souborů nebo složek, volitelně s nastavením úrovně komprese, šifrování nebo vlastních metadat. Aspose.Zip abstrahuje složitost a umožňuje vám soustředit se na obchodní logiku místo samotného formátu zip souboru.

## Proč používat Aspose.Zip pro .NET?

- **Žádné externí závislosti** – čistá .NET knihovna, žádné nativní DLL.  
- **Plná kontrola nad položkami** – přidávejte, mazejte, přejmenovávejte nebo nahrazujte soubory za běhu.  
- **Stream‑centrické API** – pracujte s objekty `MemoryStream`, ideální pro cloud nebo in‑memory scénáře.  
- **Robustní práce s vnořenými archivy** – snadno **extrahujte vnitřní zip soubory** bez dočasných souborů na disku.

## Požadavky

Než začnete, ujistěte se, že máte:

1. **Aspose.Zip for .NET** nainstalovaný ve vašem projektu. Můžete jej stáhnout **[zde](https://releases.aspose.com/zip/net/)**.  
2. Složku, která obsahuje zdrojové zip soubory, se kterými budete pracovat. Nahraďte `"Your Document Directory"` v ukázkách kódu skutečnou cestou na vašem počítači.  
3. Vývojové prostředí .NET (Visual Studio, VS Code nebo Rider) cílící na .NET Framework 4.6+ nebo .NET Core 3.1+.

## Importování jmenných prostorů

Nejprve načtěte požadované jmenné prostory:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Jak modifikovat zip soubor C# s Aspose.Zip

Níže je krok‑za‑krokem průvodce, který vás provede otevřením existujícího archivu, extrahováním vnitřních zip položek, zploštěním struktury a nakonec uložením nového archivu.

### Krok 1: Otevření vnějšího zip souboru  

Začínáme otevřením existujícího archivu (`outer.zip`). Příkaz `using` zajistí automatické uzavření souboru.

```csharp
using (Archive outer = new Archive(dataDir + "outer.zip"))
{
    // Code for Step 1
}
```

### Krok 2: Identifikace vnitřních zip položek  

Dále prohledáme vnější archiv na položky, které končí na `.zip`. Tyto jsou **vnitřní zip soubory**, které chceme extrahovat.

```csharp
List<ArchiveEntry> entriesToDelete = new List<ArchiveEntry>();
List<string> namesToInsert = new List<string>();
List<MemoryStream> contentToInsert = new List<MemoryStream>();

foreach (ArchiveEntry entry in outer.Entries)
{
    if (entry.Name.EndsWith(".zip", StringComparison.InvariantCultureIgnoreCase))
    {
        entriesToDelete.Add(entry);
        MemoryStream innerCompressed = new MemoryStream();
        entry.Open().CopyTo(innerCompressed);
        
        // Code for extracting inner entries
    }
}
```

### Krok 3: Extrahování vnitřních položek  

Nyní zacházíme s každým vnitřním zipem jako s vlastním `Archive`. Zde **extrahujeme vnitřní zip soubory** a shromažďujeme jejich obsah v paměti.

```csharp
using (Archive inner = new Archive(innerCompressed))
{
    foreach (ArchiveEntry ie in inner.Entries)
    {
        namesToInsert.Add(ie.Name);
        MemoryStream content = new MemoryStream();
        ie.Open().CopyTo(content);
        
        // Code for extracting content of inner entries
    }
}
```

### Krok 4: Smazání vnitřních archivních položek  

Po zachycení potřebných dat odstraníme původní vnitřní zip položky z vnějšího archivu. Tento krok je v podstatě logikou **delete zip entry C#**.

```csharp
foreach (ArchiveEntry e in entriesToDelete)
{
    outer.DeleteEntry(e);
}
```

### Krok 5: Přidání upravených položek do vnějšího zipu  

Nakonec znovu vložíme extrahované soubory zpět do vnějšího archivu, čímž efektivně zploštíme strukturu, a výsledek uložíme jako `flatten.zip`.

```csharp
for (int i = 0; i < namesToInsert.Count; i++)
{
    outer.CreateEntry(namesToInsert[i], contentToInsert[i]);
}

outer.Save(dataDir + "flatten.zip");
```

Dodržením těchto pěti kroků jste **vytvořili zip archiv C#**, který obsahuje stejné soubory jako originál, ale bez vnořených zip vrstev.

## Časté problémy a řešení

| Problém | Proč k tomu dochází | Řešení |
|---------|----------------------|--------|
| `ArgumentNullException` při otevírání vnitřního archivu | Pozice streamu `innerCompressed` je na konci | Před vytvořením `Archive` zavolejte `innerCompressed.Position = 0;` |
| Velké soubory způsobují vysokou spotřebu paměti | Všechny vnitřní položky jsou uloženy v objektech `MemoryStream` | Pro velmi velké archivy použijte dočasné soubory na disku (`Path.GetTempFileName()`) |
| Chybějící položky po zploštění | Zapomenutí přidat extrahovaný obsah do seznamu `contentToInsert` | Ujistěte se, že voláte `contentToInsert.Add(content);` uvnitř vnitřní smyčky |

## Často kladené otázky

### Q1: Mohu použít Aspose.Zip pro .NET s jinými programovacími jazyky?

A1: Aspose.Zip je primárně určen pro .NET aplikace. Nicméně Aspose poskytuje knihovny pro různé programovací jazyky, každou přizpůsobenou jejich prostředí.

### Q2: Je k dispozici bezplatná zkušební verze pro Aspose.Zip pro .NET?

A2: Ano, bezplatnou zkušební verzi můžete získat **[zde](https://releases.aspose.com/)**.

### Q3: Jak získám podporu pro Aspose.Zip pro .NET?

A3: Pro podporu a diskuse navštivte **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

### Q4: Mohu zakoupit dočasnou licenci pro Aspose.Zip pro .NET?

A4: Ano, dočasnou licenci můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

### Q5: Kde najdu dokumentaci pro Aspose.Zip pro .NET?

A5: Dokumentace je dostupná **[zde](https://reference.aspose.com/zip/net/)**.

---

**Poslední aktualizace:** 2026-02-15  
**Testováno s:** Aspose.Zip 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}