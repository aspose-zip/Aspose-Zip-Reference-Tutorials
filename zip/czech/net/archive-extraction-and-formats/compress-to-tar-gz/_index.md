---
date: 2026-01-28
description: Naučte se, jak vytvořit archiv tar.gz, přidávat soubory do tar a komprimovat
  pomocí Aspose.Zip pro .NET – rychlý, spolehlivý způsob archivace souborů.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořte archiv tar.gz a přidejte soubory do tar pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a vytvoření TarGz pomocí Aspose.Zip pro .NET

## Úvod

V moderních .NET aplikacích je **add files to tar** rychle a spolehlivě běžnou požadavkem — ať už balíte logy, připravujete data pro cloudové úložiště nebo vytváříte nasazovací balíčky. Aspose.Zip pro .NET vám poskytuje čisté, vysoce výkonné API pro **add files to tar**, následně archiv komprimuje do široce používaného formátu **tar.gz**. V tomto tutoriálu se přesně naučíte, jak **create tar.gz archive** od nuly, krok za krokem, pomocí knihovny Aspose.Zip .NET.

## Rychlé odpovědi
- **Jaká knihovna by měla být použita?** Aspose.Zip pro .NET  
- **Jak přidat soubory do tar?** Použijte `TarArchive.CreateEntry` pro každý soubor.  
- **Mohu komprimovat přímo do tar.gz?** Ano — zavolejte `SaveGzipped`.  
- **Potřebuji licenci pro produkci?** Platná licence Aspose je vyžadována pro ne‑zkušební použití.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co znamená „add files to tar“?
Přidání souborů do tar archivu znamená seskupení více souborů do jednoho nekomprimovaného kontejneru. Formát tar zachovává strukturu adresářů a metadata souborů, což ho činí ideálním pro archivaci před volitelnou kompresí (např. gzip) k **create tar.gz archive**.

## Proč použít Aspose.Zip k kompresi souborů do tar.gz?
- **Žádné externí nástroje** — vše běží uvnitř vašeho .NET kódu.  
- **Vysoký výkon** — stream‑based API efektivně zpracovává velké soubory.  
- **Cross‑platform** — funguje na Windows, Linuxu i macOS.  
- **Bohatá sada funkcí** — podporuje šifrování, ochranu heslem a vlastní atributy položek.  

## Požadavky

Než začnete, ujistěte se, že máte:

- Základní zkušenosti s vývojem v .NET.  
- Visual Studio (nebo jakékoli jiné IDE).  
- Aspose.Zip pro .NET nainstalovaný — viz oficiální dokumentace [zde](https://reference.aspose.com/zip/net/).  
- Knihovnu Aspose.Zip staženou z [tohoto odkazu](https://releases.aspose.com/zip/net/).

## Importování jmenných prostorů

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak vytvořit archiv tar.gz pomocí Aspose.Zip pro .NET

### Krok 1: Nastavte adresář dokumentů

Nejprve nasměrujte kód na složku, která obsahuje soubory, jež chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Používejte `Path.Combine` při sestavování cest, aby se předešlo problémům s oddělovači specifickými pro platformu.

### Krok 2: Inicializujte TarArchive

Vytvořte instanci `TarArchive`, která bude obsahovat položky.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

### Krok 3: Přidání souborů – jádro „add files to tar“

Uvnitř `using` bloku přidejte každý soubor, který chcete zahrnout do archivu.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Každé volání `CreateEntry` přijímá **entry name** (jak se soubor zobrazí uvnitř tar) a **source file path** na disku.

### Krok 4: Uložení jako Gzipped Tar (jak komprimovat soubory do tar.gz)

Nakonec zapište obsah tar do gzip streamu a vytvořte kompaktní `archive.tar.gz`.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` zajišťuje jak balení do tar, tak gzip kompresi v jednom plynulém volání.

## Běžné případy použití

| Scénář | Proč pomáhá „add files to tar“ |
|----------|------------------------------|
| **Agregace logů** | Seskládejte denní logy do jednoho archivu před nahráním do cloudového úložiště. |
| **Nasazovací balíčky** | Vytvořte přenosné tar.gz balíčky pro Linux servery z Windows build pipeline. |
| **Zálohování dat** | Zachovejte hierarchii složek a metadata při nízké velikosti zálohy. |

## Běžné problémy a řešení

- **Chyba souboru nenalezen** — Ujistěte se, že `dataDir` končí správným oddělovačem cesty nebo použijte `Path.Combine`.  
- **Velké soubory způsobují tlak na paměť** — Použijte přetížení založená na streamu (`CreateEntry` s `Stream`), aby se předešlo načítání celých souborů do paměti.  
- **Výstup gzip je poškozen** — Ověřte, že archiv je uzavřen (`using` blok) před voláním `SaveGzipped`.  

## Často kladené otázky

**Q: Je Aspose.Zip pro .NET kompatibilní se všemi .NET aplikacemi?**  
A: Ano, funguje s .NET Framework, .NET Core i .NET 5/6/7 projekty.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Zip pro .NET?**  
A: Navštivte [stránku dočasné licence](https://purchase.aspose.com/temporary-license/) a požádejte o zkušební licenci.

**Q: Existují nějaká omezení velikosti souboru?**  
A: Knihovna je optimalizována pro velké soubory; neexistuje pevný limit kromě dostupné systémové paměti.

**Q: Kde mohu získat podporu?**  
A: Použijte komunitní fórum podpory [zde](https://forum.aspose.com/c/zip/37) pro pomoc od inženýrů Aspose a dalších vývojářů.

**Q: Můžu Aspose.Zip pro .NET vyzkoušet zdarma?**  
A: Rozhodně — stáhněte si bezplatnou zkušební verzi z [stránky vydání Aspose Zip](https://releases.aspose.com/zip/net).

## Závěr

Nyní jste se naučili **jak přidat soubory do tar**, vytvořit tar archiv a komprimovat jej do **tar.gz** pomocí Aspose.Zip pro .NET. Tento přístup eliminuje externí závislosti, poskytuje jemnou kontrolu nad obsahem archivu a škáluje na velké datové sady. Neváhejte prozkoumat další funkce Aspose.Zip, jako je šifrování, vlastní atributy položek a streaming API, které ještě více vylepší váš archivní workflow.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-28  
**Testováno s:** Aspose.Zip 24.11 pro .NET  
**Autor:** Aspose