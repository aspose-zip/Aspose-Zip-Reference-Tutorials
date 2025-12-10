---
date: 2025-12-09
description: Apprenez à compresser un répertoire avec Aspose.Zip pour .NET et à créer
  efficacement une archive zip .NET. Optimisez l'espace de stockage dans vos applications
  .NET.
linktitle: How to Compress a Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser un répertoire avec Aspose.Zip pour .NET
url: /fr/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Compression de répertoires sans effort avec Aspose.Zip pour .NET

Dans ce tutoriel, nous vous montrerons **comment compresser un répertoire** à l'aide d'Aspose.Zip pour .NET, une solution puissante pour gérer de grands ensembles de données et économiser de l'espace de stockage. Que vous développiez un utilitaire de bureau ou un service cloud, compresser les dossiers efficacement peut améliorer considérablement les performances et réduire les coûts. Nous parcourrons chaque étape, expliquerons la logique du code et soulignerons les pièges courants afin que vous puissiez appliquer la technique en toute confiance.

## Réponses rapides
- **Que fait Aspose.Zip ?** Il fournit une API .NET simple pour créer et extraire des archives ZIP sans dépendances externes.  
- **Combien de temps prend l'implémentation ?** Généralement moins de 10 minutes pour une compression de répertoire basique.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6+.  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise pour un usage en production.  
- **Puis‑je compresser plusieurs dossiers en même temps ?** Absolument — utilisez la méthode `CreateEntries` sur n’importe quelle collection `DirectoryInfo`.

## Introduction

Aspose.Zip pour .NET est une bibliothèque puissante qui permet aux développeurs .NET de travailler de manière fluide avec des fichiers et répertoires compressés. Que vous manipuliez de grands ensembles de données ou que vous ayez besoin de **générer des archives zip c#**, Aspose.Zip offre un ensemble complet de fonctionnalités pour les tâches de compression et de décompression.

## Qu’est‑ce que « how to compress directory » ?

Compresser un répertoire consiste à prendre tous les fichiers et sous‑dossiers d’un dossier donné et à les regrouper dans une archive ZIP unique. Cela réduit la taille globale, simplifie le transfert et préserve la hiérarchie du dossier d’origine.

## Pourquoi utiliser Aspose.Zip pour cette tâche ?

- **Vitesse & efficacité** : des algorithmes optimisés traitent rapidement les gros dossiers.  
- **Pure .NET** : aucune dépendance native ou outil tiers requis.  
- **Ensemble riche de fonctionnalités** : prise en charge de la protection par mot de passe, du streaming et de l’ajout d’entrées à la volée—idéal pour les scénarios **zip multiple files .net**.  
- **API cohérente** : fonctionne de la même façon sur .NET Framework, .NET Core et .NET 5/6.

## Prérequis

- **Aspose.Zip pour .NET** – téléchargez‑le [ici](https://releases.aspose.com/zip/net/).  
- **Environnement de développement** – Visual Studio, Rider ou tout IDE supportant C#.  
- **Répertoire de documents** – remplacez `"Your Document Directory"` dans le code par le chemin du dossier que vous souhaitez compresser.  
- **Documentation de référence** – consultez les docs officielles [ici](https://reference.aspose.com/zip/net/).

## Importer les espaces de noms

Commencez par importer les espaces de noms nécessaires. Ils vous donnent accès aux classes de compression de base.

```csharp
using Aspose.Zip;
using System.IO;
```

## Comment zipper un dossier avec Aspose.Zip

Voici un exemple simple qui montre **comment zipper le contenu d’un dossier**. Le même modèle peut être étendu pour **zip multiple files .net** ou pour créer des structures d’archives personnalisées.

### Étape 1 : Initialiser votre répertoire de documents

Définissez la variable `dataDir` sur le chemin du répertoire que vous voulez compresser.

```csharp
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer les fichiers ZIP de sortie

Ouvrez deux objets `FileStream` pour les fichiers ZIP de sortie. Cela montre comment générer plusieurs archives à partir de la même source—utile pour les sauvegardes versionnées.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Étape 3 : Compresser le répertoire

Utilisez la classe `Archive` pour ajouter chaque entrée du dossier cible. L’exemple utilise un dossier d’exemple nommé **CanterburyCorpus**, mais vous pouvez le pointer vers n’importe quel répertoire.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Astuce pro** : Si vous devez **create zip archive .net** avec un niveau de compression spécifique, définissez `archive.CompressionLevel` avant d’appeler `Save`.

## Problèmes courants et solutions

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Fichier ZIP vide | `dataDir` pointe vers le mauvais dossier ou il manque le slash final | Vérifiez le chemin et assurez‑vous que le dossier contient des fichiers |
| `UnauthorizedAccessException` | L’application n’a pas les permissions du système de fichiers | Exécutez Visual Studio en tant qu’administrateur ou accordez les droits de lecture/écriture |
| Utilisation mémoire élevée pour de très gros répertoires | Chargement de toutes les entrées en mémoire d’un coup | Utilisez `Archive.CreateEntryFromFile` dans une boucle pour diffuser les fichiers individuellement |

## Questions fréquentes (Supplémentaires)

**Q : Puis‑je ajouter un mot de passe à l’archive ZIP ?**  
R : Oui. Définissez `archive.Password = "yourPassword";` avant d’appeler `Save`.

**Q : Comment n’inclure que certains types de fichiers ?**  
R : Filtrez la collection `DirectoryInfo` avec `GetFiles("*.txt")` ou similaire avant d’appeler `CreateEntries`.

**Q : Existe‑t‑il un moyen de mettre à jour un ZIP existant sans le recréer ?**  
R : Aspose.Zip prend en charge les mises à jour incrémentielles via `Archive.UpdateEntry`.

## FAQ

### Q1 : Puis‑je utiliser Aspose.Zip pour .NET à la fois dans des projets commerciaux et personnels ?

R1 : Oui, Aspose.Zip pour .NET est licencié pour les usages commerciaux et personnels.

### Q2 : Existe‑t‑il une version d’essai gratuite ?

R2 : Oui, vous pouvez explorer une version d’essai gratuite [ici](https://releases.aspose.com/zip/net).

### Q3 : Comment obtenir du support pour Aspose.Zip pour .NET ?

R3 : Visitez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour le support communautaire ou envisagez d’acheter une [licence temporaire](https://purchase.aspose.com/temporary-license/) pour une assistance dédiée.

### Q4 : D’autres exemples et tutoriels sont‑ils disponibles ?

R4 : Oui, la [documentation](https://reference.aspose.com/zip/net/) contient de nombreux exemples et tutoriels complets.

### Q5 : Puis‑je acheter Aspose.Zip pour .NET ?

R5 : Bien sûr, vous pouvez effectuer un achat [ici](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-09  
**Testé avec :** Aspose.Zip 24.11 pour .NET  
**Auteur :** Aspose  

---