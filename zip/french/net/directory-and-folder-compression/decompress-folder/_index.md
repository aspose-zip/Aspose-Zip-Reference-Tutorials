---
date: 2025-12-01
description: Apprenez à compresser un répertoire en zip et à extraire un zip vers
  un répertoire en utilisant Aspose.Zip pour .NET – un guide complet de la compression
  zip .NET et de la création d’archives zip .NET.
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Compresser un répertoire en zip et décompresser – Aspose.Zip pour .NET
url: /fr/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Compresser un répertoire en Zip & Décompresser – Aspose.Zip pour .NET

Si vous devez **compress directory to zip** et ensuite extraire cette archive dans une application .NET, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons l’ensemble du flux de travail—en commençant par créer une archive zip, puis en vous montrant une décompression propre, étape par étape, à l’aide d’Aspose.Zip pour .NET. À la fin, vous disposerez d’un modèle réutilisable pour la compression zip dans les projets .NET et d’une compréhension solide de la façon de décompresser à la manière .NET.

## Réponses rapides
- **What does “compress directory to zip” mean?** Cela signifie transformer le contenu d’un dossier en un seul fichier .zip.  
- **How do I extract zip to directory?** Utilisez la méthode `Archive.ExtractToDirectory` comme indiqué dans le guide.  
- **Which .NET versions are supported?** Toutes les versions modernes de .NET Framework, .NET Core et .NET 5/6+.
- **Is a license required for production?** Oui, une licence commerciale Aspose.Zip est requise pour une utilisation hors période d’essai.  
- **Can I automate this in CI/CD pipelines?** Absolument—il suffit d’ajouter le même code à vos scripts de construction.

## Qu’est‑ce que “compress directory to zip” ?
Compresser un répertoire en zip regroupe chaque fichier et sous‑dossier dans une archive compressée unique. Cela réduit la taille de stockage, simplifie le transfert et constitue une méthode standard pour empaqueter des ressources en vue du déploiement.

## Pourquoi utiliser Aspose.Zip pour .NET ?
Aspose.Zip propose une API **pure‑managed** qui fonctionne sans dépendances natives, prend en charge les gros fichiers et offre des capacités de compression zip haute performance .NET. Elle gère également les cas particuliers tels que les archives protégées par mot de passe et les noms de fichiers Unicode dès le départ.

## Prérequis
- Bibliothèque **Aspose.Zip for .NET** installée (téléchargez‑la [ici](https://releases.aspose.com/zip/net/)).  
- Un dossier sur le disque que vous souhaitez archiver – définissez son chemin dans la variable `dataDir`.  
- Environnement de développement .NET (Visual Studio, VS Code ou tout IDE de votre choix).

## Importer les espaces de noms
Tout d’abord, importez les espaces de noms requis :

```csharp
using Aspose.Zip;
using System.IO;
```

## Étape 1 : Compresser un répertoire en Zip
Nous créerons un fichier zip à partir du répertoire que vous prévoyez de décompresser ultérieurement. L’utilitaire `CompressDirectory.Run()` effectue le travail lourd.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Astuce :** L’exemple `CompressDirectory` regroupe chaque fichier de `dataDir` dans `CompressDirectory_out.zip`. N’hésitez pas à renommer le fichier de sortie selon vos conventions de nommage.

## Étape 2 : Décompresser le dossier (Comment dézipper .NET)

### Étape 2.1 : Ouvrir le fichier Zip
Ouvrez l’archive générée avec un `FileStream`. Cela prépare le fichier pour la lecture.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### Étape 2.2 : Créer une instance Archive
Instanciez l’objet `Archive`, qui représente le conteneur zip.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### Étape 2.3 : Extraire vers un répertoire
Enfin, extrayez le contenu vers un nouveau dossier. Il s’agit de l’étape **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

Félicitations ! Vous avez réussi à **compress a directory to zip** puis à **extract the zip to a directory** à l’aide d’Aspose.Zip pour .NET. Cette approche garantit l’intégrité des données tout en conservant un code concis et lisible.

## Problèmes courants & solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `UnauthorizedAccessException` when extracting | Le dossier cible est en lecture‑seule ou utilisé | Assurez‑vous que le chemin de destination est inscriptible et non verrouillé |
| Empty output folder after extraction | Chemin du zip source incorrect | Vérifiez que `dataDir + "CompressDirectory_out.zip"` pointe vers le bon fichier |
| Large files cause OutOfMemoryException | Utilisation de la taille de tampon par défaut sur des archives très volumineuses | Utilisez `ArchiveOptions` pour augmenter la taille du tampon ou diffusez les fichiers par morceaux |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Zip pour .NET avec n’importe quel type de fichier ?**  
**R :** Oui, Aspose.Zip prend en charge tous les types de fichiers—texte, binaire, images, PDF, etc.

**Q : Aspose.Zip est‑il adapté aux applications à grande échelle ?**  
**R :** Absolument. Il est conçu pour des scénarios de compression zip haute performance .NET, gérant des archives de plusieurs gigaoctets avec une faible consommation de mémoire.

**Q : Où puis‑je trouver une documentation complète pour Aspose.Zip pour .NET ?**  
**R :** Consultez la documentation détaillée [ici](https://reference.aspose.com/zip/net/).

**Q : Puis‑je essayer Aspose.Zip avant d’acheter ?**  
**R :** Oui, un essai gratuit est disponible sur la [page de téléchargement d’Aspose.Zip](https://releases.aspose.com/).

**Q : Comment obtenir du support pour Aspose.Zip pour .NET ?**  
**R :** Rendez‑vous sur le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour l’aide de la communauté et l’assistance officielle.

---

**Dernière mise à jour :** 2025-12-01  
**Testé avec :** Aspose.Zip 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}