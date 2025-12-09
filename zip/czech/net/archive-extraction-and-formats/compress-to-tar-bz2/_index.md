---
date: 2025-11-29
description: Naučte se, jak přidávat soubory do tar a komprimovat soubory do formátu
  tarbz2 v .NET pomocí Aspose.Zip. Tento krok‑za‑krokem průvodce ukazuje, jak efektivně
  vytvářet archivy tarbz2.
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Přidat soubory do tar a komprimovat do TarBz2 pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a komprese do TarBz2 pomocí Aspose.Zip pro .NET

## Úvod

Vítejte v našem komplexním průvodci, jak **přidat soubory do tar** a komprimovat je do formátu TarBz2 pomocí Aspose.Zip pro .NET. Ať už vytváříte zálohovací nástroj, dodáváte nasazovací balíčky, nebo jen potřebujete kompaktní archiv pro distribuci, tento tutoriál vás provede každým krokem s jasnými vysvětleními a praktickými tipy.

Než začneme, ujistěte se, že máte vše potřebné.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip for .NET
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut
- **Potřebuji licenci?** Pro produkci je vyžadována dočasná licence; k dispozici je bezplatná zkušební verze
- **Mohu komprimovat více souborů?** Ano – přidejte do Tar archivu tolik položek, kolik chcete
- **Je kompatibilní s .NET 6+?** Rozhodně, Aspose.Zip podporuje .NET Framework i .NET Core/5/6

## Co je „přidání souborů do tar“?
Přidání souborů do **tar** (Tape Archive) vytvoří jeden nekomprimovaný kontejner, který zachovává strukturu adresářů a metadata souborů. Když na něj následně použijete kompresi Bzip2, výsledek je archiv **tar.bz2** (TarBz2) – ideální pro efektivní ukládání a přenos.

## Proč komprimovat soubory do TarBz2 pomocí Aspose.Zip?
- **Rychlost a jednoduchost** – Jednořádkové volání API zvládne jak vytvoření tar, tak kompresi Bzip2.  
- **Cross‑platform** – Funguje na .NET běhových prostředích Windows, Linux a macOS.  
- **Detailní kontrola** – Vyberte, které soubory zahrnout, nastavte vlastní názvy položek a streamujte přímo na disk.

## Požadavky

- **Aspose.Zip for .NET** – Stáhněte nejnovější balíček z oficiálního webu: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Document Directory** – Složka, která obsahuje soubory, jež chcete archivovat. V příkladech na ni odkazujeme pomocí proměnné `dataDir`.

> **Tip:** Uchovávejte zdrojové soubory v samostatné složce, abyste se vyhnuli nechtěnému zahrnutí nežádoucích souborů.

## Importování jmenných prostorů

Nejprve importujte potřebné jmenné prostory, abyste mohli přistupovat ke třídám Tar a Bzip2 v Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Krok 1: Nastavení Document Directory

Definujte cestu, která ukazuje na složku obsahující soubory, jež chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

> Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou k vaší zdrojové složce.

## Krok 2: Přidání souborů do tar a vytvoření archivu TarBz2

Jádrem procesu je vytvoření `TarArchive`, přidání položek a následné zabalení do `Bzip2Archive`. Níže uvedený kód ukazuje **jak vytvořit tarbz2** v čistém stylu s využitím disposable pattern.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` přidá každý soubor do **tar** kontejneru.  
- `bz2.SetSource(archive)` říká archivu Bzip2, aby komprimoval celý tar stream.  
- `bz2.Save(...)` zapíše finální soubor **tar.bz2** na disk.

**Tip:** Pro **kompresi souborů do tarbz2** hromadně stačí opakovat `archive.CreateEntry` pro každý potřebný soubor.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|--------|-----|
| **File not found** error | Špatná cesta `dataDir` nebo chybějící přípona souboru | Ověřte úplnou cestu a ujistěte se, že soubor existuje. |
| **Empty archive** | Žádné položky nebyly přidány před `bz2.Save` | Přidejte alespoň jedno volání `CreateEntry`. |
| **Permission denied** | Aplikace nemá oprávnění zápisu do výstupní složky | Spusťte aplikaci s potřebnými právy nebo vyberte zapisovatelný adresář. |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET aplikacemi?**  
A: Ano. Funguje s .NET Framework, .NET Core, .NET 5/6 a novějšími runtimey.

**Q: Mohu komprimovat více souborů najednou?**  
A: Rozhodně. Zavolejte `CreateEntry` pro každý soubor před uložením archivu.

**Q: Kde mohu najít další dokumentaci?**  
A: Podrobná dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/).

**Q: Jak získám dočasnou licenci pro Aspose.Zip?**  
A: Můžete ji požádat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, stáhněte si zkušební verzi [zde](https://releases.aspose.com/).

## Závěr

Nyní jste se naučili, jak **přidat soubory do tar**, zabalit je do Bzip2 streamu a vytvořit archiv **TarBz2** pomocí Aspose.Zip pro .NET. Tato technika je rychlá, spolehlivá a funguje na všech moderních .NET platformách. Klidně experimentujte s většími sadami souborů, vlastními názvy položek nebo integrujte kód do vlastních zálohovacích či nasazovacích pipeline.

Pokud narazíte na jakékoli potíže, komunita Aspose.Zip je připravena pomoci – stačí navštívit [fórum podpory Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Poslední aktualizace:** 2025-11-29  
**Testováno s:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}