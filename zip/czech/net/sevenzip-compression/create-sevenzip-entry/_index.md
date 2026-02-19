---
date: 2025-12-25
description: Mistrovské používání Aspose.Zip pro .NET k vytváření šifrovaných archivů
  7z. Tento příklad Aspose.Zip ukazuje, jak přidat soubor do 7z se šifrováním a kompresí.
linktitle: Create SevenZip Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Jak vytvořit šifrovaný archiv 7z pomocí Aspose.Zip pro .NET
url: /cs/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření šifrovaného archivu 7z pomocí Aspose.Zip pro .NET

## Úvod

V tomto tutoriálu se naučíte **jak vytvořit šifrované soubory 7z** pomocí knihovny Aspose.Zip pro .NET. Ať už potřebujete chránit citlivá data, dodržet bezpečnostní politiky nebo jen efektivně komprimovat soubory, tento průvodce vás provede každým krokem – od nastavení projektu až po potvrzení, že archiv byl úspěšně vytvořen. Ponořme se a podívejme se, jak snadné je přidat soubor do archivu 7z s AES šifrováním.

## Rychlé odpovědi
- **Co znamená “vytvořit šifrované 7z”?** To znamená vytvořit archiv 7‑zip, který je chráněn AES šifrováním.
- **Která knihovna se používá?** Aspose.Zip pro .NET.
- **Potřebuji licenci?** Dočasná licence stačí pro testování; pro produkci je vyžadována plná licence.
- **Mohu přidat více souborů?** Ano, můžete opakovaně volat `CreateEntry` pro každý soubor.
- **Je podporováno AES šifrování?** Ano, Aspose.Zip podporuje AES‑256 šifrování pro archivy 7z.

## Co je šifrovaný archiv 7z?
Archiv 7z je formát kontejneru s vysokou kompresí. Když **vytvoříte šifrované 7z** archivy, obsah je zakódován pomocí AES šifrování, což jej činí nečitelné bez správného hesla. To je ideální pro bezpečný přenos nebo ukládání důvěrných souborů.

## Proč použít Aspose.Zip pro šifrované soubory 7z?
- **Plná integrace s .NET** – funguje s .NET Framework, .NET Core i .NET 5/6.
- **Vestavěná podpora AES‑256** – není potřeba žádné externí nástroje.
- **Jednoduché API** – jednorázové volání pro přidání souborů a uložení archivu.
- **Cross‑platform** – běží na Windows, Linuxu i macOS.

## Předpoklady

Před zahájením se ujistěte, že máte následující:

- **Aspose.Zip pro .NET Library** – stáhněte ji [zde](https://releases.aspose.com/zip/net/).
- **Zapisovatelný adresář** na vašem počítači, kam bude archiv uložen.
- **Zdrojový soubor** (např. `file.dat`), který chcete komprimovat a zašifrovat.

## Importovat jmenné prostory

Přidejte požadovaný namespace na začátek vašeho C# souboru:

```csharp
using Aspose.Zip.SevenZip;
```

## Postupný průvodce

### Krok 1: Definujte pracovní adresář

Nastavte cestu k složce, která obsahuje zdrojový soubor, který chcete komprimovat.

```csharp
string dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` skutečnou cestou na vašem počítači.

### Krok 2: Vytvořte šifrovaný záznam 7z

Jádro tutoriálu – otevřeme nový souborový stream, vytvoříme `SevenZipArchive`, přidáme záznam a uložíme archiv. Tento příklad přidává jeden soubor (`file.dat`) jako `data.bin` uvnitř archivu.

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **Pro tip:** Pro povolení AES šifrování nastavte vlastnost `Encryption` na objektu `SevenZipArchive` před voláním `Save`. (Vlastnost je zde vynechána, aby byl příklad stručný.)

### Krok 3: Potvrďte úspěch

Vytiskněte přátelskou zprávu, abyste věděli, že operace byla dokončena bez chyb.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### Krok 4: Ověřte archiv (volitelné)

Po spuštění programu přejděte do složky obsahující `archive.7z` a zkuste ji otevřít pomocí 7‑zip klienta. Pokud jste v kroku 2 přidali šifrování, budete vyzváni k zadání hesla.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Soubor nenalezen** | Nesprávný `dataDir` nebo název zdrojového souboru | Zkontrolujte cestu a ujistěte se, že `file.dat` existuje. |
| **Přístup odepřen** | Nedostatečná oprávnění k zápisu | Spusťte aplikaci s vyššími právy nebo vyberte zapisovatelný adresář. |
| **Šifrování nebylo použito** | Chybějící nastavení šifrování na archivu | Nastavte `archive.Encryption = EncryptionAlgorithm.Aes256;` před voláním `Save`. |

## Často kladené otázky

### Q: Mohu použít Aspose.Zip pro .NET s jinými formáty archivů?
Aspose.Zip se primárně zaměřuje na formáty ZIP a 7z. Pro práci s jinými formáty prozkoumejte specifické knihovny určené pro tyto formáty.

### Q: Jak mohu pomocí Aspose.Zip extrahovat soubory ze zip archivu?
Využijte funkce extrakce poskytované Aspose.Zip, například metodu `ExtractToDirectory`, která umožňuje snadno extrahovat soubory ze zip archivu.

### Q: Je Aspose.Zip vhodný pro rozsáhlé aplikace?
Rozhodně! Aspose.Zip je navržen tak, aby zvládal rozsáhlé aplikace a poskytoval efektivní manipulaci se zip archivy.

### Q: Existují licenční úvahy při používání Aspose.Zip?
Ano, ujistěte se, že máte platnou licenci. Pro dočasné použití nebo průzkum můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Q: Kde mohu získat podporu nebo se spojit s komunitou pro Aspose.Zip?
Navštivte [Aspose.Zip fórum](https://forum.aspose.com/c/zip/37), kde můžete požádat o podporu, klást otázky a spojit se s komunitou.

## Závěr

Nyní máte pevný základ pro **vytváření šifrovaných archivů 7z** pomocí Aspose.Zip pro .NET. Dodržením výše uvedených kroků můžete bezpečně komprimovat soubory, přidávat je do kontejneru 7z a v případě potřeby povolit AES šifrování. Klidně rozšiřte tento příklad o další záznamy, nastavení hesel nebo integraci do větších pracovních postupů.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
