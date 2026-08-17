---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip multiple files c# avec la compression parallèle d'Aspose.Zip

## Introduction

Si vous devez **zipper plusieurs fichiers c#** rapidement et efficacement, exploiter le traitement parallèle est la solution idéale. Dans les applications .NET modernes, la création de grandes archives zip peut devenir un goulot d'étranglement—surtout lorsqu'il s'agit de dizaines ou de centaines de fichiers. Aspose.Zip pour .NET élimine ce problème en offrant une **compression zip parallèle** intégrée qui répartit le travail sur tous les cœurs CPU disponibles. Dans ce tutoriel, nous parcourrons l’ensemble du processus : de la configuration de l’environnement à l’enregistrement d’une archive zip avec le parallélisme activé, et nous vous montrerons également comment **créer une archive zip c#** qui fonctionne sans accroc sur .NET Core.

## Réponses rapides
- **Qu’est‑ce que la compression zip parallèle ?** Elle compresse plusieurs fichiers simultanément, en utilisant plusieurs threads pour réduire le temps de traitement global.  
- **Quelle bibliothèque .NET le prend en charge ?** Aspose.Zip pour .NET fournit une API simple pour la compression parallèle.  
- **Ai‑je besoin d’une licence pour la production ?** Oui—une licence complète est requise ; une licence temporaire est disponible pour les tests.  
- **Puis‑je ajouter des fichiers au zip à la volée ?** Absolument—utilisez `Archive.CreateEntry` pour chaque fichier que vous souhaitez inclure.  
- **Est‑elle compatible avec .NET 6/7 ?** Oui, l’API fonctionne sur tous les runtimes .NET modernes.

## Qu’est‑ce que zip multiple files c# ?
`zip multiple files c#` désigne la pratique de créer une archive ZIP unique contenant de nombreux fichiers individuels, en utilisant du code C#. Lorsque vous combinez cela avec la **compression zip parallèle**, la bibliothèque traite chaque fichier sur un thread séparé, réduisant ainsi de façon spectaculaire le temps nécessaire pour produire l’archive finale.

## Pourquoi utiliser Aspose.Zip pour la compression parallèle ?
La compression parallèle vous permet d’exploiter chaque cœur d’une machine multiprocesseur, offrant souvent un débit **2‑3× plus rapide** qu’une approche monothread. Elle s’adapte également de façon fluide : ajouter davantage de fichiers n’augmente pas linéairement le temps d’exécution, et l’API gère la gestion des threads pour vous, vous permettant de vous concentrer sur la logique métier.  

