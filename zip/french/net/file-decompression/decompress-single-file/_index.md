---
title: Décompresser un seul fichier avec Aspose.Zip pour .NET
linktitle: Décompresser un seul fichier
second_title: API Aspose.Zip .NET pour la compression et l'archivage de fichiers
description: Explorez le monde transparent de la décompression de fichiers avec Aspose.Zip pour .NET. Gérez sans effort les fichiers compressés dans vos projets C#.
weight: 12
url: /fr/net/file-decompression/decompress-single-file/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Décompresser un seul fichier avec Aspose.Zip pour .NET

## Introduction

Dans le domaine du développement .NET, Aspose.Zip constitue une solution robuste pour gérer les fichiers compressés avec finesse. Ce didacticiel vous guidera tout au long du processus de décompression d'un seul fichier à l'aide d'Aspose.Zip pour .NET. Attachez-vous et découvrez étape par étape les capacités de cette puissante bibliothèque.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Zip pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir du[Aspose.Zip pour la documentation .NET](https://reference.aspose.com/zip/net/).

- Environnement de développement : disposez d'un environnement de développement .NET fonctionnel, comprenant Visual Studio ou tout autre IDE compatible.

- Compréhension de base de C# : Familiarisez-vous avec les bases de la programmation C#.

Maintenant, mettons la main à la pâte avec du code !

## Importer des espaces de noms

Commencez par importer les espaces de noms nécessaires pour lancer votre parcours Aspose.Zip :

```csharp
using Aspose.Zip;
using System;
using System.IO;
```

## Décompresser un seul fichier avec Aspose.Zip pour .NET

### Étape 1 : définissez votre répertoire de documents

 Commencez par spécifier le répertoire dans lequel vos documents sont stockés. Remplacer`"Your Document Directory"` avec le chemin réel.

```csharp
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer un fichier compressé

Utilisez l'extrait de code suivant pour créer un fichier compressé que nous décompresserons ultérieurement.

```csharp
CompressSingleFile.Run();
```

### Étape 3 : Décompresser le fichier

Passons maintenant au vif du sujet : la décompression du fichier unique. Utilisez le code suivant :

```csharp
// ExStart : DécompresserSingleFile
using (FileStream fs = File.OpenRead(dataDir + "CompressSingleFile_out.zip"))
{
    using (Archive archive = new Archive(fs))
    {
        int percentReady = 0;
        archive.Entries[0].ExtractionProgressed += (s, e) =>
        {
            int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
            if (percent > percentReady)
            {
                Console.WriteLine(string.Format("{0}% decompressed", percent));
                percentReady = percent;
            }
        };
        archive.Entries[0].Extract(dataDir + "alice_extracted_out.txt");
    }
}
```

Ce code gère efficacement le processus de décompression, fournissant des mises à jour de progression en temps réel.

## Conclusion

Toutes nos félicitations! Vous avez réussi à naviguer dans les subtilités de la décompression d'un seul fichier à l'aide d'Aspose.Zip pour .NET. Profitez de la puissance de cette bibliothèque pour rationaliser vos tâches de manipulation de fichiers sans effort.

## FAQ

### Q1 : Puis-je compresser plusieurs fichiers à l’aide d’Aspose.Zip pour .NET ?

A1 : Oui, Aspose.Zip pour .NET prend en charge la compression de plusieurs fichiers. Reportez-vous à la documentation pour des instructions détaillées.

### Q2 : Aspose.Zip est-il compatible avec .NET Core ?

A2 : Absolument ! Aspose.Zip s'intègre parfaitement à .NET Framework et .NET Core.

### Q3 : Comment puis-je gérer les fichiers compressés protégés par mot de passe ?

A3 : Aspose.Zip fournit des méthodes pour travailler avec des archives protégées par mot de passe. Consultez la documentation pour obtenir des conseils.

### Q4 : Y a-t-il des considérations en matière de licence pour l'utilisation d'Aspose.Zip ?

 A4 : Consultez les informations de licence sur le[Site Aspose](https://purchase.aspose.com/buy).

### Q5 : Où puis-je demander de l'aide si je rencontre des problèmes ?

 A5 : Visitez le[Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour le soutien de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
