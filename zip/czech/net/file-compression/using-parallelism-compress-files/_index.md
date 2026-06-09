---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip více souborů c# s Aspose.Zip Parallel Compression

## Úvod

Pokud potřebujete **zip více souborů c#** rychle a efektivně, využití paralelního zpracování je správná cesta. V moderních .NET aplikacích může vytváření velkých zip archivů představovat úzké hrdlo—zejména při práci s desítkami nebo stovkami souborů. Aspose.Zip pro .NET odstraňuje tento problém tím, že nabízí vestavěnou **parallel zip compression**, která rozkládá práci na všechny dostupné jádra CPU. V tomto tutoriálu projdeme celý proces: od nastavení prostředí po uložení zip archivu s povoleným paralelismem, a také vám ukážeme, jak **vytvořit zip archiv c#**, který běží hladce na .NET Core.

## Rychlé odpovědi
- **Co je parallel zip compression?** Komprimuje několik souborů najednou pomocí více vláken, čímž zkracuje celkový čas zpracování.  
- **Která .NET knihovna to podporuje?** Aspose.Zip pro .NET poskytuje jednoduché API pro paralelní kompresi.  
- **Potřebuji licenci pro produkci?** Ano—vyžaduje se plná licence; dočasná licence je k dispozici pro testování.  
- **Mohu přidávat soubory do zipu za běhu?** Určitě—použijte `Archive.CreateEntry` pro každý soubor, který chcete zahrnout.  
- **Je kompatibilní s .NET 6/7?** Ano, API funguje na všech moderních .NET runtimech.

## Co je zip více souborů c#?
`zip multiple files c#` odkazuje na praxi vytváření jediného ZIP archivu, který obsahuje mnoho jednotlivých souborů, pomocí C# kódu. Když to spojíte s **parallel zip compression**, knihovna zpracovává každý soubor v samostatném vlákně, což dramaticky snižuje čas potřebný k vytvoření finálního archivu.

## Proč použít Aspose.Zip pro paralelní kompresi?
Paralelní komprese vám umožní využít každé jádro víceprocesorového stroje a často poskytuje **2‑3× vyšší** propustnost než jednovláknový přístup. Také se elegantně škáluje: přidání více souborů nezvyšuje lineárně čas na zdi a API za vás spravuje vlákna, takže se můžete soustředit na obchodní logiku.  

- **Speed:** Využívá všechny logické procesory, snižuje čas tvorby zipu až o 70 % při typických pracovních zatíženích.  
- **Scalability:** Zvládá dávky 500+ souborů bez úměrného nárůstu času CPU.  
- **Simplicity:** Vysoceúrovňové metody skrývají složitost `System.Threading.Tasks`.  
- **Flexibility:** Podporuje .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 a .NET 5–10, včetně .NET 6/7 pro cloud‑native služby.

## Požadavky

