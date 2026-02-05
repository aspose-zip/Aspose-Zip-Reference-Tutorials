---
date: 2026-02-05
description: Naučte se, jak přidávat soubory do tar a vytvářet archivy tarxz v .NET
  pomocí Aspose.Zip. Tento průvodce ukazuje, jak komprimovat soubory do tarxz s vysokou
  efektivitou.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Přidat soubory do tar, vytvořit archiv tarxz v .NET s Aspose.Zip
url: /cs/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat soubory do tar, vytvořit tarxz archiv v .NET s Aspise.Zip

## Úvod

Pokud potřebujete **add files to tar** a poté je komprimovat do tarxz archivu pomocí .NET, Aspose.Zip pro .NET proces zjednodušuje a činí jej spolehlivým. Ať už balíte logy, konfigurační soubory nebo jakékoli další zdroje pro uložení či přenos, komprese do formátu TarXz vám poskytne vysoký kompresní poměr při zachování známé tar struktury. V tomto tutoriálu projdeme přesné kroky — včetně úryvků kódu — abyste mohli s jistotou integrovat tvorbu tarxz do svých .NET aplikací.

## Rychlé odpovědi
- **Jaká je hlavní třída?** `TarArchive` z `Aspose.Zip.Tar`
- **Jak komprimovat tarxz?** Použijte `SaveXzCompressed` po přidání položek
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Je licence potřeba?** Ano, platná licence Aspose.Zip pro produkci
- **Typický čas implementace?** ~5‑10 minut

## Co je archiv TarXz?

**TarXz archiv** kombinuje tradiční Unixový `tar` kontejner s XZ kompresí. Tar část seskupí více souborů do jednoho proudu, zatímco XZ poskytuje silnou bezztrátovou kompresi. Tento formát je populární pro distribuci zdrojového kódu, záloh a velkých datových sad, protože zachovává adresářovou strukturu a dosahuje menších velikostí souborů než čistý tar nebo zip.

## Proč přidávat soubory do tar a komprimovat do tarxz pomocí Aspose.Zip?

- **Vysoký kompresní poměr** – XZ často komprimuje o 30‑50 % méně než gzip.  
- **Kompatibilita napříč platformami** – TarXz soubory lze otevřít na Linuxu, macOS i Windows.  
- **Jednoduché API** – Aspose.Zip abstrahuje nízkoúrovňové detaily, takže se můžete soustředit na obchodní logiku.  
- **Žádné externí nástroje** – Vše běží uvnitř vašeho .NET procesu, ideální pro cloud nebo CI pipeline.  

## Předpoklady

Než začneme, ujistěte se, že máte:

- **Aspose.Zip pro .NET** nainstalovaný (stáhněte z oficiální [Aspose.Zip dokumentace](https://reference.aspose.com/zip/net/)).  
- Složku obsahující soubory, které chcete archivovat. V níže uvedených příkladech je tato složka odkazována proměnnou `dataDir`.  
- Platnou licenci Aspose.Zip (volitelnou pro hodnocení, povinnou pro produkci).

## Importujte jmenné prostory

Nejprve importujte jmenné prostory, které poskytují funkčnost TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak přidat soubory do tar pomocí Aspose.Zip

### Krok 1: Inicializujte `TarArchive`

Vytvořte novou instanci `TarArchive`, která bude obsahovat soubory, jež chcete komprimovat.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Tip:** `using` příkaz zajišťuje, že archiv je řádně uvolněn a uvolní jakékoli neřízené prostředky.

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

> **Výsledek:** Nyní máte plně komprimovaný soubor `archive.tar.xz`, který lze přenášet, ukládat nebo rozbalit na jakékoli platformě podporující TarXz.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **“File not found” exception** | Nesprávná cesta `dataDir` | Ověřte, že cesta končí zpětným lomítkem (`\`) nebo použijte `Path.Combine`. |
| **Large memory usage** | Velmi velké soubory jsou komprimovány v paměti | Použijte `TarArchive` ve streamovacím režimu (přetížení `SaveXzCompressed`, které přijímá `Stream`). |
| **License not applied** | Chybějící licenční soubor | Načtěte licenci při startu aplikace: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET prostředími?**  
A: Ano, Aspose.Zip funguje s .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6+. Podrobnosti najdete v [dokumentaci](https://reference.aspose.com/zip/net/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Zip?**  
A: Dočasnou licenci můžete požádat na [stránce dočasných licencí Aspose](https://purchase.aspose.com/temporary-license/).

**Q: Existují další příklady pro jiné formáty archivů?**  
A: Samozřejmě — prozkoumejte kompletní sadu příkladů v [referenci API Aspose.Zip](https://reference.aspose.com/zip/net/).

**Q: Kde mohu získat pomoc nebo diskutovat o problémech?**  
A: Připojte se k diskuzi na [fóru Aspose.Zip](https://forum.aspose.com/c/zip/37) pro komunitní podporu a oficiální odpovědi.

**Q: Můžu si Aspose.Zip vyzkoušet zdarma před zakoupením?**  
A: Ano, k dispozici je bezplatná zkušební verze na [stránce ke stažení Aspose.Zip](https://releases.aspose.com/zip/net).

## Závěr

Po absolvování výše uvedených kroků nyní víte, **jak přidat soubory do tar** a **vytvořit tarxz archivy** pomocí Aspose.Zip v .NET. Tento přístup vám poskytne kompaktní, přenosný balíček, který lze snadno začlenit do jakéhokoli .NET workflow — ať už vytváříte desktopový nástroj, webovou službu nebo automatizovanou CI/CD pipeline.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}