---
date: 2026-07-18
description: Apprenez comment ajouter un dossier à un zip et ajouter des fichiers
  à un zip en utilisant Aspose.Zip pour .NET. Ce guide étape par étape montre comment
  compresser des fichiers avec FileInfo dans des projets ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Compresser des fichiers avec FileInfo
og_description: Ajouter un dossier à un zip avec Aspose.Zip pour .NET. Apprenez comment
  créer une archive zip, ajouter des fichiers à un zip et compresser des dossiers
  efficacement dans ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Ajouter un dossier à un zip – Compresser des fichiers avec Aspose.Zip pour
  .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Ajouter un dossier à un zip avec Aspose.Zip pour .NET – Compresser des fichiers
  avec FileInfo
url: /fr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dossier à un zip avec Aspose.Zip pour .NET

## Introduction

Si vous devez **ajouter un dossier à un zip** de manière programmatique, Aspose.Zip pour .NET propose une API propre et haute performance qui fonctionne dans n'importe quelle application .NET (y compris ASP.NET). Dans ce tutoriel, nous parcourrons la compression de fichiers avec la classe `FileInfo`, vous montrerons comment **ajouter des fichiers à un zip**, et expliquerons pourquoi cette approche est idéale pour les projets .NET modernes. Nous couvrirons également les étapes exactes pour **ajouter un dossier à un zip** afin que vous puissiez regrouper des répertoires entiers en une seule opération. Commençons !

## Réponses rapides
- **Quelle est la façon la plus simple de créer une archive zip ?** Utilisez la classe `Archive` d’Aspose.Zip avec des objets `FileInfo`.  
- **Puis-je ajouter plusieurs fichiers à la fois ?** Oui – créez simplement un `FileInfo` pour chaque fichier et appelez `CreateEntry`.  
- **Ai-je besoin d'une licence spéciale pour ASP.NET ?** Une licence commerciale Aspose.Zip est requise pour la production ; un essai gratuit suffit pour l'évaluation.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 et .NET 5–10.  
- **L'API est‑elle thread‑safe ?** Oui, tant que chaque thread travaille avec sa propre instance `Archive`.

## Qu'est‑ce qu'une archive Zip et pourquoi en créer une ?

Une archive zip regroupe un ou plusieurs fichiers dans un seul conteneur compressé. Cela réduit l'espace de stockage, accélère les transferts réseau et simplifie la distribution. Que vous livriez des journaux, exportiez des rapports ou empaquetiez des ressources pour un client, savoir **comment créer des archives zip** de manière programmatique est une compétence précieuse pour tout développeur .NET.

## Pourquoi utiliser Aspose.Zip pour ajouter des fichiers à un zip ?

Aspose.Zip fournit une solution pure‑.NET qui élimine les dépendances externes tout en offrant aux développeurs un contrôle fin sur la compression, l'encodage et la sécurité. Il prend en charge les gros fichiers, la protection par mot de passe et fonctionne de manière cohérente sur toutes les versions .NET prises en charge, ce qui en fait un choix fiable tant pour les applications héritées que modernes.  

- **Aucune dépendance externe** – implémentation pure .NET.  
- **Contrôle complet du niveau de compression et de l'encodage** (ASCII, UTF‑8, etc.).  
- **Prend en charge les fichiers de plus de 4 Go** et la protection par mot de passe.  
- **API cohérente sur plus de 50 versions .NET** – du .NET Framework 2.0 jusqu'à .NET 10.  

## Prérequis

Avant de plonger dans le code, assurez‑vous d'avoir :

