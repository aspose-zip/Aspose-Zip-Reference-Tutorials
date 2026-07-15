---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip meerdere bestanden c# met Aspose.Zip Parallelle Compressie

## Introductie

Als je **zip meerdere bestanden c#** snel en efficiënt wilt, is het benutten van parallelle verwerking de juiste aanpak. In moderne .NET‑toepassingen kan het maken van grote zip‑archieven een knelpunt worden—vooral bij tientallen of honderden bestanden. Aspose.Zip voor .NET verwijdert dat probleem door ingebouwde **parallelle zip‑compressie** aan te bieden die het werk verdeelt over alle beschikbare CPU‑kernen. In deze tutorial lopen we het volledige proces door: van het opzetten van de omgeving tot het opslaan van een zip‑archief met ingeschakelde paralleliteit, en we laten je ook zien hoe je **zip‑archief maakt c#** dat soepel draait op .NET Core.

## Snelle Antwoorden
- **Wat is parallelle zip‑compressie?** Het comprimeert meerdere bestanden tegelijk, met meerdere threads om de totale verwerkingstijd te verkorten.  
- **Welke .NET‑bibliotheek ondersteunt dit?** Aspose.Zip voor .NET biedt een eenvoudige API voor parallelle compressie.  
- **Heb ik een licentie nodig voor productie?** Ja—een volledige licentie is vereist; een tijdelijke licentie is beschikbaar voor testen.  
- **Kan ik bestanden on‑the‑fly aan een zip toevoegen?** Absoluut—gebruik `Archive.CreateEntry` voor elk bestand dat je wilt opnemen.  
- **Is het compatibel met .NET 6/7?** Ja, de API werkt op alle moderne .NET‑runtime‑omgevingen.

## Wat is zip meerdere bestanden c#?
`zip multiple files c#` verwijst naar de praktijk van het maken van één ZIP‑archief dat veel individuele bestanden bevat, met C#‑code. Wanneer je dit combineert met **parallelle zip‑compressie**, verwerkt de bibliotheek elk bestand op een aparte thread, waardoor de tijd die nodig is om het uiteindelijke archief te produceren drastisch wordt verkort.

## Waarom Aspose.Zip gebruiken voor parallelle compressie?
Parallelle compressie stelt je in staat om elke kern van een multi‑processor machine te benutten, vaak een **2‑3× snellere** doorvoer leverend dan een single‑threaded aanpak. Het schaalt ook soepel: meer bestanden toevoegen verhoogt de kloktijd niet lineair, en de API regelt het thread‑beheer voor je, zodat je je kunt concentreren op de bedrijfslogica.  

- **Snelheid:** Gebruikt alle logische processors, waardoor de tijd voor het maken van een zip tot wel 70 % wordt verkort bij typische workloads.  
- **Schaalbaarheid:** Verwerkt batches van 500+ bestanden zonder een evenredige stijging in CPU‑tijd.  
- **Eenvoud:** High‑level methoden verbergen de complexiteit van `System.Threading.Tasks`.  
- **Flexibiliteit:** Ondersteunt .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, en .NET 5–10, inclusief .NET 6/7 voor cloud‑native services.

## Vereisten