- **Vitesse :** Utilise tous les processeurs logiques, réduisant le temps de création du zip jusqu’à 70 % sur des charges de travail typiques.  
- **Scalabilité :** Gère des lots de 500 + fichiers sans augmentation proportionnelle du temps CPU.  
- **Simplicité :** Les méthodes de haut niveau masquent la complexité de `System.Threading.Tasks`.  
- **Flexibilité :** Prend en charge .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, et .NET 5–10, y compris .NET 6/7 pour les services cloud‑native.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Des connaissances de base en C# et développement .NET.  
- Aspose.Zip pour .NET installé. Vous pouvez le télécharger **[ici](https://releases.aspose.com/zip/net/)**.  
- Une licence temporaire ou complète (la licence temporaire suffit pour ce tutoriel).  

## Importer les espaces de noms

L’espace de noms `Aspose.Zip` contient tous les types nécessaires pour travailler avec les archives ZIP.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Tout d’abord, importez les espaces de noms requis dans votre fichier C# afin que le compilateur sache où trouver les classes que vous utiliserez.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Étape 1 : Configurer le répertoire de vos documents

Définissez le dossier contenant les fichiers que vous souhaitez compresser. Ce chemin est stocké dans la variable `dataDir`, que vous pouvez pointer vers n’importe quel emplacement sur le disque.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Initialiser le processus de compression

Ouvrez un nouveau fichier ZIP en écriture. L’instruction `using` garantit que le flux de fichier est correctement libéré après l’opération, évitant les fuites de descripteurs de fichiers.

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

## Étape 3 : Lire et compresser les fichiers en parallèle

`Parallel.ForEach` exécute une boucle foreach dont les itérations peuvent s’exécuter simultanément sur plusieurs threads.  

Ouvrez chaque fichier source que vous avez l’intention d’ajouter à l’archive. Dans cet exemple nous travaillons avec deux textes classiques, mais vous pouvez **ajouter des fichiers au zip** pour n’importe quel nombre de documents. La boucle `Parallel.ForEach` répartit automatiquement le travail entre les threads.

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

## Étape 4 : Créer les entrées d’archive

La classe `Archive` est l’objet de haut niveau d’Aspose.Zip qui représente le conteneur ZIP que vous construisez.  

`CreateEntry` crée une nouvelle entrée dans l’archive ZIP pour un fichier spécifié. Chaque appel à `CreateEntry` ajoute une nouvelle entrée de fichier à l’archive.

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

## Étape 5 : Définir le critère de parallélisme

`ParallelOptions` est un type .NET qui contrôle la façon dont les boucles parallèles sont exécutées.  

Configurez la compression pour s’exécuter en parallèle en définissant `ParallelOptions`. Le drapeau `ParallelCompressInMemory` indique à Aspose.Zip d’utiliser toujours le traitement parallèle, tandis que `MaxDegreeOfParallelism` vous permet de limiter le nombre de threads concurrents.

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

## Étape 6 : Enregistrer l’archive compressée

Enfin, écrivez l’archive sur le disque avec les options souhaitées, incluant l’encodage, un commentaire et les paramètres parallèles définis précédemment. La méthode `Save` finalise le fichier ZIP.

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

> **Astuce pro :** Si vous compressez des fichiers très volumineux, envisagez de définir `ParallelOptions.MaxDegreeOfParallelism` à une valeur inférieure au nombre de processeurs logiques. Cela aide à garder votre serveur réactif sous charge.

### Cas d'utilisation courants

- **Rapports par lots :** Générer un bundle zip de rapports CSV quotidiens pour les systèmes en aval.  
- **Archivage de documents :** Stocker de grandes collections de PDF, images ou journaux dans une archive unique pour la sauvegarde.  
- **API d’exportation de données :** Retourner un fichier zip contenant plusieurs fichiers de données à un client dans une seule réponse HTTP.  

## Problèmes courants et astuces

- **Pression mémoire sur les gros fichiers :** Au lieu de charger un fichier entier en mémoire, diffusez‑le par blocs ou utilisez le mode `ParallelCompressInMemory` de façon sélective.  
- **Sécurité des threads :** L’API Aspose.Zip est thread‑safe en mode parallèle, mais évitez de modifier le même `FileStream` depuis l’extérieur de la bibliothèque pendant la compression.  
- **Optimisation des performances :** Expérimentez avec `ParallelOptions.MaxDegreeOfParallelism` si vous devez limiter l’utilisation du CPU sur des serveurs partagés.  

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Zip pour .NET conjointement avec d’autres bibliothèques de compression ?**  
R : Oui, Aspose.Zip peut coexister avec d’autres bibliothèques .NET ; il suffit de garder leurs espaces de noms distincts.

**Q : Une licence temporaire est‑elle disponible à des fins de test ?**  
R : Oui, vous pouvez obtenir une licence temporaire pour les tests **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Où puis‑je demander de l’aide en cas de problème ?**  
R : Rendez‑vous sur le **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** pour le support communautaire et les discussions.

**Q : Où trouver plus d’exemples de code et la documentation détaillée de l’API ?**  
R : Explorez la **[documentation Aspose.Zip](https://reference.aspose.com/zip/net/)** pour des exemples complets.

**Q : Comment acheter une licence complète pour Aspose.Zip ?**  
R : Vous pouvez acheter Aspose.Zip pour .NET **[ici](https://purchase.aspose.com/buy)**.

---

**Dernière mise à jour :** 2026-06-09  
**Testé avec :** Aspose.Zip 24.11 pour .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [zip multiple files c# – Compression sans effort avec Aspose.Zip pour .NET](/zip/net/file-compression/compress-multiple-files/)
- [Comment créer une archive Zip et ajouter un fichier au Zip en utilisant Aspose.Zip pour .NET](/zip/net/file-compression/compress-single-file/)
- [Compresser plusieurs fichiers avec chiffrement dans Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}