Než se pustíme dál, ujistěte se, že máte:
- Základní znalosti C# a vývoje v .NET.  
- Aspose.Zip pro .NET nainstalovaný. Můžete si jej stáhnout **[zde](https://releases.aspose.com/zip/net/)**.  
- Dočasnou nebo plnou licenci (dočasná licence stačí pro tento tutoriál).  

## Importovat jmenné prostory

Jmenný prostor `Aspose.Zip` obsahuje všechny typy, které potřebujete pro práci se ZIP archivy.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Nejprve přidejte požadované jmenné prostory do vašeho C# souboru, aby kompilátor věděl, kde najít třídy, které budete používat.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Krok 1: Nastavte adresář dokumentů

Definujte složku, která obsahuje soubory, které chcete komprimovat. Tato cesta je uložena v proměnné `dataDir`, kterou můžete nasměrovat na libovolné místo na disku.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Inicializovat proces komprese

Otevřete nový ZIP soubor pro zápis. Příkaz `using` zajišťuje, že souborový stream je po operaci řádně uvolněn, čímž se předchází únikům souborových handle.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Krok 3: Číst a komprimovat soubory paralelně

`Parallel.ForEach` provádí smyčku foreach, kde se iterace mohou spouštět souběžně na více vláknech.  

Otevřete každý zdrojový soubor, který chcete přidat do archivu. V tomto příkladu pracujeme se dvěma klasickými texty, ale můžete **přidávat soubory do zipu** pro libovolný počet dokumentů. Smyčka `Parallel.ForEach` automaticky rozděluje práci mezi vlákna.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Krok 4: Vytvořit položky archivu

Třída `Archive` je nejvyšší objekt Aspose.Zip, který představuje ZIP kontejner, který budujete.  

`CreateEntry` vytvoří novou položku v ZIP archivu pro zadaný soubor. Každé volání `CreateEntry` přidá novou souborovou položku do archivu.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Krok 5: Definovat kritérium paralelismu

`ParallelOptions` je typ v .NET, který řídí, jak jsou paralelní smyčky vykonávány.  

Nastavte kompresi tak, aby běžela paralelně nastavením `ParallelOptions`. Příznak `ParallelCompressInMemory` říká Aspose.Zip, aby vždy používal paralelní zpracování, zatímco `MaxDegreeOfParallelism` vám umožní omezit počet souběžných vláken.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Krok 6: Uložit komprimovaný archiv

Nakonec zapište archiv na disk s požadovanými možnostmi, včetně kódování, komentáře a dříve definovaných paralelních nastavení. Metoda `Save` dokončí ZIP soubor.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** Pokud komprimujete velmi velké soubory, zvažte nastavení `ParallelOptions.MaxDegreeOfParallelism` na hodnotu nižší než počet logických procesorů. To pomáhá udržet server responsivní pod zatížením.

### Běžné případy použití

- **Batch reporting:** Vytvořte zip balíček denních CSV reportů pro podřadné systémy.  
- **Document archiving:** Uložte velké kolekce PDF, obrázků nebo logů do jednoho archivu pro zálohování.  
- **Data export APIs:** Vrátit zip soubor obsahující více datových souborů klientovi v jedné HTTP odpovědi.  

## Běžné problémy a tipy

- **Memory pressure on huge files:** Místo načítání celého souboru do paměti streamujte soubor po částech nebo použijte režim `ParallelCompressInMemory` selektivně.  
- **Thread safety:** API Aspose.Zip je pro paralelní režim bezpečné pro vlákna, ale vyhněte se úpravám stejného `FileStream` zvenčí knihovny během běhu komprese.  
- **Performance tuning:** Experimentujte s `ParallelOptions.MaxDegreeOfParallelism`, pokud potřebujete omezit využití CPU na sdílených serverech.  

## Často kladené otázky

**Q: Můžu použít Aspose.Zip pro .NET spolu s jinými kompresními knihovnami?**  
A: Ano, Aspose.Zip může koexistovat s jinými .NET knihovnami; stačí udržovat jejich jmenné prostory oddělené.

**Q: Je k dispozici dočasná licence pro testovací účely?**  
A: Ano, dočasnou licenci pro testování můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Kde se mohu zeptat na pomoc, pokud narazím na problémy?**  
A: Navštivte **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** pro podporu komunity a diskuze.

**Q: Kde najdu více příkladů kódu a podrobné API dokumentace?**  
A: Prozkoumejte **[dokumentaci Aspose.Zip](https://reference.aspose.com/zip/net/)** pro komplexní příklady.

**Q: Jak si mohu zakoupit plnou licenci pro Aspose.Zip?**  
A: Aspose.Zip pro .NET můžete zakoupit **[zde](https://purchase.aspose.com/buy)**.

---

**Poslední aktualizace:** 2026-06-09  
**Testováno s:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [zip multiple files c# – Snadná komprese s Aspose.Zip pro .NET](/zip/net/file-compression/compress-multiple-files/)
- [Jak vytvořit zip archiv a přidat soubor do zipu pomocí Aspose.Zip pro .NET](/zip/net/file-compression/compress-single-file/)
- [Komprimovat více souborů s šifrováním v Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}