- Basiskennis van C# en .NET‑ontwikkeling.  
- Aspose.Zip voor .NET geïnstalleerd. Je kunt het downloaden **[hier](https://releases.aspose.com/zip/net/)**.  
- Een tijdelijke of volledige licentie (de tijdelijke licentie is voldoende voor deze tutorial).  

## Namespaces importeren

De `Aspose.Zip` namespace bevat alle types die je nodig hebt om met ZIP‑archieven te werken.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Eerst, importeer de vereiste namespaces in je C#‑bestand zodat de compiler weet waar de klassen die je gebruikt te vinden zijn.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Stap 1: Stel je documentmap in

Definieer de map die de bestanden bevat die je wilt comprimeren. Dit pad wordt opgeslagen in de `dataDir`‑variabele, die je naar elke locatie op de schijf kunt wijzen.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Stap 2: Initialiseer het compressieproces

Open een nieuw ZIP‑bestand voor schrijven. De `using`‑statement zorgt ervoor dat de bestandsstroom correct wordt vrijgegeven na de bewerking, waardoor lekken van bestands‑handles worden voorkomen.

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

## Stap 3: Lees en comprimeer bestanden parallel

`Parallel.ForEach` voert een foreach‑lus uit waarbij iteraties gelijktijdig op meerdere threads kunnen draaien.  

Open elk bronbestand dat je aan het archief wilt toevoegen. In dit voorbeeld werken we met twee klassieke teksten, maar je kunt **bestanden aan een zip toevoegen** voor elk aantal documenten. De `Parallel.ForEach`‑lus verdeelt het werk automatisch over threads.

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

## Stap 4: Maak archief‑items aan

De `Archive`‑klasse is het top‑level object van Aspose.Zip dat de ZIP‑container vertegenwoordigt die je aan het bouwen bent.  

`CreateEntry` maakt een nieuw item aan in het ZIP‑archief voor een opgegeven bestand. Elke aanroep van `CreateEntry` voegt een nieuw bestand toe aan het archief.

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

## Stap 5: Definieer parallelisme‑criterium

`ParallelOptions` is een .NET‑type dat bepaalt hoe parallelle lussen worden uitgevoerd.  

Configureer de compressie om parallel te draaien door `ParallelOptions` in te stellen. De `ParallelCompressInMemory`‑vlag vertelt Aspose.Zip om altijd parallelle verwerking te gebruiken, terwijl `MaxDegreeOfParallelism` je in staat stelt het aantal gelijktijdige threads te beperken.

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

## Stap 6: Sla het gecomprimeerde archief op

Schrijf tenslotte het archief naar schijf met de gewenste opties, inclusief codering, een commentaar, en de eerder gedefinieerde parallelle instellingen. De `Save`‑methode finaliseert het ZIP‑bestand.

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

> **Pro tip:** Als je zeer grote bestanden comprimeert, overweeg dan om `ParallelOptions.MaxDegreeOfParallelism` in te stellen op een waarde lager dan het aantal logische processors. Dit helpt je server responsief te houden onder belasting.

### Veelvoorkomende gebruikssituaties

- **Batchrapportage:** Genereer een zip‑bundel van dagelijkse CSV‑rapporten voor downstream‑systemen.  
- **Documentarchivering:** Bewaar grote collecties van PDF’s, afbeeldingen of logbestanden in één archief voor backup.  
- **Data‑export‑API’s:** Retourneer een zip‑bestand met meerdere data‑bestanden aan een client in één HTTP‑respons.  

## Veelvoorkomende problemen & tips

- **Geheugendruk bij enorme bestanden:** In plaats van een heel bestand in het geheugen te laden, stream je het bestand in stukken of gebruik je de `ParallelCompressInMemory`‑modus selectief.  
- **Thread‑veiligheid:** De Aspose.Zip‑API is thread‑safe voor parallelle modus, maar vermijd het wijzigen van dezelfde `FileStream` buiten de bibliotheek terwijl compressie loopt.  
- **Prestatie‑afstemming:** Experimenteer met `ParallelOptions.MaxDegreeOfParallelism` als je het CPU‑gebruik op gedeelde servers moet beperken.  

## Veelgestelde vragen

**Q: Kan ik Aspose.Zip voor .NET samen met andere compressiebibliotheken gebruiken?**  
A: Ja, Aspose.Zip kan naast andere .NET‑bibliotheken bestaan; houd hun namespaces gewoon gescheiden.

**Q: Is er een tijdelijke licentie beschikbaar voor testdoeleinden?**  
A: Ja, je kunt een tijdelijke licentie voor testen verkrijgen via **[hier](https://purchase.aspose.com/temporary-license/)**.

**Q: Waar kan ik hulp vragen als ik tegen problemen aanloop?**  
A: Bezoek het **[Aspose.Zip‑forum](https://forum.aspose.com/c/zip/37)** voor community‑ondersteuning en discussies.

**Q: Waar kan ik meer code‑voorbeelden en gedetailleerde API‑documentatie vinden?**  
A: Bekijk de **[Aspose.Zip‑documentatie](https://reference.aspose.com/zip/net/)** voor uitgebreide voorbeelden.

**Q: Hoe koop ik een volledige licentie voor Aspose.Zip?**  
A: Je kunt Aspose.Zip voor .NET aanschaffen **[hier](https://purchase.aspose.com/buy)**.

---

**Laatst bijgewerkt:** 2026-06-09  
**Getest met:** Aspose.Zip 24.11 voor .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [zip meerdere bestanden c# – moeiteloze compressie met Aspose.Zip voor .NET](/zip/net/file-compression/compress-multiple-files/)
- [Hoe een zip‑archief maken en een bestand aan een zip toevoegen met Aspose.Zip voor .NET](/zip/net/file-compression/compress-single-file/)
- [Meerdere bestanden comprimeren met encryptie in Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}