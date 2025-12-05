---
date: 2025-12-05
description: Naučte se, jak vytvořit archiv tarxz v .NET a jak komprimovat soubory
  tarxz pomocí Aspose.Zip pro .NET. Postupujte podle tohoto krok‑za‑krokem průvodce
  pro efektivní ukládání a přenos.
language: cs
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak vytvořit tarxz archiv v .NET pomocí Aspose.Zip
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit tarxz archiv .net pomocí Aspose.Zip

## Úvod

Pokud potřebujete **vytvořit tarxz archiv .net**, Aspose.Zip pro .NET proces zjednodušuje a dělá jej spolehlivým. Ať už balíte logy, konfigurační soubory nebo jakékoli jiné prostředky pro uložení či přenos, komprese do formátu TarXz vám poskytne vysoký kompresní poměr při zachování známé struktury tar. V tomto tutoriálu projdeme přesné kroky — včetně úryvků kódu — abyste mohli s jistotou integrovat tvorbu tarxz do svých .NET aplikací.

## Rychlé odpovědi
- **Jaká je hlavní třída?** `TarArchive` z `Aspose.Zip.Tar`
- **Jak komprimovat tarxz?** Použijte `SaveXzCompressed` po přidání položek
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Je licence potřebná?** Ano, platná licence Aspose.Zip pro produkci
- **Typická doba implementace?** ~5‑10 minut

## Co je TarXz archiv?

**TarXz archiv** kombinuje tradiční unixový kontejner `tar` s XZ kompresí. Část tar sbaluje více souborů do jednoho proudu, zatímco XZ poskytuje silnou, bezztrátovou kompresi. Tento formát je populární pro distribuci zdrojového kódu, záloh a velkých datových sad, protože zachovává adresářové struktury a dosahuje menších velikostí souborů než prostý tar nebo zip.

## Proč vytvářet tarxz archiv .net s Aspose.Zip?

- **Vysoký kompresní poměr** — XZ často komprimuje o 30‑50 % více než gzip.
- **Kompatibilita napříč platformami** — TarXz soubory lze otevřít na Linuxu, macOS i Windows.
- **Jednoduché API** — Aspose.Zip abstrahuje nízkoúrovňové detaily, takže se můžete soustředit na obchodní logiku.
- **Žádné externí nástroje** — Vše běží uvnitř vašeho .NET procesu, ideální pro cloud nebo CI pipeline.

## Požadavky

Než začneme, ujistěte se, že máte:

- **Aspose.Zip pro .NET** nainstalovaný (stáhněte z oficiální [Aspose.Zip dokumentace](https://reference.aspose.com/zip/net/)).
- Složku obsahující soubory, které chcete archivovat. V příkladech níže je tato složka odkazována proměnnou `dataDir`.
- Platnou licenci Aspose.Zip (volitelně pro hodnocení, povinně pro produkci).

## Importujte jmenné prostory

Nejprve importujte jmenné prostory, které zpřístupňují funkčnost TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Postupný průvodce vytvořením tarxz archivu .net

### Krok 1: Inicializujte `TarArchive`

Vytvořte novou instanci `TarArchive`, která bude obsahovat soubory k kompresi.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Tip:** Příkaz `using` zajišťuje, že archiv bude řádně uvolněn a uvolní jakékoli neřízené prostředky.

### Krok 2: Přidejte soubory do archivu

Přidejte každý soubor, který chcete zahrnout. V tomto příkladu přidáváme dva textové soubory, ale můžete přidat libovolný počet položek.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Proč je to důležité:** Přidání položek před kompresí umožňuje Aspose.Zip nejprve vytvořit tar kontejner a poté aplikovat XZ kompresi v jednom kroku.

### Krok 3: Uložte archiv s XZ kompresí

Nakonec zapište tar archiv na disk s XZ kompresí. Výsledný soubor bude mít příponu `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Výsledek:** Nyní máte plně komprimovaný soubor `archive.tar.xz`, který můžete přenášet, ukládat nebo rozbalovat na jakékoli platformě podporující TarXz.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Výjimka „File not found“** | Nesprávná cesta `dataDir` | Ověřte, že cesta končí zpětným lomítkem (`\`) nebo použijte `Path.Combine`. |
| **Vysoká spotřeba paměti** | Velmi velké soubory komprimované v paměti | Použijte `TarArchive` v režimu streamování (`SaveXzCompressed` přetížení přijímající `Stream`). |
| **Licence nebyla použita** | Chybějící licenční soubor | Načtěte licenci při startu aplikace: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET prostředími?**  
A: Ano, Aspose.Zip funguje s .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6+. Viz [dokumentace](https://reference.aspose.com/zip/net/) pro podrobnosti.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Zip?**  
A: Dočasnou licenci můžete požádat na [stránce dočasných licencí Aspose](https://purchase.aspose.com/temporary-license/).

**Q: Existují další příklady pro jiné formáty archivů?**  
A: Rozhodně — prozkoumejte kompletní sadu příkladů v [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: Kde mohu získat pomoc nebo diskutovat o problémech?**  
A: Připojte se k diskuzi na [fóru Aspose.Zip](https://forum.aspose.com/c/zip/37) pro komunitní podporu a oficiální odpovědi.

**Q: Můžu si Aspose.Zip vyzkoušet zdarma před zakoupením?**  
A: Ano, bezplatná zkušební verze je k dispozici na [stahovací stránce Aspose.Zip](https://releases.aspose.com/zip/net).

## Závěr

Po absolvování výše uvedených kroků nyní víte, **jak komprimovat tarxz** soubory a, co je důležitější, **jak vytvořit tarxz archiv .net** pomocí Aspose.Zip. Tento přístup vám poskytne kompaktní, přenosný balíček, který lze snadno začlenit do jakéhokoli .NET workflow — ať už vytváříte desktopovou utilitu, webovou službu nebo automatizovanou CI/CD pipeline.

---

**Poslední aktualizace:** 2025-12-05  
**Testováno s:** Aspose.Zip pro .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}