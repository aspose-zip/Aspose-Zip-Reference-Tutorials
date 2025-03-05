---
title: Créer sept fichiers Zip - Tutoriel Aspose.Zip pour .NET
linktitle: SevenZip avec diverses méthodes de compression
second_title: API Aspose.Zip .NET pour la compression et l'archivage de fichiers
description: Apprenez à créer Seven Zip avec Aspose.Zip pour .NET en utilisant différentes méthodes de compression. Étapes simples pour LZMA2, BZip2 et Store (pas de compression).
type: docs
weight: 12
url: /fr/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## Introduction

Dans le domaine du développement .NET, la gestion et la compression de fichiers sont une tâche courante. Aspose.Zip pour .NET fournit une solution puissante pour travailler avec des archives compressées, offrant une variété de méthodes de compression. Dans ce didacticiel, nous allons explorer comment utiliser Aspose.Zip pour .NET pour créer des fichiers Seven Zip avec différentes méthodes de compression.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous de disposer des éléments suivants :

- Une compréhension de base de la programmation C#.
- Visual Studio installé sur votre ordinateur.
-  Aspose.Zip pour la bibliothèque .NET. Vous pouvez le télécharger[ici](https://releases.aspose.com/zip/net/).

## Importer des espaces de noms

Commencez par importer les espaces de noms nécessaires dans votre projet C#. Utilisez l'extrait de code suivant pour commencer :

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Compression LZMA2

```csharp
//ExStart : SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd : SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

## CompressionBZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Stocker, pas de compression

```csharp
//Stocker, pas de compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Conclusion

Dans ce didacticiel, nous avons exploré la polyvalence d'Aspose.Zip pour .NET dans la création de fichiers Seven Zip avec diverses méthodes de compression. Que vous ayez besoin de taux de compression élevés ou que vous préfériez aucune compression, Aspose.Zip offre la flexibilité nécessaire pour répondre à vos besoins.

## FAQ

### Puis-je utiliser Aspose.Zip pour .NET avec n’importe quel type de fichier ?
Oui, Aspose.Zip pour .NET prend en charge un large éventail de types de fichiers, vous permettant de compresser et décompresser différents formats.

### Un essai gratuit est-il disponible pour Aspose.Zip pour .NET ?
 Oui, vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).

### Où puis-je trouver de la documentation pour Aspose.Zip pour .NET ?
 La documentation est disponible[ici](https://reference.aspose.com/zip/net/).

### Comment puis-je obtenir des licences temporaires pour Aspose.Zip pour .NET ?
 Des licences temporaires peuvent être obtenues[ici](https://purchase.aspose.com/temporary-license/).

### Où puis-je obtenir de l’assistance pour Aspose.Zip pour .NET ?
 Vous pouvez demander de l'aide sur le[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).
