---
date: 2025-12-09
description: Naučte se, jak v C# vytvořit zip archiv a pomocí Aspose.Zip pro .NET
  krok po kroku extrahovat vnitřní zip soubory v C# tutoriálu.
linktitle: Modifying Zip Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořit zip archiv v C# pomocí Aspose.Zip pro .NET
url: /cs/net/file-compression/modifying-zip-files/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit zip archiv C# pomocí Aspise.Zip pro .NET

## Úvod

Zip soubory jsou standardním formátem pro balení a kompresi dat, ale reálné scénáře často vyžadují, abyste **vytvořili zip archiv C#** programy, které také **extrahují vnitřní zip soubory**, přejmenovávají položky nebo zplošťují vnořené archivy. Aspose.Zip pro .NET vám poskytuje čisté, plně spravované API, které umožňuje všechnu tuto funkčnost bez nutnosti pracovat s nízkoúrovňovým streamovým gymnastikem.

V tomto tutoriálu se naučíte, jak upravit existující zip, vytáhnout vnitřní zip položky a nakonec vše znovu zabalit do nového plochého archivu – vše pomocí stručného C# kódu. Ať už budujete službu pro zpracování souborů, nástroj pro zálohování nebo automatizovaný nasazovací pipeline, níže uvedené kroky vám ukážou přesně, jak úkol splnit.

## Rychlé odpovědi
- **Může Aspose.Zip vytvořit zip archiv C#?** Ano – třída `Archive` vám umožní přímo v C# vytvářet a upravovat zip soubory.
- **Jak extrahovat vnitřní zip soubory?** Otevřete vnější položku jako stream, vytvořte druhý `Archive` z tohoto streamu a poté enumerujte jeho položky.
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence.
- **Podporované verze .NET?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
- **Typický čas běhu vzorku?** Méně než sekunda pro několik megabajtů dat.

## Co je „vytvořit zip archiv C#“?

Vytvoření zip archivu v C# znamená programově generovat soubor `.zip`, který může obsahovat libovolný počet souborů nebo složek, volitelně aplikovat úrovně komprese, šifrování nebo vlastní metadata. Aspose.Zip abstrahuje složitost a umožňuje vám soustředit se na obchodní logiku místo na samotný formát zip souboru.

## Proč použít Aspose.Zip pro .NET?

- **Žádné externí závislosti** – čistá .NET knihovna, žádné nativní DLL.
- **Plná kontrola nad položkami** – přidávejte, mazejte, přejmenovávejte nebo nahrazujte soubory za běhu.
- **Stream‑centrické API** – pracujte s objekty `MemoryStream`, ideální pro cloudové nebo in‑memory scénáře.
- **Robustní práce s vnořenými archivy** – snadno **extrahujte vnitřní zip soubory** bez dočasných souborů na disku.

## Předpoklady

Než začnete, ujistěte se, že máte:

1. **Aspose.Zip pro .NET** nainstalovaný ve vašem projektu. Můžete jej stáhnout **[zde](https://releases.aspose.com/zip/net/)**.  
2. Složku, která obsahuje zdrojové zip soubory, se kterými budete pracovat. Nahraďte `"Your Document Directory"` v ukázkovém kódu skutečnou cestou na vašem počítači.  
3. Vývojové prostředí .NET (Visual Studio, VS Code nebo Rider) cílící na .NET Framework 4.6+ nebo .NET Core 3.1+.

## Import Namespaces

Nejprve přidejte požadované jmenné prostory do rozsahu:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Průvodce krok za krokem

### Krok 1: Otevřete vnější zip soubor  

Začneme otevřením existujícího archivu (`outer.zip`). Příkaz `using` zajistí automatické uzavření souboru.

```csharp
using (Archive outer = new Archive(dataDir + "outer.zip"))
{
    // Code for Step 1
}
```

### Krok 2: Identifikujte vnitřní zip položky  

Dále prohledáme vnější archiv na položky končící na `.zip`. Tyto jsou **vnitřní zip soubory**, které chceme extrahovat.

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

### Krok 3: Extrahujte vnitřní položky  

Nyní zacházíme s každým vnitřním zipem jako s vlastním `Archive`. Zde **extrahujeme vnitřní zip soubory** a načteme jejich obsah do paměti.

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

### Krok 4: Odstraňte položky vnitřního archivu  

Po zachycení potřebných dat odstraníme původní vnitřní zip položky z vnějšího archivu.

```csharp
foreach (ArchiveEntry e in entriesToDelete)
{
    outer.DeleteEntry(e);
}
```

### Krok 5: Přidejte upravené položky do vnějšího zipu  

Nakonec vložíme extrahované soubory zpět do vnějšího archivu, čímž efektivně zploštíme strukturu, a výsledek uložíme jako `flatten.zip`.

```csharp
for (int i = 0; i < namesToInsert.Count; i++)
{
    outer.CreateEntry(namesToInsert[i], contentToInsert[i]);
}

outer.Save(dataDir + "flatten.zip");
```

Dodržením těchto pěti kroků jste **vytvořili zip archiv C#**, který obsahuje stejné soubory jako originál, ale bez vnořených zip vrstev.

## Časté problémy a řešení

| Problém | Proč se vyskytuje | Řešení |
|-------|----------------|-----|
| `ArgumentNullException` při otevírání vnitřního archivu | Pozice streamu `innerCompressed` je na konci | Před vytvořením `Archive` zavolejte `innerCompressed.Position = 0;` |
| Velké soubory způsobují vysokou spotřebu paměti | Všechny vnitřní položky jsou uloženy v objektech `MemoryStream` | Pro velmi velké archivy použijte dočasné soubory na disku (`Path.GetTempFileName()`) |
| Chybějící položky po zploštění | Zapomenutí přidat extrahovaný obsah do seznamu `contentToInsert` | Ujistěte se, že volání `contentToInsert.Add(content);` je uvnitř vnitřní smyčky |

## Často kladené otázky

### Q1: Mohu použít Aspose.Zip pro .NET s jinými programovacími jazyky?

A1: Aspose.Zip je primárně určen pro .NET aplikace. Nicméně Aspose poskytuje knihovny pro různé programovací jazyky, každou přizpůsobenou svému prostředí.

### Q2: Je k dispozici bezplatná zkušební verze Aspose.Zip pro .NET?

A2: Ano, bezplatnou zkušební verzi získáte **[zde](https://releases.aspose.com/)**.

### Q3: Jak získám podporu pro Aspose.Zip pro .NET?

A3: Pro podporu a diskuze navštivte **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

### Q4: Mohu zakoupit dočasnou licenci pro Aspose.Zip pro .NET?

A4: Ano, dočasnou licenci lze získat **[zde](https://purchase.aspose.com/temporary-license/)**.

### Q5: Kde najdu dokumentaci k Aspose.Zip pro .NET?

A5: Dokumentace je dostupná **[zde](https://reference.aspose.com/zip/net/)**.

---

**Poslední aktualizace:** 2025-12-09  
**Testováno s:** Aspose.Zip 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}