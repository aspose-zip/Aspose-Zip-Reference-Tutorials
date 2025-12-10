---
date: 2025-12-10
description: Apprenez la compression de fichiers en parallèle dans .NET avec Aspose.Zip.
  Compressez plusieurs fichiers efficacement grâce à notre guide étape par étape.
linktitle: Using Parallelism to Compress Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Compression de fichiers en parallèle avec Aspose.Zip pour .NET
url: /fr/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Compression de fichiers en parallèle avec Aspose.Zip pour .NET

## Introduction

Dans le monde du développement .NET, la **compression de fichiers en parallèle** est essentielle pour optimiser l'espace de stockage et accélérer la transmission des données. Aspose.Zip pour .NET offre une solution puissante, et l'une de ses caractéristiques remarquables est la capacité à exploiter le parallélisme pour la compression de fichiers. Dans ce tutoriel, nous vous guiderons pour utiliser le parallélisme afin de **compresser plusieurs fichiers** efficacement avec Aspose.Zip pour .NET.

## Réponses rapides
- **Qu’est‑ce que la compression de fichiers en parallèle ?** Une technique qui compresse plusieurs fichiers simultanément, en utilisant plusieurs cœurs CPU pour réduire le temps de traitement global.  
- **Quelle bibliothèque le prend en charge sous .NET ?** Aspose.Zip pour .NET propose des options de compression parallèle intégrées.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire est disponible pour les tests ; une licence complète est requise pour la production.  
- **Puis‑je ajouter des fichiers au zip à la volée ?** Oui — utilisez `Archive.CreateEntry` pour chaque fichier que vous souhaitez inclure.  
- **Est‑il compatible avec .NET Core/5/6 ?** Absolument, l’API fonctionne sur tous les runtimes .NET modernes.

## Qu’est‑ce que la compression de fichiers en parallèle ?
La compression de fichiers en parallèle consiste à répartir la charge de travail de compression sur plusieurs threads ou cœurs, permettant ainsi de compresser plusieurs fichiers (ou des parties d’un gros fichier) en même temps. Cette approche réduit considérablement le temps nécessaire pour créer une **archive zip c#** comparée à la compression séquentielle traditionnelle.

## Pourquoi utiliser Aspose.Zip pour la compression parallèle ?
- **Vitesse :** Exploite pleinement les CPU multi‑cœurs.  
- **Scalabilité :** Gère de gros lots de fichiers sans augmentation proportionnelle du temps de traitement.  
- **Simplicité :** L’API de haut niveau abstrait les complexités du threading.  
- **Flexibilité :** Fonctionne avec n’importe quelle version de .NET et s’intègre facilement aux bases de code existantes.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Des connaissances de base en C# et en développement .NET.  
- La bibliothèque Aspose.Zip pour .NET installée. Vous pouvez la télécharger **[ici](https://releases.aspose.com/zip/net/)**.  
- Une compréhension des concepts standards de compression de fichiers.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis dans votre fichier C# afin que le compilateur sache où trouver les classes que vous utiliserez.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Étape 1 : Configurer votre répertoire de documents

Définissez le dossier contenant les fichiers que vous souhaitez compresser. Ce chemin est stocké dans la variable `dataDir`.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Initialiser le processus de compression

Ouvrez un nouveau fichier ZIP en écriture. L’instruction `using` garantit que le flux de fichier est correctement libéré après l’opération.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Étape 3 : Lire et compresser les fichiers en parallèle

Ouvrez chaque fichier source que vous avez l’intention d’ajouter à l’archive. Dans cet exemple nous travaillons avec deux textes classiques, mais vous pouvez **ajouter des fichiers au zip** pour n’importe quel nombre de documents.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Étape 4 : Créer les entrées d'archive

Créez une instance `Archive` et ajoutez chaque fichier comme une entrée séparée. C’est à ce moment que l’étape **create zip archive c#** se produit.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Étape 5 : Définir le critère de parallélisme

Configurez la compression pour s’exécuter en parallèle en définissant `ParallelOptions`. Le drapeau `ParallelCompressInMemory` indique à Aspose.Zip d’utiliser toujours le traitement parallèle.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Étape 6 : Enregistrer l'archive compressée

Enfin, écrivez l’archive sur le disque avec les options souhaitées, incluant l’encodage, un commentaire, et les paramètres parallèles définis précédemment.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

Félicitations ! Vous venez d’effectuer une **compression de fichiers en parallèle** avec Aspose.Zip pour .NET, compressant efficacement **plusieurs fichiers** dans une archive unique.

## Problèmes courants & conseils

- **Fichiers volumineux :** Si vous rencontrez une pression mémoire, envisagez de compresser les fichiers par morceaux plutôt que de charger le fichier entier en mémoire.  
- **Sécurité des threads :** L’API Aspose.Zip est thread‑safe en mode parallèle ; évitez de modifier le même flux depuis plusieurs threads en dehors de la bibliothèque.  
- **Optimisation des performances :** Expérimentez avec `ParallelOptions.MaxDegreeOfParallelism` si vous devez limiter l’utilisation du CPU sur des serveurs partagés.  

## FAQ

### Q1 : Puis‑je utiliser Aspose.Zip pour .NET avec d’autres bibliothèques .NET ?

R1 : Oui, Aspose.Zip pour .NET est conçu pour s’intégrer de façon transparente avec d’autres bibliothèques .NET.

### Q2 : Une licence temporaire est‑elle disponible pour les tests ?

R2 : Oui, vous pouvez obtenir une licence temporaire pour les tests **[ici](https://purchase.aspose.com/temporary-license/)**.

### Q3 : Où puis‑je trouver un support supplémentaire ou poser des questions ?

R3 : Visitez le **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** pour le support communautaire et les discussions.

### Q4 : Existe‑t‑il des exemples ou de la documentation disponible ?

R4 : Explorez la **[documentation Aspose.Zip](https://reference.aspose.com/zip/net/)** pour des exemples complets et une documentation détaillée.

### Q5 : Comment puis‑je acheter Aspose.Zip pour .NET ?

R5 : Vous pouvez acheter Aspose.Zip pour .NET **[ici](https://purchase.aspose.com/buy)**.

**Dernière mise à jour :** 2025-12-10  
**Testé avec :** Aspose.Zip 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}