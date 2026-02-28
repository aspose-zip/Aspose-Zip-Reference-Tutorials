---
date: 2026-02-28
description: Apprenez comment ajouter un dossier à un zip et ajouter des fichiers
  à un zip en utilisant Aspose.Zip pour .NET. Ce guide étape par étape montre comment
  compresser des fichiers avec FileInfo dans les projets ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment ajouter un dossier à une archive zip avec Aspose.Zip pour .NET – Compresser
  des fichiers avec FileInfo
url: /fr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dossier à un zip avec Aspose.Zip pour .NET

## Introduction

Si vous devez **create a zip archive** de manière programmatique, Aspose.Zip pour .NET vous offre une API propre et haute performance qui fonctionne dans n'importe quelle application .NET (y compris ASP.NET). Dans ce tutoriel, nous parcourrons la compression de fichiers avec la classe `FileInfo`, vous montrerons comment **add files to zip**, et expliquerons pourquoi cette approche est idéale pour les projets .NET modernes. Nous aborderons également comment **add folder to zip** afin que vous puissiez regrouper des répertoires entiers en une seule étape. Commençons !

## Quick Answers
- **What is the easiest way to create a zip archive?** Utilisez la classe `Archive` d’Aspose.Zip avec des objets `FileInfo`.  
- **Can I add multiple files at once?** Oui – créez simplement un `FileInfo` pour chaque fichier et appelez `CreateEntry`.  
- **Do I need a special license for ASP.NET?** Une licence commerciale Aspose.Zip est requise pour la production ; un essai gratuit suffit pour l’évaluation.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Is the API thread‑safe?** Oui, tant que chaque thread travaille avec sa propre instance `Archive`.

## What is a Zip Archive and Why Create One?
Une archive zip regroupe un ou plusieurs fichiers dans un seul conteneur compressé. Cela réduit l’espace de stockage, accélère les transferts réseau et simplifie la distribution. Que vous livriez des journaux, exportiez des rapports ou empaquetiez des ressources pour un client, savoir **how to create zip archive** de façon programmatique est une compétence précieuse pour tout développeur .NET.

## Why Use Aspose.Zip to Add Files to Zip?
- **Zero external dependencies** – implémentation pure .NET.  
- **Full control over compression level and encoding** (ASCII, UTF‑8, etc.).  
- **Supports large files** (> 4 GB) and password protection.  
- **Consistent API across .NET Framework, .NET Core, and .NET 5+**.

