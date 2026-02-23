---
date: 2026-02-23
description: Naučte se, jak přidávat soubory do tar a komprimovat soubory do archivu
  tarxz v .NET pomocí Aspose.Zip. Postupujte podle tohoto krok‑za‑krokem průvodce
  pro efektivní ukládání a přenos.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Přidat soubory do tar a vytvořit archiv tarxz pomocí Aspose.Zip
url: /cs/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

 unchanged.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání souborů do tar a vytvoření archivu tarxz pomocí Aspose.Zip

## Úvod

Pokud potřebujete **přidat soubory do tar** a poté **vytvořit tarxz archiv .net**, Aspose.Zip pro .NET proces zjednodušuje a činí jej spolehlivým. Ať už balíte logy, konfigurační soubory nebo jakékoli jiné zdroje pro ukládání či přenos, komprese do formátu TarXz vám poskytne vysoký kompresní poměr při zachování známé struktury tar. V tomto tutoriálu projdeme přesné kroky – včetně úryvků kódu – abyste mohli s jistotou integrovat tvorbu tarxz do svých .NET aplikací.

## Rychlé odpovědi
- **Jaká je hlavní třída?** `TarArchive` z `Aspose.Zip.Tar`
- **Jak komprimovat tarxz?** Použijte `SaveXzCompressed` po přidání položek
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Je licence potřeba?** Ano, platná licence Aspose.Zip pro produkci
- **Typická doba implementace?** ~5‑10 minut

## Co je archiv TarXz?

**TarXz archiv** kombinuje tradiční Unixový kontejner `tar` s XZ kompresí. Část tar seskupí více souborů do jednoho proudu, zatímco XZ poskytuje silnou bezztrátovou kompresi. Tento formát je populární pro distribuci zdrojového kódu, záloh a velkých datových sad, protože zachovává adresářové struktury a dosahuje menších velikostí souborů než běžný tar nebo zip.

## Proč vytvářet tarxz archiv .net pomocí Aspose.Zip?

- **Vysoký kompresní poměr** – XZ často komprimuje o 30‑50 % méně než gzip.  
- **Kompatibilita napříč platformami** – soubory TarXz lze otevřít na Linuxu, macOS a Windows.  
- **Jednoduché API** – Aspose.Zip abstrahuje nízkoúrovňové detaily, takže se můžete soustředit na svou obchodní logiku.  
- **Žádné externí nástroje** – vše běží uvnitř vašeho .NET procesu, ideální pro cloud nebo CI pipeline.

## Požadavky

Před začátkem se ujistěte, že máte:

- **Aspose.Zip for .NET** nainstalován (stáhněte z oficiální [Aspose.Zip dokumentace](https://reference.aspose.com/zip/net/)).  
- Složku obsahující soubory, které chcete archivovat. V níže uvedených příkladech je tato složka odkazována proměnnou `dataDir`.  
- Platnou licenci Aspose.Zip (volitelně pro hodnocení, povinně pro produkci).

## Importujte jmenné prostory

Nejprve importujte jmenné prostory, které zpřístupňují funkčnost TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Jak přidat soubory do tar pomocí Aspose.Zip

Níže je krok‑za‑krokem průvodce, který přesně ukazuje, jak **přidat soubory do tar** před jejich kompresí.

### Krok 1: Inicializujte `TarArchive`

Vytvořte novou instanci `TarArchive`, která bude obsahovat soubory, které chcete komprimovat.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Tip:** Příkaz `using` zajišťuje, že archiv je řádně uvolněn, čímž uvolní jakékoli neřízené prostředky.

### Krok 2: Přidejte soubory do archivu

Přidejte každý soubor, který chcete zahrnout. V tomto příkladu přidáváme dva textové soubory, ale můžete přidat libovolný počet položek.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Proč je to důležité:** Přidání položek před kompresí umožňuje Aspose.Zip nejprve vytvořit tar kontejner a poté aplikovat XZ kompresi v jediném kroku.

### Krok 3: Uložte archiv s XZ kompresí

Nakonec zapište tar archiv na disk s XZ kompresí. Výsledný soubor bude mít příponu `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Výsledek:** Nyní máte plně komprimovaný soubor `archive.tar.xz`, který lze přenášet, ukládat nebo rozbalovat na jakékoli platformě, která podporuje TarXz.

## Jak komprimovat tarxz soubory pomocí Aspose.Zip

Proces uvedený výše je v podstatě **jak komprimovat tarxz** soubory: nejprve přidáte soubory do tar kontejneru (`add files to tar`) a poté zavoláte `SaveXzCompressed`. Tento jednorázový přístup eliminuje potřebu externích nástrojů příkazové řádky a vše zůstane uvnitř vašeho .NET kódu.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| **“File not found” výjimka** | Nesprávná cesta `dataDir` | Ověřte, že cesta ke složce končí zpětným lomítkem (`\`) nebo použijte `Path.Combine`. |
| **Vysoké využití paměti** | Velmi velké soubory komprimované v paměti | Použijte `TarArchive` v režimu streamování (`SaveXzCompressed` přetížení, které přijímá `Stream`). |
| **Licence nebyla použita** | Chybějící soubor licence | Načtěte licenci při startu aplikace: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Často kladené otázky

**Q: Je Aspose.Zip kompatibilní se všemi .NET prostředími?**  
A: Ano, Aspose.Zip funguje s .NET Framework 4.5+, .NET Core 3.1+, a .NET 5/6+. Podívejte se na [dokumentaci](https://reference.aspose.com/zip/net/) pro podrobnosti.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Zip?**  
A: Dočasnou licenci můžete požádat na [stránce dočasných licencí Aspose](https://purchase.aspose.com/temporary-license/).

**Q: Existují další příklady pro jiné formáty archivů?**  
A: Rozhodně – prozkoumejte kompletní sadu příkladů v [referenci API Aspose.Zip](https://reference.aspose.com/zip/net/).

**Q: Kde mohu získat pomoc nebo diskutovat o problémech?**  
A: Připojte se k diskuzi na [fóru Aspose.Zip](https://forum.aspose.com/c/zip/37) pro podporu komunity a oficiální odpovědi.

**Q: Můžu si Aspose.Zip vyzkoušet zdarma před zakoupením?**  
A: Ano, bezplatná zkušební verze je k dispozici na [stahovací stránce Aspose.Zip](https://releases.aspose.com/zip/net).

## Závěr

Po provedení výše uvedených kroků nyní víte **jak přidat soubory do tar** a **komprimovat tarxz** soubory, a co je důležitější, **jak vytvořit tarxz archiv .net** pomocí Aspose.Zip. Tento přístup vám poskytuje kompaktní, přenosný balíček, který lze snadno začlenit do jakéhokoli .NET workflow – ať už vytváříte desktopovou utilitu, webovou službu nebo automatizovaný CI/CD pipeline.

---

**Poslední aktualizace:** 2026-02-23  
**Testováno s:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}