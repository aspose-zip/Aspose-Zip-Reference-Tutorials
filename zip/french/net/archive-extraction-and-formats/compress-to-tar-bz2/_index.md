---
date: 2026-08-07
description: Apprenez comment ajouter des fichiers à tar et générer une archive TarBz2
  en .NET avec Aspose.Zip. Ce guide étape par étape montre la création de tar, la
  compression Bzip2 et des conseils de bonnes pratiques.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Compression en TarBz2
og_description: Ajoutez des fichiers à tar et générez une archive TarBz2 en .NET avec
  Aspose.Zip. Ce guide couvre la création de tar, la compression Bzip2 et des conseils
  de dépannage.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Ajouter des fichiers à tar et créer une archive TarBz2 avec Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Ajouter des fichiers à tar et créer une archive TarBz2 avec Aspose.Zip
url: /fr/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des fichiers à un tar et créer une archive TarBz2 avec Aspose.Zip

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Zip for .NET  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes  
- **Ai‑je besoin d’une licence ?** Une licence temporaire est requise pour la production ; un essai gratuit est disponible  
- **Puis‑je compresser plusieurs fichiers ?** Oui – ajoutez autant d’entrées que vous le souhaitez à l’archive tar  
- **Est‑elle compatible avec .NET 6+ ?** Absolument, Aspose.Zip prend en charge .NET Framework et .NET Core/5/6  

## Qu’est‑ce qu’une archive TarBz2 ?

Un fichier TarBz2 combine le conteneur **tar** traditionnel (qui préserve la structure des répertoires et les métadonnées des fichiers) avec la compression **Bzip2**, ce qui donne un paquet fortement compressé `.tar.bz2`. Ce format est populaire sur les systèmes de type Unix car il offre un bon compromis entre le taux de compression et la vitesse de décompression.

## Pourquoi compresser des fichiers en TarBz2 avec Aspose.Zip ?

Aspose.Zip peut générer une archive TarBz2 en **deux appels d’API** tout en gérant les flux de manière efficace. Il prend en charge **plus de 50 formats d’archive et de compression**, traite des fichiers jusqu’à **2 Go** sans charger l’ensemble de l’archive en mémoire, et fonctionne sur les runtimes .NET Windows, Linux et macOS. La bibliothèque vous offre également un contrôle granulaire sur les noms d’entrée, les horodatages et les niveaux de compression, ce qui la rend idéale tant pour les utilitaires en ligne de commande que pour les services web.

## Prérequis

- **Aspose.Zip for .NET** – téléchargez le dernier package depuis le site officiel : [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Répertoire de documents** – un dossier contenant les fichiers que vous souhaitez archiver. Dans les exemples, nous le référencions avec la variable `dataDir`.

> **Astuce :** Conservez vos fichiers sources dans un dossier dédié afin d’éviter l’inclusion accidentelle de fichiers indésirables.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin de pouvoir accéder aux classes Tar et Bzip2 d’Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Étape 1 : définir le répertoire de documents

Définissez le chemin qui pointe vers le dossier contenant les fichiers que vous souhaitez archiver.

```csharp
string dataDir = "Your Document Directory";
```

> Remplacez `"Your Document Directory"` par le chemin absolu ou relatif de votre dossier source.

## Étape 2 : ajouter des fichiers au tar et créer une archive TarBz2

`TarArchive` représente un conteneur tar en mémoire pouvant contenir plusieurs entrées de fichiers.  
`Bzip2Archive` compresse un flux à l’aide de l’algorithme Bzip2.  
La méthode `CreateEntry` ajoute un fichier à l’archive tar en tant que nouvelle entrée.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **ajoute des fichiers au tar** – vous pouvez appeler cette méthode pour chaque fichier nécessaire dans l’archive.  
- `bz2.SetSource(archive)` indique à l’archive Bzip2 de compresser l’ensemble du flux tar.  
- `bz2.Save(...)` écrit le fichier final **TarBz2** sur le disque.

**Astuce :** Pour **ajouter des fichiers au tar** en masse, répétez simplement `archive.CreateEntry` pour chaque fichier avant d’appeler `bz2.Save`.

## Comment ajouter des fichiers au tar ?

Chargez le répertoire source, créez une instance `TarArchive`, ajoutez chaque fichier avec `CreateEntry`, puis encapsulez le flux tar dans un `Bzip2Archive` et appelez `Save`. Ce modèle en deux étapes ajoute un nombre quelconque de fichiers et produit un fichier `.tar.bz2` en un seul flux fluide, éliminant le besoin de fichiers temporaires ou d’outils externes.

## Problèmes courants & solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Erreur : fichier non trouvé** | Chemin `dataDir` incorrect ou extension de fichier manquante | Vérifiez le chemin complet et assurez‑vous que le fichier existe. |
| **Archive vide** | Aucune entrée ajoutée avant `bz2.Save` | Ajoutez au moins un appel à `CreateEntry`. |
| **Permission refusée** | L’application n’a pas les droits d’écriture sur le dossier de sortie | Exécutez l’application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

## Questions fréquemment posées

**Q : Aspose.Zip est‑il compatible avec toutes les applications .NET ?**  
**R :** Oui. Il fonctionne avec .NET Framework, .NET Core, .NET 5/6 et les runtimes plus récents.

**Q : Puis‑je compresser plusieurs fichiers simultanément ?**  
**R :** Absolument. Appelez `CreateEntry` pour chaque fichier avant d’enregistrer l’archive.

**Q : Où puis‑je trouver une documentation supplémentaire ?**  
**R :** Des documents détaillés sont disponibles dans la **référence API Aspose.Zip .NET** : [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q : Comment obtenir une licence temporaire pour Aspose.Zip ?**  
**R :** Vous pouvez **demander une licence temporaire** ici : [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q : Une version d’essai gratuite est‑elle disponible ?**  
**R :** Oui, **téléchargez une version d’essai depuis les releases d’Aspose** : [download a trial version](https://releases.aspose.com/).

## Conclusion

Vous savez maintenant **comment ajouter des fichiers au tar**, compresser le flux tar avec Bzip2 et générer une archive **TarBz2** en utilisant Aspose.Zip pour .NET. Cette approche est rapide, efficace en mémoire et fonctionne sur toutes les plateformes .NET modernes. N’hésitez pas à expérimenter avec des ensembles de fichiers plus volumineux, des noms d’entrée personnalisés, ou à intégrer le code dans vos propres pipelines de sauvegarde ou de déploiement.

Si vous rencontrez des difficultés, la communauté Aspose.Zip est prête à aider—rendez‑vous simplement sur le **forum de support Aspose.Zip** : [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

**Dernière mise à jour :** 2026-08-07  
**Testé avec :** Aspose.Zip for .NET (latest release)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer une archive tar et ajouter des fichiers au tar avec Aspose.Zip pour .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Ajouter des fichiers au tar et créer une archive tarxz avec Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Ajouter des fichiers au tar et compresser en TarZ avec Aspose.Zip pour .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}