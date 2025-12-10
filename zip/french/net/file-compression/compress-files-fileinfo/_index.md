---
date: 2025-12-05
description: Apprenez à créer une archive zip et à y ajouter des fichiers avec Aspose.Zip
  pour .NET. Ce guide étape par étape montre comment compresser des fichiers avec
  FileInfo dans les projets ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment créer une archive Zip avec Aspose.Zip pour .NET – Compresser des fichiers
  avec FileInfo
url: /fr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une archive Zip avec Aspose.Zip pour .NET

## Introduction

Si vous devez **créer une archive zip** de manière programmatique, Aspose.Zip pour .NET vous offre une API propre et haute performance qui fonctionne dans n'importe quelle application .NET (y compris ASP.NET). Dans ce tutoriel, nous parcourrons la compression de fichiers avec la classe `FileInfo`, vous montrerons comment **ajouter des fichiers à un zip**, et expliquerons pourquoi cette approche est idéale pour les projets .NET modernes. Commençons !

## Quick Answers
- **Quelle est la façon la plus simple de créer une archive zip ?** Utilisez la classe `Archive` d’Aspose.Zip avec des objets `FileInfo`.  
- **Puis-je ajouter plusieurs fichiers à la fois ?** Oui – créez simplement un `FileInfo` pour chaque fichier et appelez `CreateEntry`.  
- **Ai-je besoin d'une licence spéciale pour ASP.NET ?** Une licence commerciale Aspose.Zip est requise pour la production ; un essai gratuit suffit pour l'évaluation.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **L'API est‑ thread‑safe ?** Oui, tant que chaque thread travaille avec sa propre instance `Archive`.

## What is a Zip Archive and Why Create One?
Une archive zip regroupe un ou plusieurs fichiers dans un conteneur unique et compressé. Cela réduit l'espace de stockage, accélère les transferts réseau et simplifie la distribution. Que vous livriez des journaux, exportiez des rapports ou empaquetiez des ressources pour un client, savoir **comment créer des archives zip** de manière programmatique est une compétence précieuse pour tout développeur .NET.

## Why Use Aspose.Zip to Add Files to Zip?
- **Aucune dépendance externe** – implémentation pure .NET.  
- **Contrôle complet du niveau de compression et de l'encodage** (ASCII, UTF‑8, etc.).  
- **Prise en charge des fichiers volumineux** (> 4 GB) et de la protection par mot de passe.  
- **API cohérente sur .NET Framework, .NET Core et .NET 5+**.

## Prerequisites

Avant de plonger dans le code, assurez‑vous d'avoir :

1. **Aspose.Zip pour .NET** installé. Téléchargez le dernier package depuis la [page de téléchargement Aspose.Zip](https://releases.aspose.com/zip/net/).  
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

## Step‑by‑Step Guide

### Step 1: Set Up Your Document Directory

Tout d'abord, définissez le dossier qui contient les fichiers source. Remplacez le placeholder par le chemin absolu ou relatif sur votre système :

```csharp
string dataDir = "Your Document Directory";
```

> **Astuce :** Utilisez `Path.Combine` pour construire les chemins de manière multiplateforme.

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

> **Pourquoi utiliser `FileInfo` ?** Cela évite de charger le fichier entier en mémoire, ce qui est particulièrement utile pour les gros fichiers.

### Step 4: Create the Archive and Add Entries

Instanciez un objet `Archive`, puis appelez `CreateEntry` pour chaque `FileInfo`. Le premier argument est le nom que le fichier aura à l'intérieur du zip, le second argument est le `FileInfo` source :

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Step 5: Save the Zip Archive with Desired Encoding

Enfin, persistez l'archive dans le `FileStream` que vous avez ouvert précédemment. Ici nous utilisons l'encodage ASCII pour les noms d'entrées, mais vous pouvez passer à UTF‑8 si vos noms de fichiers contiennent des caractères non‑ASCII :

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Lorsque les blocs `using` se terminent, les flux sont automatiquement fermés et le fichier zip est prêt à être utilisé.

## Common Issues & Solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Fichier zip vide** | `FileInfo` pointe vers un chemin inexistant | Vérifiez `dataDir` et les noms de fichiers ; utilisez `File.Exists` pour vérifier avant de créer les entrées. |
| **Encodage de nom de fichier incorrect** | Utilisation de l'encodage par défaut avec des noms non‑ASCII | Définissez `Encoding = Encoding.UTF8` dans `ArchiveSaveOptions`. |
| **OutOfMemoryException sur de gros fichiers** | Chargement du fichier entier en mémoire | `FileInfo` diffuse le fichier ; assurez‑vous de ne pas lire le fichier dans un tableau d'octets ailleurs. |
| **Permission refusée** | L'application n'a pas les droits d'écriture sur le dossier de sortie | Exécutez l'application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

## Frequently Asked Questions

**Q : Puis‑je ajouter une protection par mot de passe à l'archive zip ?**  
R : Oui. Après avoir créé l'`Archive`, définissez `archive.Password = "yourPassword"` avant d'appeler `Save`.

**Q : Est‑il possible de mettre à jour un fichier zip existant ?**  
R : Aspose.Zip permet d'ouvrir une archive existante avec `Archive.Open` puis d'ajouter de nouvelles entrées.

**Q : Comment compresser des fichiers dans un contrôleur ASP.NET MVC ?**  
R : Le même code fonctionne ; assurez‑vous simplement que le flux de sortie est renvoyé comme `FileResult` au client.

**Q : Aspose.Zip prend‑il en charge les algorithmes de chiffrement ?**  
R : Il prend en charge le ZipCrypto standard et le chiffrement AES‑256.

**Q : Que faire si je dois compresser un dossier de façon récursive ?**  
R : Parcourez `Directory.GetFiles` (et les sous‑dossiers) et créez un `FileInfo` pour chaque fichier, puis ajoutez‑les à l'archive.

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

Vous savez maintenant **comment créer des archives zip** avec Aspose.Zip pour .NET, comment **ajouter des fichiers à un zip**, et pourquoi cette méthode est idéale pour ASP.NET et d'autres applications .NET. Expérimentez différents niveaux de compression, encodages et options de chiffrement pour adapter l'archive à vos besoins précis. Bonne compression !

---

**Dernière mise à jour:** 2025-12-05  
**Testé avec:** Aspose.Zip for .NET 24.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}