## Prerequisites

Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Aspose.Zip for .NET** installé. Téléchargez le dernier package depuis la [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Un dossier sur votre machine contenant les fichiers que vous souhaitez compresser (par ex., `alice29.txt` et `fields.c`).  

## Import Namespaces

Dans tout fichier C# où vous travaillerez avec des archives zip, ajoutez les instructions `using` suivantes :

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Ces espaces de noms vous donnent accès à la classe `Archive`, aux options de sauvegarde et aux utilitaires d’E/S standards.

## Step‑by‑Step Guide

### Step 1: Set Up Your Document Directory

Tout d’abord, définissez le dossier qui contient les fichiers source. Remplacez le texte de substitution par le chemin absolu ou relatif sur votre système :

```csharp
string dataDir = "Your Document Directory";
```

> **Conseil pro :** Utilisez `Path.Combine` pour construire les chemins de manière multiplateforme.

### Step 2: Open a Zip File for Writing

Créez un `FileStream` qui pointe vers le fichier zip de sortie. Le flux est ouvert en mode **Create**, ce qui écrase tout fichier existant du même nom :

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Step 3: Prepare `FileInfo` Objects for Each Source File

`FileInfo` donne à Aspose.Zip un accès direct aux fichiers physiques sur le disque. Créez une instance par fichier que vous souhaitez compresser :

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** Cela évite de charger le fichier entier en mémoire, ce qui est particulièrement utile pour les gros fichiers.

### Step 4: Create the Archive and Add Entries

Instanciez un objet `Archive`, puis appelez `CreateEntry` pour chaque `FileInfo`. Le premier argument est le nom que le fichier aura à l’intérieur du zip, le second argument est le `FileInfo` source :

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Step 5: Save the Zip Archive with Desired Encoding

Enfin, persistez l’archive dans le `FileStream` que vous avez ouvert précédemment. Ici nous utilisons l’encodage ASCII pour les noms d’entrée, mais vous pouvez passer à UTF‑8 si vos noms de fichiers contiennent des caractères non ASCII :

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Lorsque les blocs `using` se terminent, les flux sont automatiquement fermés et le fichier zip est prêt à l’emploi.

## How to Add Folder to Zip Using Aspose.Zip

Si vous devez **add folder to zip** plutôt que des fichiers individuels, le processus est simple :

1. **Enumerate the folder** avec `DirectoryInfo.GetFiles` (et éventuellement `GetDirectories` pour la récursion).  
2. **Create a `FileInfo`** pour chaque fichier découvert.  
3. **Call `CreateEntry`** avec un chemin relatif incluant le nom du dossier, par ex., `"MyFolder/Report.pdf"`.

Comme l’API travaille avec `FileInfo`, vous n’avez jamais à charger des fichiers entiers en mémoire, ce qui la rend sûre pour les grands répertoires. Cette technique fonctionne également pour les scénarios **zip multiple files asp.net** où vous générez un ensemble de rapports à la volée et devez le livrer sous forme d’une archive unique.

## Common Issues & Solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Empty zip file** | `FileInfo` pointe vers un chemin inexistant | Vérifiez `dataDir` et les noms de fichiers ; utilisez `File.Exists` pour valider avant de créer les entrées. |
| **Incorrect filename encoding** | Utilisation de l’encodage par défaut avec des noms non ASCII | Définissez `Encoding = Encoding.UTF8` dans `ArchiveSaveOptions`. |
| **OutOfMemoryException on large files** | Chargement complet du fichier en mémoire | `FileInfo` diffuse le fichier ; assurez‑vous de ne pas lire le fichier dans un tableau d’octets ailleurs. |
| **Permission denied** | L’application n’a pas les droits d’écriture sur le dossier de sortie | Exécutez l’application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

## Frequently Asked Questions

**Q : Puis‑je ajouter une protection par mot de passe à l’archive zip ?**  
R : Oui. Après avoir créé le `Archive`, définissez `archive.Password = "yourPassword"` avant d’appeler `Save`.

**Q : Est‑il possible de mettre à jour un fichier zip existant ?**  
R : Aspose.Zip permet d’ouvrir une archive existante avec `Archive.Open` puis d’ajouter de nouvelles entrées.

**Q : Comment compresser des fichiers dans un contrôleur ASP.NET MVC ?**  
R : Le même code fonctionne ; assurez‑vous simplement que le flux de sortie est renvoyé comme un `FileResult` au client.

**Q : Aspose.Zip prend‑il en charge les algorithmes de chiffrement ?**  
R : Il prend en charge le ZipCrypto standard et le chiffrement AES‑256.

**Q : Que faire pour compresser un dossier de façon récursive ?**  
R : Parcourez `Directory.GetFiles` (et les sous‑dossiers) et créez un `FileInfo` pour chaque fichier, puis ajoutez‑les à l’archive.

## Additional FAQ

**Q : Comment créer un zip archive .net pour de grands ensembles de données ?**  
R : Utilisez des objets `FileInfo` pour diffuser les données et définissez `CompressionLevel` dans `ArchiveSaveOptions` pour des performances optimales.

**Q : Puis‑je utiliser Aspose.Zip dans une API web .NET Core (zip files asp.net core) ?**  
R : Absolument – la bibliothèque est pleinement compatible avec .NET Core 3.1 et versions ultérieures.

**Q : Existe‑t‑il un moyen d’ajouter un dossier à un zip sans écrire une boucle personnalisée ?**  
R : Aspose.Zip ne possède pas de méthode unique « add folder », mais itérer avec `DirectoryInfo` est léger et vous donne un contrôle total sur les noms des entrées.

**Q : La protection par mot de passe d’une archive zip affecte‑t‑elle la vitesse de compression ?**  
R : L’activation du chiffrement ajoute un léger surcoût, mais l’impact reste minime pour la plupart des cas d’utilisation.

**Q : Quelle licence est requise pour le déploiement commercial ?**  
R : Une licence payante Aspose.Zip est nécessaire en production ; un essai gratuit peut être utilisé pour le développement et les tests.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusion

Vous savez maintenant **how to add folder to zip** et **how to create zip archive** avec Aspose.Zip pour .NET, comment **add files to zip**, et pourquoi cette méthode est idéale pour ASP.NET et les autres applications .NET. Expérimentez avec différents niveaux de compression, encodages et options de chiffrement pour adapter l’archive à vos besoins précis. Bonne compression !

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}