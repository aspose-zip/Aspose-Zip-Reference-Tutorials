---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip több fájlt C#-ban az Aspose.Zip párhuzamos tömörítéssel

## Bevezetés

Ha gyorsan és hatékonyan kell **zip multiple files c#** elvégezni, a párhuzamos feldolgozás kihasználása a megfelelő út. A modern .NET alkalmazásokban a nagy zip archívumok létrehozása szűk keresztmetszetté válhat – különösen, ha tucatnyi vagy akár több száz fájlról van szó. Az Aspose.Zip for .NET ezt a problémát a beépített **parallel zip compression** segítségével oldja meg, amely a munkát az összes elérhető CPU magra osztja. Ebben az útmutatóban végigvezetjük a teljes folyamatot: a környezet beállításától a párhuzamosítással mentett zip archívum létrehozásáig, és megmutatjuk, hogyan **create zip archive c#** készíthető .NET Core környezetben is zökkenőmentesen.

## Gyors válaszok
- **Mi a párhuzamos zip tömörítés?** Több fájlt tömörít egyszerre, több szál használatával csökkentve a teljes feldolgozási időt.  
- **Mely .NET könyvtár támogatja?** Az Aspose.Zip for .NET egyszerű API-t biztosít a párhuzamos tömörítéshez.  
- **Szükségem van licencre a termeléshez?** Igen – teljes licenc szükséges; teszteléshez ideiglenes licenc is elérhető.  
- **Hozzáadhatok fájlokat a zip-hez menet közben?** Természetesen – használja a `Archive.CreateEntry`-t minden hozzáadni kívánt fájlhoz.  
- **Kompatibilis a .NET 6/7-tel?** Igen, az API minden modern .NET futtatókörnyezettel működik.

## Mi a zip multiple files c#?
`zip multiple files c#` a gyakorlatot jelenti, amikor egyetlen ZIP archívumot hozunk létre, amely sok egyedi fájlt tartalmaz, C# kóddal. Ha ezt kombinálja a **parallel zip compression**-nel, a könyvtár minden fájlt külön szálon dolgoz fel, drámai módon csökkentve a végső archívum elkészítéséhez szükséges időt.

## Miért használja az Aspose.Zip-et párhuzamos tömörítéshez?
Párhuzamos tömörítés lehetővé teszi, hogy kihasználja egy többmagos gép minden magját, gyakran **2‑3× gyorsabb** áteresztőképességet biztosítva, mint az egy szálas megközelítés. Emellett elegánsan skálázódik: több fájl hozzáadása nem növeli lineárisan a CPU időt, és az API kezeli a szálkezelést Ön helyett, így a üzleti logikára koncentrálhat.

- **Sebesség:** Kihasználja az összes logikai processzort, csökkentve a zip létrehozási időt akár 70 %-kal tipikus terhelések esetén.  
- **Skálázhatóság:** Kezeli az 500+ fájlból álló csomagokat anélkül, hogy a CPU idő arányosan nőne.  
- **Egyszerűség:** Magas szintű metódusok elrejtik a `System.Threading.Tasks` komplexitását.  
- **Rugalmasság:** Támogatja a .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, valamint a .NET 5–10 verziókat, beleértve a .NET 6/7-et is a felhő‑natív szolgáltatásokhoz.

## Előkövetelmények

