---
date: 2025-12-05
description: Apprenez à créer des archives tarxz avec .NET et à compresser des fichiers
  tarxz en utilisant Aspose.Zip pour .NET. Suivez ce guide étape par étape pour un
  stockage et une transmission efficaces.
language: fr
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment créer une archive tarxz .NET avec Aspose.Zip
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une archive tarxz .net avec Aspose.Zip

## Introduction

Si vous devez **créer une archive tarxz .net**, Aspose.Zip pour .NET rend le processus simple et fiable. Que vous emballiez des journaux, des fichiers de configuration ou tout autre actif pour le stockage ou la transmission, la compression au format TarXz vous offre un taux de compression élevé tout en conservant la structure tar familière. Dans ce tutoriel, nous parcourrons les étapes exactes — avec des extraits de code — afin que vous puissiez intégrer la création de tarxz dans vos applications .NET en toute confiance.

## Réponses rapides
- **Quelle est la classe principale ?** `TarArchive` de `Aspose.Zip.Tar`
- **Comment compresser en tarxz ?** Utilisez `SaveXzCompressed` après avoir ajouté les entrées
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Licence requise ?** Oui, une licence valide Aspose.Zip pour la production
- **Temps d’implémentation typique ?** ~5‑10 minutes

## Qu’est‑ce qu’une archive TarXz ?

Une **archive TarXz** combine le conteneur Unix traditionnel `tar` avec la compression XZ. La partie tar regroupe plusieurs fichiers en un seul flux, tandis que XZ fournit une compression forte et sans perte. Ce format est populaire pour la distribution de code source, les sauvegardes et les grands ensembles de données car il conserve les structures de répertoires et obtient des tailles de fichier plus petites que le tar ou le zip classiques.

## Pourquoi créer une archive tarxz .net avec Aspose.Zip ?

- **Taux de compression élevé** – XZ compresse souvent 30‑50 % plus petit que gzip.  
- **Compatibilité multiplateforme** – Les fichiers TarXz peuvent être ouverts sous Linux, macOS et Windows.  
- **API simple** – Aspose.Zip abstrait les détails bas‑niveau, vous laissant vous concentrer sur votre logique métier.  
- **Pas d’outils externes** – Tout s’exécute dans votre processus .NET, idéal pour le cloud ou les pipelines CI.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Aspose.Zip pour .NET** installé (téléchargez‑le depuis la documentation officielle [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Un dossier contenant les fichiers que vous souhaitez archiver. Dans les exemples ci‑dessous, ce dossier est référencé par la variable `dataDir`.  
- Une licence Aspose.Zip valide (optionnelle pour l’évaluation, obligatoire pour la production).

## Importer les espaces de noms

Commencez par importer les espaces de noms qui exposent la fonctionnalité TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Guide étape par étape pour créer une archive tarxz .net

### Étape 1 : Initialiser un `TarArchive`

Créez une nouvelle instance de `TarArchive` qui contiendra les fichiers à compresser.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Astuce :** L’instruction `using` garantit que l’archive est correctement libérée, libérant ainsi les ressources non gérées.

### Étape 2 : Ajouter des fichiers à l’archive

Ajoutez chaque fichier que vous souhaitez inclure. Dans cet exemple, nous ajoutons deux fichiers texte, mais vous pouvez ajouter autant d’entrées que nécessaire.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Pourquoi c’est important :** Ajouter les entrées avant la compression permet à Aspose.Zip de créer d’abord le conteneur tar, puis d’appliquer la compression XZ en une seule étape.

### Étape 3 : Enregistrer l’archive avec compression XZ

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
| **Utilisation importante de la mémoire** | Fichiers très volumineux compressés en mémoire | Utilisez `TarArchive` en mode flux (`SaveXzCompressed` surcharge acceptant un `Stream`). |
| **Licence non appliquée** | Fichier de licence manquant | Chargez la licence au démarrage de l’application : `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Foire aux questions

**Q : Aspose.Zip est‑il compatible avec tous les environnements .NET ?**  
R : Oui, Aspose.Zip fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6+. Consultez la [documentation](https://reference.aspose.com/zip/net/) pour plus de détails.

**Q : Comment obtenir une licence temporaire pour Aspose.Zip ?**  
R : Vous pouvez demander une licence temporaire depuis la [page de licence temporaire Aspose](https://purchase.aspose.com/temporary-license/).

**Q : Existe‑t‑il d’autres exemples pour d’autres formats d’archive ?**  
R : Bien sûr — explorez l’ensemble complet d’exemples dans la [référence API Aspose.Zip](https://reference.aspose.com/zip/net/).

**Q : Où puis‑je obtenir de l’aide ou discuter des problèmes ?**  
R : Rejoignez la conversation sur le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour le support communautaire et les réponses officielles.

**Q : Puis‑je essayer Aspose.Zip gratuitement avant d’acheter ?**  
R : Oui, un essai gratuit est disponible sur la [page de téléchargement Aspose.Zip](https://releases.aspose.com/zip/net).

## Conclusion

En suivant les étapes ci‑dessus, vous savez maintenant **comment compresser des fichiers tarxz** et, surtout, **comment créer une archive tarxz .net** avec Aspose.Zip. Cette approche vous fournit un paquet compact et portable qui peut être intégré de façon transparente dans n’importe quel flux de travail .NET — que vous développiez un utilitaire de bureau, un service web ou un pipeline CI/CD automatisé.

---

**Dernière mise à jour :** 2025-12-05  
**Testé avec :** Aspose.Zip pour .NET 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}