1. **Aspose.Zip pour .NET** installé. Téléchargez le dernier package depuis la [page de téléchargement d'Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Un dossier sur votre machine contenant les fichiers que vous souhaitez compresser (par ex., `alice29.txt` et `fields.c`).  

## Importer les espaces de noms

Dans tout fichier C# où vous travaillerez avec des archives zip, ajoutez les instructions `using` suivantes :

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Ces espaces de noms vous donnent accès à la classe `Archive`, aux options d'enregistrement et aux utilitaires d'E/S standard.

## Guide étape par étape

### Étape 1 : Configurer votre répertoire de documents

First, define the folder that holds the source files. Replace the placeholder with the absolute or relative path on your system:

```csharp
string dataDir = "Your Document Directory";
```

> **Astuce :** Utilisez `Path.Combine` pour construire les chemins de manière multiplateforme.

### Étape 2 : Ouvrir un fichier zip en écriture

Create a `FileStream` that points to the output zip file. The stream is opened in **Create** mode, which overwrites any existing file with the same name:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Étape 3 : Préparer les objets `FileInfo` pour chaque fichier source

`FileInfo` gives Aspose.Zip direct access to the physical files on disk. Create one instance per file you want to compress:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Pourquoi utiliser `FileInfo` ?** Cela évite de charger le fichier entier en mémoire, ce qui est particulièrement utile pour les gros fichiers.

### Étape 4 : Créer l'archive et ajouter des entrées

The `Archive` class is Aspose.Zip's core object that represents a zip container in memory. Instantiate an `Archive` object, then call `CreateEntry` for each `FileInfo`. The first argument is the name the file will have inside the zip, the second argument is the source `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

La méthode `CreateEntry` ajoute une nouvelle entrée de fichier à l'archive, liant le nom de l'entrée au `FileInfo` source afin que les données soient diffusées directement depuis le disque lors de l'enregistrement de l'archive.

### Étape 5 : Enregistrer l'archive zip avec l'encodage souhaité

Finally, persist the archive to the `FileStream` you opened earlier. Here we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames contain non‑ASCII characters:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Lorsque les blocs `using` se terminent, les flux sont automatiquement fermés et le fichier zip est prêt à être utilisé.

## Comment ajouter un dossier à un zip avec Aspose.Zip ?

Chargez le répertoire cible, énumérez chaque fichier et ajoutez‑les avec un chemin relatif incluant le nom du dossier. Cette approche vous permet de **ajouter un dossier à un zip** sans lister manuellement chaque fichier. En conservant la hiérarchie des dossiers dans les noms d'entrée, l'archive résultante peut être extraite avec la structure de répertoires d'origine intacte, ce qui est essentiel pour de nombreux scénarios de déploiement.

1. Utilisez `DirectoryInfo` pour pointer vers le dossier que vous souhaitez compresser.  
2. Appelez `GetFiles("*", SearchOption.AllDirectories)` pour récupérer tous les fichiers de façon récursive.  
3. Pour chaque fichier, créez un `FileInfo` et appelez `CreateEntry` avec un chemin tel que `"MyFolder/Report.pdf"`.

Comme l'API travaille avec `FileInfo`, elle diffuse chaque fichier directement depuis le disque, maintenant une faible utilisation de la mémoire même pour des dossiers contenant des centaines de mégaoctets.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Fichier zip vide** | `FileInfo` pointe vers un chemin inexistant | Vérifiez `dataDir` et les noms de fichiers ; utilisez `File.Exists` pour vérifier avant de créer les entrées. |
| **Encodage de nom de fichier incorrect** | Utilisation de l'encodage par défaut avec des noms non ASCII | Définissez `Encoding = Encoding.UTF8` dans `ArchiveSaveOptions`. |
| **OutOfMemoryException sur de gros fichiers** | Chargement du fichier entier en mémoire | `FileInfo` diffuse le fichier ; assurez‑vous de ne pas lire le fichier dans un tableau d'octets ailleurs. |
| **Permission refusée** | L'application n'a pas les droits d'écriture sur le dossier de sortie | Exécutez l'application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

## Questions fréquemment posées

**Q : Puis‑je ajouter un dossier entier à une archive zip en un seul appel ?**  
R : Il n'existe pas de méthode à appel unique, mais l'énumération des fichiers avec `DirectoryInfo` et l'ajout de chacun via `CreateEntry` permet d'obtenir le même résultat efficacement.

**Q : Aspose.Zip prend‑il en charge la protection par mot de passe ?**  
R : Oui, vous pouvez définir un mot de passe sur l'objet `Archive` avant l'enregistrement pour chiffrer l'ensemble de l'archive.

**Q : Quelle taille maximale de fichier zip Aspose.Zip peut‑il gérer ?**  
R : La bibliothèque traite des fichiers de plus de 4 Go et peut créer des archives dépassant 10 Go sans charger l'intégralité de l'archive en mémoire.

**Q : L'API est‑elle compatible avec .NET 6 et .NET 8 ?**  
R : Absolument. Aspose.Zip prend en charge .NET 5 à .NET 10, couvrant toutes les versions LTS actuelles.

**Q : Quels niveaux de compression sont disponibles ?**  
R : Vous pouvez choisir `CompressionLevel.NoCompression`, `Fast`, `Normal` ou `Maximum` pour équilibrer vitesse et taille.

## Ressources supplémentaires

- Télécharger le dernier package Aspose.Zip : [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Acheter une licence pour une utilisation en production : [purchase page](https://purchase.aspose.com/buy)  
- Obtenir de l'aide de la communauté : [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Essayer Aspose.Zip gratuitement : [free trial here](https://releases.aspose.com/)  
- Obtenir une licence temporaire pour l'évaluation : [this link](https://purchase.aspose.com/temporary-license/)

## Conclusion

Vous savez maintenant **comment ajouter un dossier à un zip** et **comment créer des archives zip** avec Aspose.Zip pour .NET, comment **ajouter des fichiers à un zip**, et pourquoi cette méthode est idéale pour ASP.NET et les autres applications .NET. Expérimentez différents niveaux de compression, encodages et options de chiffrement pour adapter l'archive à vos besoins précis. Bonne compression !

---

**Dernière mise à jour :** 2026-07-18  
**Testé avec :** Aspose.Zip pour .NET 24.12 (dernière version)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment zipper un dossier avec Aspose.Zip pour .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Compresser plusieurs fichiers c# – Compression sans effort avec Aspose.Zip pour .NET](/zip/net/file-compression/compress-multiple-files/)
- [Créer une archive Zip .NET – Compression de fichiers avec Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}