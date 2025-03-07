---
title: Komprimujte soubory pomocí FileInfo v Aspose.Zip pro .NET
linktitle: Komprimujte soubory pomocí FileInfo
second_title: Aspose.Zip .NET API pro kompresi a archivaci souborů
description: Naučte se komprimovat soubory pomocí fileinfo s Aspose.Zip pro .NET. Postupujte podle našeho podrobného průvodce pro efektivní správu souborů.
weight: 11
url: /cs/net/file-compression/compress-files-fileinfo/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Komprimujte soubory pomocí FileInfo v Aspose.Zip pro .NET

## Úvod

Vítejte v našem komplexním průvodci komprimací souborů pomocí Aspose.Zip pro .NET! Pokud hledáte optimalizaci ukládání nebo přenosu souborů, Aspose.Zip je vaším řešením. V tomto tutoriálu vás provedeme procesem komprimace souborů pomocí třídy FileInfo a poskytneme podrobného průvodce krok za krokem. Pojďme se ponořit!

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Zip for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Zip. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/zip/net/).

2. Adresář dokumentů: Nastavte v systému adresář pro ukládání souborů, které chcete komprimovat.

## Importovat jmenné prostory

Ve svém projektu .NET zahrňte potřebné jmenné prostory:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Krok 1: Nastavte adresář dokumentů

Nejprve definujte adresář, kde jsou uloženy vaše dokumenty. Můžete použít následující kód:

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Komprimujte soubory pomocí FileInfo

 Nyní pojďme k jádru procesu. Použijeme`FileInfo` třídy spolu s Aspose.Zip pro kompresi souborů. Následuj tyto kroky:

### Krok 2.1: Otevřete soubor ZIP

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Krok 2.2: Vytvořte objekty FileInfo

 Vytvořit`FileInfo` objekty pro soubory, které chcete komprimovat:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### Krok 2.3: Vytvořte archiv a přidejte položky

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Krok 2.4: Uložte soubor ZIP

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Gratulujeme! Úspěšně jste komprimovali soubory pomocí třídy FileInfo v Aspose.Zip pro .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak efektivně komprimovat soubory pomocí Aspose.Zip pro .NET. Pomocí těchto kroků můžete zlepšit možnosti správy souborů a optimalizovat využití místa. Experimentujte s různými typy a velikostmi souborů a zažijte plný potenciál Aspose.Zip.

## FAQ

### Q1: Je Aspose.Zip kompatibilní se všemi typy souborů?

A1: Aspose.Zip podporuje širokou škálu typů souborů, což zajišťuje všestrannost v kompresi.

### Q2: Mohu použít Aspose.Zip pro komerční projekty?

 A2: Rozhodně! Navštivte naši[nákupní stránku](https://purchase.aspose.com/buy) prozkoumat možnosti licencování.

### Q3: Jak mohu získat podporu pro Aspose.Zip?

 A3: Připojte se k naší komunitě na[Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) za pomoc a diskuze.

### Q4: Je k dispozici bezplatná zkušební verze?

 A4: Ano, můžete si vzít své[zkušební verze zdarma zde](https://releases.aspose.com/).

### Q5: Jak mohu získat dočasnou licenci pro Aspose.Zip?

 A5: Návštěva[tento odkaz](https://purchase.aspose.com/temporary-license/) informace o získání dočasné licence.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
