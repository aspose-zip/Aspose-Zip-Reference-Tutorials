---
date: 2026-04-24
description: Naučte se, jak komprimovat tar a vytvořit archiv TarBz2 v .NET pomocí
  Aspose.Zip. Tento průvodce krok za krokem ukazuje, jak přidávat soubory do tar a
  efektivně generovat soubory tarbz2.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: Komprimování do TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak komprimovat tar a vytvořit TarBz2 pomocí Aspose.Zip pro .NET
url: /cs/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak komprimovat tar a vytvořit TarBz2 pomocí Aspose.Zip pro .NET

## Úvod

V tomto tutoriálu se dozvíte **jak komprimovat tar** archivy a převést je na kompaktní soubor **TarBz2** pomocí knihovny **Aspose.Zip** pro .NET. Ať už vytváříte nástroj pro zálohování, publikujete nasazovací balíčky, nebo jen potřebujete lehký balíček pro distribuci, níže uvedené kroky vás provedou přidáním souborů do tar, aplikací komprese Bzip2 a vytvořením připraveného k sdílení archivu.

Než se pustíme dál, ujistěte se, že máte požadavky uvedené dále v tomto průvodci, abyste mohli postupovat bez problémů.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Zip pro .NET  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut  
- **Potřebuji licenci?** Pro produkci je vyžadována dočasná licence; k dispozici je bezplatná zkušební verze  
- **Mohu komprimovat více souborů?** Ano – můžete přidat libovolný počet položek do tar archivu  
- **Je kompatibilní s .NET 6+?** Rozhodně, Aspose.Zip podporuje .NET Framework i .NET Core/5/6  

## Co je archiv TarBz2?

Soubor **TarBz2** kombinuje tradiční kontejner **tar** (který zachovává strukturu adresářů a metadata souborů) s kompresí **Bzip2**, což vede k vysoce komprimovanému balíčku `.tar.bz2`. Tento formát je populární na Unix‑like systémech, protože nabízí dobrý poměr mezi kompresním poměrem a rychlostí dekomprese.

## Proč komprimovat soubory do TarBz2 pomocí Aspose.Zip?

- **Rychlost a jednoduchost** – Jednořádkové volání API zvládne jak vytvoření tar, tak kompresi Bzip2.  
- **Cross‑platform** – Funguje na .NET runtime na Windows, Linuxu i macOS.  
- **Detailní kontrola** – Vyberte, které soubory zahrnout, nastavte vlastní názvy položek a streamujte přímo na disk.  
- **Robustní podpora .NET** – Ideální pro scénáře **tar archive .net**, od konzolových aplikací po webové služby.  

## Požadavky

- **Aspose.Zip pro .NET** – Stáhněte nejnovější balíček z oficiální stránky: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Adresář dokumentů** – Složka, která obsahuje soubory, které chcete archivovat. V příkladech na ni odkazujeme pomocí proměnné `dataDir`.

> **Tip:** Uchovávejte zdrojové soubory v samostatné složce, abyste se vyhnuli neúmyslnému zahrnutí nežádoucích souborů.

## Importujte jmenné prostory

Nejprve importujte požadované jmenné prostory, abyste mohli přistupovat ke třídám Tar a Bzip2 z Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Krok 1: Nastavte adresář dokumentů

Definujte cestu, která ukazuje na složku obsahující soubory, které chcete archivovat.

```csharp
string dataDir = "Your Document Directory";
```

> Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou k vaší zdrojové složce.

## Krok 2: Přidejte soubory do tar a vytvořte archiv TarBz2

Jádrem procesu je vytvoření `TarArchive`, přidání položek a následné zabalení do `Bzip2Archive`. Níže uvedený kód demonstruje **jak vytvořit tar** a komprimovat jej do **TarBz2** v čistém stylu s využitím disposable‑pattern.

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

- `CreateEntry` **přidává soubory do tar** – můžete tuto metodu volat pro každý soubor, který potřebujete v archivu.  
- `bz2.SetSource(archive)` říká Bzip2 archivu, aby komprimoval celý tar stream.  
- `bz2.Save(...)` zapíše finální soubor **TarBz2** na disk.

**Tip:** Pro **hromadné přidání souborů do tar** jednoduše opakujte `archive.CreateEntry` pro každý soubor před voláním `bz2.Save`.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Chyba souboru nenalezen** | Nesprávná cesta `dataDir` nebo chybějící přípona souboru | Ověřte úplnou cestu a ujistěte se, že soubor existuje. |
| **Prázdný archiv** | Žádné položky nebyly přidány před `bz2.Save` | Přidejte alespoň jedno volání `CreateEntry`. |
| **Přístup odmítnut** | Aplikace nemá oprávnění zapisovat do výstupní složky | Spusťte aplikaci s příslušnými právy nebo vyberte zapisovatelný adresář. |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET aplikacemi?**  
A: Ano. Funguje s .NET Framework, .NET Core, .NET 5/6 a novějšími runtime.

**Q: Mohu komprimovat více souborů najednou?**  
A: Rozhodně. Zavolejte `CreateEntry` pro každý soubor před uložením archivu.

**Q: Kde mohu najít další dokumentaci?**  
A: Podrobná dokumentace je k dispozici [zde](https://reference.aspose.com/zip/net/).

**Q: Jak získám dočasnou licenci pro Aspose.Zip?**  
A: Můžete ji požádat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, trial verzi si můžete stáhnout [zde](https://releases.aspose.com/).

## Závěr

Nyní jste se naučili **jak komprimovat tar**, přidávat do něj soubory a zabalit výsledek do Bzip2 proudu, abyste vytvořili archiv **TarBz2** pomocí Aspose.Zip pro .NET. Tento přístup je rychlý, spolehlivý a funguje na všech moderních .NET platformách. Klidně experimentujte s většími sadami souborů, vlastními názvy položek nebo integrujte kód do vlastních zálohovacích či nasazovacích pipeline.

Pokud narazíte na jakékoli potíže, komunita Aspose.Zip je připravena pomoci – stačí navštívit [fórum podpory Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Poslední aktualizace:** 2026-04-24  
**Testováno s:** Aspose.Zip pro .NET (nejnovější verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}