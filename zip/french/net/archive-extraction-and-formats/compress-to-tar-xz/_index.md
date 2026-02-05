---
date: 2026-02-05
description: Apprenez à ajouter des fichiers à un tar et à créer des archives tarxz
  dans .NET en utilisant Aspose.Zip. Ce guide montre comment compresser des fichiers
  en tarxz avec une grande efficacité.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Ajouter des fichiers à un tar, créer une archive tarxz .NET avec Aspose.Zip
url: /fr/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter des fichiers à un tar, créer une archive tarxz .NET avec Aspise.Zip

## Introduction

Si vous devez **add files to tar** puis les compresser dans une archive tarxz en utilisant .NET, Aspose.Zip for .NET rend le processus simple et fiable. Que vous empaquetiez des journaux, des fichiers de configuration ou tout autre actif pour le stockage ou la transmission, la compression au format TarXz vous offre un taux de compression élevé tout en conservant la structure tar familière. Dans ce tutoriel, nous parcourrons les étapes exactes — avec des extraits de code — afin que vous puissiez intégrer la création de tarxz dans vos applications .NET en toute confiance.

## Réponses rapides
- **Quelle est la classe principale ?** `TarArchive` from `Aspose.Zip.Tar`
- **Comment compresser tarxz ?** Utilisez `SaveXzCompressed` after adding entries
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Licence requise ?** Oui, une licence Aspose.Zip valide pour la production
- **Temps d'implémentation typique ?** ~5‑10 minutes

## Qu'est-ce qu'une archive TarXz ?

Une **archive TarXz** combine le conteneur Unix traditionnel `tar` avec la compression XZ. La partie tar regroupe plusieurs fichiers dans un seul flux, tandis que XZ fournit une compression forte et sans perte. Ce format est populaire pour la distribution de code source, les sauvegardes et les grands ensembles de données car il conserve les structures de répertoires et obtient des tailles de fichier plus petites que le tar ou le zip classiques.

## Pourquoi ajouter des fichiers à un tar et compresser en tarxz avec Aspose.Zip ?

- **Ratio de compression élevé** – XZ compresse souvent 30‑50 % plus petit que gzip.  
- **Compatibilité multiplateforme** – Les fichiers TarXz peuvent être ouverts sur Linux, macOS et Windows.  
- **API simple** – Aspose.Zip abstrait les détails bas‑niveau, vous permettant de vous concentrer sur votre logique métier.  
- **Pas d'outils externes** – Tout s'exécute à l'intérieur de votre processus .NET, parfait pour le cloud ou les pipelines CI.  

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

- **Aspose.Zip for .NET** installé (téléchargez depuis la [documentation officielle d'Aspose.Zip](https://reference.aspose.com/zip/net/)).  
- Un dossier contenant les fichiers que vous souhaitez archiver. Dans les exemples ci‑dessous, ce dossier est référencé par la variable `dataDir`.  
- Une licence Aspose.Zip valide (optionnelle pour l'évaluation, requise pour la production).

## Importer les espaces de noms

Tout d'abord, importez les espaces de noms qui exposent la fonctionnalité TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Comment ajouter des fichiers à un tar avec Aspose.Zip

### Étape 1 : Initialiser un `TarArchive`

Créez une nouvelle instance de `TarArchive` qui contiendra les fichiers que vous voulez compresser.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Astuce :** L’instruction `using` garantit que l’archive est correctement libérée, libérant ainsi les ressources non gérées.

### Étape 2 : Ajouter des fichiers à l'archive

Ajoutez chaque fichier que vous souhaitez inclure. Dans cet exemple nous ajoutons deux fichiers texte, mais vous pouvez ajouter autant d’entrées que nécessaire.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Pourquoi c’est important :** Ajouter les entrées avant la compression permet à Aspose.Zip de construire d’abord le conteneur tar, puis d’appliquer la compression XZ en une seule étape.

### Étape 3 : Enregistrer l'archive avec compression XZ

Enfin, écrivez l’archive tar sur le disque en utilisant la compression XZ. Le fichier résultant aura l’extension `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Résultat :** Vous disposez maintenant d’un fichier `archive.tar.xz` entièrement compressé, pouvant être transféré, stocké ou décompressé sur n’importe quelle plateforme supportant TarXz.

## Problèmes courants & solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Exception « File not found »** | Chemin `dataDir` incorrect | Vérifiez que le chemin du répertoire se termine par une barre oblique inverse (`\`) ou utilisez `Path.Combine`. |
| **Utilisation élevée de mémoire** | Fichiers très volumineux compressés en mémoire | Utilisez `TarArchive` en mode streaming (surcharge `SaveXzCompressed` qui accepte un `Stream`). |
| **Licence non appliquée** | Fichier de licence manquant | Chargez la licence au démarrage de l'application : `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Questions fréquentes

**Q : Aspose.Zip est‑il compatible avec tous les environnements .NET ?**  
R : Oui, Aspose.Zip fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6+. Consultez la [documentation](https://reference.aspose.com/zip/net/) pour plus de détails.

**Q : Comment obtenir une licence temporaire pour Aspose.Zip ?**  
R : Vous pouvez demander une licence temporaire depuis la [page de licence temporaire d'Aspose](https://purchase.aspose.com/temporary-license/).

**Q : Existe‑t‑il des exemples supplémentaires pour d’autres formats d’archive ?**  
R : Absolument — explorez l’ensemble complet d’exemples dans la [référence API d'Aspose.Zip](https://reference.aspose.com/zip/net/).

**Q : Où puis‑je obtenir de l’aide ou discuter des problèmes ?**  
R : Rejoignez la conversation sur le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour le support communautaire et les réponses officielles.

**Q : Puis‑je essayer Aspose.Zip gratuitement avant d’acheter ?**  
R : Oui, un essai gratuit est disponible sur la [page de téléchargement d'Aspose.Zip](https://releases.aspose.com/zip/net).

## Conclusion

En suivant les étapes ci‑dessus, vous savez maintenant **comment ajouter des fichiers à un tar** et **créer des archives tarxz** avec Aspose.Zip en .NET. Cette approche vous fournit un paquet compact et portable qui peut être intégré de façon transparente à n’importe quel flux de travail .NET—que vous développiez un utilitaire de bureau, un service web ou un pipeline CI/CD automatisé.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}