---
date: 2026-02-20
description: Naučte se, jak vytvořit tar archiv, přidávat soubory do taru a komprimovat
  do tar.gz pomocí Aspose.Zip pro .NET – rychlý, multiplatformní způsob, jak vytvářet
  archivy TarGz.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Vytvořte tar archiv a přidejte soubory do taru pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

:" to "Poslední aktualizace:" maybe. But it's part of content after a horizontal rule. Should translate.

"Tested With:" => "Testováno s:".

"Author:" => "Autor:".

Make sure to keep shortcodes.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte tar archiv a přidejte soubory do tar pomocí Aspose.Zip pro .NET

## Úvod

V moderních .NET aplikacích je **vytvoření tar archivu** a **přidání souborů do tar** rychle a spolehlivě běžnou požadavkem — ať už balíte logy, připravujete data pro cloudové úložiště nebo vytváříte nasazovací balíčky. Aspose.Zip pro .NET vám poskytuje čisté, výkonné API pro **přidání souborů do tar**, následně archiv komprimuje do široce používaného formátu **tar.gz**. V tomto průvodci projdeme celý proces, od nastavení projektu až po vytvoření připraveného `archive.tar.gz`.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip pro .NET  
- **Jak přidám soubory do tar?** Použijte `TarArchive.CreateEntry` pro každý soubor.  
- **Mohu komprimovat přímo do tar.gz?** Ano — zavolejte `SaveGzipped`.  
- **Potřebuji licenci pro produkci?** Platná licence Aspose je vyžadována pro ne‑zkušební použití.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co znamená „add files to tar“?
Přidání souborů do tar archivu znamená sloučení více souborů do jednoho nekomprimovaného kontejneru. Formát tar zachovává strukturu adresářů a metadata souborů, což je ideální pro archivaci před volitelnou kompresí (např. gzip) a **vytvořením tar.gz archivu**.

## Proč použít Aspose.Zip k kompresi souborů do tar.gz?
- **Žádné externí nástroje** — vše běží uvnitř vašeho .NET kódu.  
- **Vysoký výkon** — stream‑based API efektivně zpracovává velké soubory.  
- **Cross‑platform tar** — funguje na Windows, Linuxu i macOS bez úprav.  
- **Bohatá sada funkcí** — podporuje šifrování, ochranu heslem a vlastní atributy položek.

## Požadavky

Než začnete, ujistěte se, že máte:

- Základní zkušenosti s vývojem v .NET.  
- Visual Studio (nebo libovolné preferované IDE).  
- Aspose.Zip pro .NET nainstalovaný — viz oficiální dokumentace [zde](https://reference.aspose.com/zip/net/).  
- Knihovnu Aspose.Zip staženou z [tohoto odkazu](https://releases.aspose.com/zip/net/).

## Importujte jmenné prostory

Ve svém .NET projektu importujte jmenné prostory, které exponují třídy související s tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak přidat soubory do tar pomocí Aspose.Zip pro .NET

### Krok 1: Nastavte adresář dokumentů

Nejprve nasměrujte kód na složku, která obsahuje soubory, jež chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

> **Tip:** Používejte `Path.Combine` při sestavování cest, abyste se vyhnuli problémům s oddělovači specifickými pro platformu.

### Krok 2: Vytvořte archiv TarGz

Nyní vytvoříme tar archiv, přidáme položky a komprimujeme jej v jednom plynulém toku.

#### 2.1 Inicializujte TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Přidejte soubory – jádro „add files to tar“

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Každé volání `CreateEntry` přijímá **název položky** (jak se soubor zobrazí uvnitř tar) a **cestu ke zdrojovému souboru** na disku. `CreateEntry` můžete volat opakovaně a **přidat více souborů tar** do jednoho archivu.

#### 2.3 Uložte jako Gzipped Tar (jak komprimovat tar.gz)

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` zapíše obsah tar do gzip streamu a vytvoří kompaktní soubor `archive.tar.gz`, připravený k distribuci.

## Běžné případy použití

| Scénář | Proč pomáhá „add files to tar“ |
|----------|------------------------------|
| **Agregace logů** | Zabalte denní logy do jednoho archivu před nahráním do cloudového úložiště. |
| **Balíčky pro nasazení** | Vytvořte přenosné tar.gz balíčky pro Linux servery z Windows build pipeline. |
| **Zálohování dat** | Zachovejte hierarchii složek a metadata při nízké velikosti zálohy. |

## Běžné problémy a řešení

- **Chyba soubor nenalezen** — Ujistěte se, že `dataDir` končí správným oddělovačem cesty nebo použijte `Path.Combine`.  
- **Velké soubory způsobují tlak na paměť** — Použijte overloady založené na streamech (`CreateEntry` s `Stream`), abyste se vyhnuli načítání celých souborů do paměti.  
- **Výstup gzip je poškozený** — Ověřte, že je archiv uzavřen (`using` blok) před voláním `SaveGzipped`.  

## Často kladené otázky

**Q: Je Aspose.Zip pro .NET kompatibilní se všemi .NET aplikacemi?**  
A: Ano, funguje s .NET Framework, .NET Core i .NET 5/6/7 projekty.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Zip pro .NET?**  
A: Navštivte [stránku s dočasnou licencí](https://purchase.aspose.com/temporary-license/) a požádejte o zkušební licenci.

**Q: Existují nějaká omezení velikosti souboru?**  
A: Knihovna je optimalizována pro velké soubory; neexistuje žádný pevný limit kromě dostupné systémové paměti.

**Q: Kde mohu získat podporu?**  
A: Použijte komunitní fórum podpory [zde](https://forum.aspose.com/c/zip/37) pro pomoc od inženýrů Aspose a dalších vývojářů.

**Q: Můžu Aspose.Zip pro .NET vyzkoušet zdarma?**  
A: Rozhodně — stáhněte si bezplatnou zkušební verzi z [stránky s vydáními Aspose Zip](https://releases.aspose.com/zip/net).

## Závěr

Nyní jste se naučili **jak vytvořit tar archiv**, přidat do něj soubory a komprimovat jej do **tar.gz** pomocí Aspose.Zip pro .NET. Tento přístup eliminuje externí závislosti, poskytuje jemnou kontrolu nad obsahem archivu a škáluje na velké datové sady. Neváhejte prozkoumat další funkce Aspose.Zip, jako je šifrování, vlastní atributy položek a streaming API, a dále tak vylepšit svůj archivní workflow.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-02-20  
**Testováno s:** Aspose.Zip 24.11 pro .NET  
**Autor:** Aspose