Mielőtt belemerülnénk, győződjön meg róla, hogy rendelkezik:
- Alapvető C# és .NET fejlesztési ismeretekkel.  
- Aspose.Zip for .NET telepítve. Letöltheti **[itt](https://releases.aspose.com/zip/net/)**.  
- Ideiglenes vagy teljes licenccel (az ideiglenes licenc elegendő ehhez az útmutatóhoz).

## Névterek importálása

`Aspose.Zip` névtér tartalmazza az összes típust, amelyre a ZIP archívumok kezeléséhez szüksége van.

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Először hozza be a szükséges névtereket a C# fájljába, hogy a fordító tudja, hol találja a használandó osztályokat.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## 1. lépés: Dokumentumkönyvtár beállítása

Határozza meg azt a mappát, amely a tömöríteni kívánt fájlokat tartalmazza. Ez az útvonal a `dataDir` változóban van tárolva, amelyet bármely lemezhelyre mutathat.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## 2. lépés: A tömörítési folyamat inicializálása

Nyisson egy új ZIP fájlt írásra. A `using` utasítás biztosítja, hogy a fájlfolyam a művelet után megfelelően felszabaduljon, megakadályozva a fájl‑kezelő szivárgásokat.

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

## 3. lépés: Fájlok olvasása és tömörítése párhuzamosan

`Parallel.ForEach` egy foreach ciklust hajt végre, amelyben az iterációk több szálon párhuzamosan futtathatók.  

Nyissa meg minden forrásfájlt, amelyet a archívumba kíván felvenni. Ebben a példában két klasszikus szöveggel dolgozunk, de bármennyi dokumentumhoz **add files to zip** használhat. A `Parallel.ForEach` ciklus automatikusan elosztja a munkát a szálak között.

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

## 4. lépés: Archívum bejegyzések létrehozása

`Archive` osztály az Aspose.Zip legfelső szintű objektuma, amely a létrehozandó ZIP konténert képviseli.  

A `CreateEntry` új bejegyzést hoz létre a ZIP archívumban egy megadott fájlhoz. Minden `CreateEntry` hívás egy új fájlbejegyzést ad az archívumhoz.

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

## 5. lépés: Párhuzamossági kritérium meghatározása

`ParallelOptions` egy .NET típus, amely szabályozza, hogyan hajtódnak végre a párhuzamos ciklusok.  

Állítsa be a tömörítést párhuzamosan futtatásra a `ParallelOptions` beállításával. A `ParallelCompressInMemory` jelző azt mondja az Aspose.Zip-nek, hogy mindig használja a párhuzamos feldolgozást, míg a `MaxDegreeOfParallelism` lehetővé teszi a párhuzamos szálak számának korlátozását.

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

## 6. lépés: A tömörített archívum mentése

Végül írja az archívumot lemezre a kívánt beállításokkal, beleértve a kódolást, egy megjegyzést és a korábban meghatározott párhuzamos beállításokat. A `Save` metódus befejezi a ZIP fájlt.

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

> **Pro tip:** Ha nagyon nagy fájlokat tömörít, fontolja meg a `ParallelOptions.MaxDegreeOfParallelism` beállítását a logikai processzorok számánál alacsonyabb értékre. Ez segít a szerver terhelés alatt is válaszkész maradni.

### Gyakori felhasználási esetek

- **Kötegelt jelentés:** Napi CSV jelentések zip csomagjának generálása az alrendszerek számára.  
- **Dokumentum archiválás:** Nagy PDF, kép vagy naplógyűjtemények tárolása egyetlen archívumban biztonsági mentésként.  
- **Adat export API-k:** Egy zip fájl visszaadása, amely több adatfájlt tartalmaz, egyetlen HTTP válaszban a kliensnek.  

## Gyakori problémák és tippek

- **Memória nyomás hatalmas fájlok esetén:** A teljes fájl memóriába töltése helyett streamelje a fájlt darabokban, vagy szelektíven használja a `ParallelCompressInMemory` módot.  
- **Szálbiztonság:** Az Aspose.Zip API szálbiztos a párhuzamos módban, de kerülje el ugyanannak a `FileStream`-nek a könyvtáron kívüli módosítását a tömörítés közben.  
- **Teljesítményhangolás:** Kísérletezzen a `ParallelOptions.MaxDegreeOfParallelism` beállítással, ha korlátozni kell a CPU használatot megosztott szervereken.  

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Zip for .NET-et más tömörítő könyvtárakkal együtt?**  
A: Igen, az Aspose.Zip együtt élhet más .NET könyvtárakkal; csak tartsa külön a névtereiket.

**Q: Ideiglenes licenc elérhető teszteléshez?**  
A: Igen, ideiglenes licencet kaphat teszteléshez **[itt](https://purchase.aspose.com/temporary-license/)**.

**Q: Hol kérhetek segítséget, ha problémába ütközöm?**  
A: Látogassa meg az **[Aspose.Zip fórumot](https://forum.aspose.com/c/zip/37)** a közösségi támogatás és megbeszélésekért.

**Q: Hol találok további kódpéldákat és részletes API dokumentációt?**  
A: Fedezze fel az **[Aspose.Zip dokumentációt](https://reference.aspose.com/zip/net/)** a részletes példákért.

**Q: Hogyan vásárolhatok teljes licencet az Aspose.Zip-hez?**  
A: Megvásárolhatja az Aspose.Zip for .NET **[itt](https://purchase.aspose.com/buy)**.

---

**Legutóbb frissítve:** 2026-06-09  
**Tesztelt verzió:** Aspose.Zip 24.11 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [zip multiple files c# – Gondtalan tömörítés Aspose.Zip for .NET használatával](/zip/net/file-compression/compress-multiple-files/)
- [Hogyan hozzunk létre zip archívumot és adjunk hozzá fájlt a zip-hez Aspose.Zip for .NET használatával](/zip/net/file-compression/compress-single-file/)
- [Több fájl tömörítése titkosítással az Aspose.Zip .NET-ben](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}