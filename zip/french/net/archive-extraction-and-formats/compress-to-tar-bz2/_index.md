---
date: 2026-04-24
description: Apprenez à compresser un tar et à créer une archive TarBz2 dans .NET
  avec Aspose.Zip. Ce guide étape par étape montre comment ajouter des fichiers à
  un tar et générer des fichiers tarbz2 efficacement.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: Compression en TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser un tar et créer un TarBz2 avec Aspose.Zip pour .NET
url: /fr/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment compresser tar et créer un TarBz2 avec Aspose.Zip pour .NET

## Introduction

Dans ce tutoriel, vous découvrirez **comment compresser tar** les archives et les transformer en un fichier **TarBz2** compact en utilisant la bibliothèque **Aspose.Zip** pour .NET. Que vous créiez un utilitaire de sauvegarde, publiiez des paquets de déploiement ou ayez simplement besoin d’un bundle léger pour la distribution, les étapes ci‑dessous vous guideront pour ajouter des fichiers à tar, appliquer la compression Bzip2 et produire une archive prête à être partagée.

Avant de commencer, assurez‑vous d’avoir les prérequis listés plus loin dans ce guide afin de pouvoir suivre sans aucun problème.

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Zip for .NET  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes  
- **Ai‑je besoin d’une licence ?** Une licence temporaire est requise pour la production ; un essai gratuit est disponible  
- **Puis‑je compresser plusieurs fichiers ?** Oui – ajoutez autant d’entrées que vous le souhaitez à l’archive tar  
- **Est‑elle compatible avec .NET 6+ ?** Absolument, Aspose.Zip prend en charge .NET Framework et .NET Core/5/6  

## Qu’est‑ce qu’une archive TarBz2 ?

Un fichier **TarBz2** combine le conteneur **tar** traditionnel (qui préserve la structure des répertoires et les métadonnées des fichiers) avec la compression **Bzip2**, produisant ainsi un paquet très compressé `.tar.bz2`. Ce format est populaire sur les systèmes de type Unix car il offre un bon compromis entre le taux de compression et la vitesse de décompression.

## Pourquoi compresser des fichiers en TarBz2 avec Aspose.Zip ?

- **Vitesse & Simplicité** – Des appels API en une ligne gèrent à la fois la création de tar et la compression Bzip2.  
- **Cross‑platform** – Fonctionne sur les runtimes .NET Windows, Linux et macOS.  
- **Contrôle fin** – Choisissez les fichiers à inclure, définissez des noms d’entrée personnalisés et diffusez directement sur le disque.  
- **Support .NET robuste** – Parfait pour les scénarios **tar archive .net**, des applications console aux services web.  

## Prérequis

- **Aspose.Zip for .NET** – Téléchargez le dernier package depuis le site officiel : [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – Un dossier contenant les fichiers que vous souhaitez archiver. Dans les exemples nous le référencions avec la variable `dataDir`.

> **Astuce :** Conservez vos fichiers sources dans un dossier dédié pour éviter l’inclusion accidentelle de fichiers indésirables.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin de pouvoir accéder aux classes Tar et Bzip2 d’Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Étape 1 : Définir le répertoire des documents

Définissez le chemin qui pointe vers le dossier contenant les fichiers que vous souhaitez archiver.

```csharp
string dataDir = "Your Document Directory";
```

> Remplacez `"Your Document Directory"` par le chemin absolu ou relatif de votre dossier source.

## Étape 2 : Ajouter des fichiers à tar et créer une archive TarBz2

Le cœur du processus consiste à créer un `TarArchive`, ajouter des entrées, puis l’envelopper avec un `Bzip2Archive`. Le code ci‑dessous montre **comment créer tar** et le compresser en **TarBz2** avec un style propre et basé sur le pattern disposable.

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

- `CreateEntry` **ajoute des fichiers à tar** – vous pouvez appeler cette méthode pour chaque fichier nécessaire dans l’archive.  
- `bz2.SetSource(archive)` indique à l’archive Bzip2 de compresser le flux tar complet.  
- `bz2.Save(...)` écrit le fichier final **TarBz2** sur le disque.

**Astuce :** Pour **ajouter des fichiers à tar** en masse, répétez simplement `archive.CreateEntry` pour chaque fichier avant d’appeler `bz2.Save`.

## Problèmes courants & solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **File not found** error | Chemin `dataDir` incorrect ou extension de fichier manquante | Vérifiez le chemin complet et assurez‑vous que le fichier existe. |
| **Empty archive** | Aucune entrée ajoutée avant `bz2.Save` | Ajoutez au moins un appel `CreateEntry`. |
| **Permission denied** | L’application n’a pas les droits d’écriture sur le dossier de sortie | Exécutez l’application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

## Questions fréquemment posées

**Q : Aspose.Zip est‑il compatible avec toutes les applications .NET ?**  
R : Oui. Il fonctionne avec .NET Framework, .NET Core, .NET 5/6 et les runtimes plus récents.

**Q : Puis‑je compresser plusieurs fichiers simultanément ?**  
R : Absolument. Appelez `CreateEntry` pour chaque fichier avant d’enregistrer l’archive.

**Q : Où puis‑je trouver de la documentation supplémentaire ?**  
R : La documentation détaillée est disponible [ici](https://reference.aspose.com/zip/net/).

**Q : Comment obtenir une licence temporaire pour Aspose.Zip ?**  
R : Vous pouvez en demander une [ici](https://purchase.aspose.com/temporary-license/).

**Q : Une version d’essai gratuite est‑elle disponible ?**  
R : Oui, téléchargez une version d’essai [ici](https://releases.aspose.com/).

## Conclusion

Vous avez maintenant appris **comment compresser tar**, ajouter des fichiers, et envelopper le résultat dans un flux Bzip2 pour produire une archive **TarBz2** en utilisant Aspose.Zip pour .NET. Cette approche est rapide, fiable et fonctionne sur toutes les plateformes .NET modernes. N’hésitez pas à expérimenter avec des ensembles de fichiers plus volumineux, des noms d’entrée personnalisés, ou à intégrer le code dans vos propres pipelines de sauvegarde ou de déploiement.

Si vous rencontrez des difficultés, la communauté Aspose.Zip est prête à aider—rendez‑vous simplement sur le [forum de support Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}