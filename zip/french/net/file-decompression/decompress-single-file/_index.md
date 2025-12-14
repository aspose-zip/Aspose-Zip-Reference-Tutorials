---
date: 2025-12-14
description: Apprenez à décompresser un fichier zip en C# et à extraire un seul fichier
  zip en utilisant Aspose.Zip pour .NET dans vos projets C#.
linktitle: Decompressing a Single File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Décompresser zip c# – Extraire un fichier unique avec Aspose.Zip
url: /fr/net/file-decompression/decompress-single-file/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Décompresser zip c# – Extraire un fichier unique avec Aspose.Zip

## Introduction

Si vous devez **décompresser zip c#** des fichiers et extraire une seule entrée, Aspose.Zip for .NET rend la tâche simple. Dans ce tutoriel, nous parcourrons un exemple complet et réel qui montre comment extraire un seul fichier d’une archive ZIP, surveiller la progression et gérer le résultat de manière propre et maintenable. À la fin, vous serez à l’aise pour ajouter l’extraction de zip à n’importe quelle application C#.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Décompression d’une archive ZIP et extraction d’un seul fichier à l’aide d’Aspose.Zip for .NET.  
- **Quel mot‑clé principal est ciblé ?** decompress zip c#  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **.NET Core est‑il pris en charge ?** Oui – le même code fonctionne sur .NET Framework et .NET Core.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour une configuration de base.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants en place :

- Bibliothèque Aspose.Zip for .NET : téléchargez et installez la bibliothèque depuis la [Documentation Aspose.Zip for .NET](https://reference.aspose.com/zip/net/).
- Environnement de développement : disposez d’un environnement de développement .NET fonctionnel, incluant Visual Studio ou tout autre IDE compatible.
- Connaissances de base en C# : familiarisez‑vous avec les bases de la programmation C#.

Maintenant, mettons les mains dans le code !

## Importer les espaces de noms

Commencez par importer les espaces de noms nécessaires pour démarrer votre aventure avec Aspose.Zip :

```csharp
using Aspose.Zip;
using System;
using System.IO;
```

## Guide étape par étape pour décompresser zip c#

### Étape 1 : Définir votre répertoire de documents

Commencez par spécifier le répertoire où vos documents sont stockés. Remplacez `"Your Document Directory"` par le chemin réel.

```csharp
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer un fichier compressé (configuration de démonstration)

L’appel suivant crée un fichier ZIP d’exemple que nous décompresserons plus tard. Cela reflète un scénario typique où vous avez déjà une archive ZIP.

```csharp
CompressSingleFile.Run();
```

### Étape 3 : Décompresser le fichier – extraire un fichier ZIP unique

Passons maintenant au cœur du sujet – extraire l’entrée unique. Le code ci‑dessous ouvre l’archive ZIP, attache un gestionnaire de progression et extrait la première entrée vers un fichier texte.

```csharp
// ExStart: DecompressSingleFile
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

Cet extrait **extrait une seule entrée zip** tout en affichant la progression en temps réel (par ex., « 30 % décompressé »). Vous pouvez adapter l’index (`Entries[0]`) pour cibler tout autre fichier dans l’archive.

## Pourquoi utiliser Aspose.Zip pour la décompression de fichiers C# ?

- **Aucune dépendance externe** – bibliothèque pure .NET.  
- **Prend en charge les grandes archives** grâce au streaming, ce qui maintient une faible consommation de mémoire.  
- **Événements de progression intégrés** facilitent la fourniture de retours UI.  
- **Fonctionne sur .NET Framework, .NET Core et .NET 5/6**.

## Problèmes courants et astuces

- **Séparateurs de chemin de fichier** – utilisez `Path.Combine` pour la sécurité multiplateforme.  
- **ZIP protégés par mot de passe** – définissez `archive.Password` avant l’extraction.  
- **Entrées multiples** – parcourez `archive.Entries` et comparez par `FileName`.

## Questions fréquentes

### Q1 : Puis‑je compresser plusieurs fichiers avec Aspose.Zip for .NET ?

R1 : Oui, Aspose.Zip for .NET prend en charge la compression de plusieurs fichiers. Consultez la documentation pour des instructions détaillées.

### Q2 : Aspose.Zip est‑il compatible avec .NET Core ?

R2 : Absolument ! Aspose.Zip s’intègre parfaitement à la fois avec .NET Framework et .NET Core.

### Q3 : Comment gérer les fichiers compressés protégés par mot de passe ?

R3 : Aspose.Zip propose des méthodes pour travailler avec des archives protégées par mot de passe. Consultez la documentation pour obtenir des conseils.

### Q4 : Y a‑t‑il des considérations de licence pour l’utilisation d’Aspose.Zip ?

R4 : Consultez les informations de licence sur le [site Aspose](https://purchase.aspose.com/buy).

### Q5 : Où puis‑je obtenir de l’aide en cas de problème ?

R5 : Rendez‑vous sur le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour le support communautaire.

## Conclusion

Félicitations ! Vous avez réussi à maîtriser les subtilités du **décompress zip c#** et à extraire un seul fichier avec Aspose.Zip for .NET. Intégrez ce modèle dans vos applications pour simplifier la gestion des fichiers, améliorer l’expérience utilisateur et garder votre base de code propre.

---

**Dernière mise à jour :** 2025-12-14  
**Testé avec :** Aspose.Zip for .NET 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}