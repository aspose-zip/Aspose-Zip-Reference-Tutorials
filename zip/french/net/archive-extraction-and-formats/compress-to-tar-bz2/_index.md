---
date: 2025-11-29
description: Apprenez comment ajouter des fichiers à un tar et compresser des fichiers
  au format tarbz2 dans .NET avec Aspose.Zip. Ce guide étape par étape montre comment
  créer des archives tarbz2 efficacement.
linktitle: Compressing to TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Ajouter des fichiers à un tar et le compresser en TarBz2 avec Aspose.Zip pour
  .NET
url: /fr/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des fichiers à un tar et compresser en TarBz2 avec Aspose.Zip pour .NET

## Introduction

Bienvenue dans notre guide complet sur **comment ajouter des fichiers à un tar** et les compresser au format TarBz2 en utilisant Aspose.Zip pour .NET. Que vous construisiez un utilitaire de sauvegarde, livriez des paquets de déploiement, ou ayez simplement besoin d’une archive compacte pour la distribution, ce tutoriel vous accompagne pas à pas avec des explications claires et des conseils pratiques.

Avant de commencer, assurons‑nous que vous disposez de tout le nécessaire.

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Zip pour .NET
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes
- **Ai‑je besoin d’une licence ?** Une licence temporaire est requise en production ; un essai gratuit est disponible
- **Puis‑je compresser plusieurs fichiers ?** Oui – ajoutez autant d’entrées que vous le souhaitez à l’archive Tar
- **Est‑ce compatible avec .NET 6+ ?** Absolument, Aspose.Zip prend en charge .NET Framework et .NET Core/5/6

## Qu’est‑ce que « add files to tar » ?
Ajouter des fichiers à un **tar** (Tape Archive) crée un conteneur unique non compressé qui préserve la structure des répertoires et les métadonnées des fichiers. Lorsque vous appliquez ensuite la compression Bzip2, le résultat est une archive **tar.bz2** (TarBz2) – idéale pour un stockage et un transfert efficaces.

## Pourquoi compresser des fichiers en TarBz2 avec Aspose.Zip ?
- **Rapidité & Simplicité** – Des appels API en une ligne gèrent à la fois la création du tar et la compression Bzip2.
- **Cross‑platform** – Fonctionne sous Windows, Linux et macOS avec les runtimes .NET.
- **Contrôle fin** – Choisissez les fichiers à inclure, définissez des noms d’entrée personnalisés et diffusez directement sur le disque.

## Prérequis

- **Aspose.Zip pour .NET** – Téléchargez le dernier package depuis le site officiel : [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)
- **Répertoire de documents** – Un dossier contenant les fichiers que vous souhaitez archiver. Dans les exemples, nous le référencions avec la variable `dataDir`.

> **Astuce :** Conservez vos fichiers sources dans un dossier dédié afin d’éviter l’inclusion accidentelle de fichiers indésirables.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin de pouvoir accéder aux classes Tar et Bzip2 d’Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Étape 1 : Définir le répertoire de documents

Définissez le chemin qui pointe vers le dossier contenant les fichiers à archiver.

```csharp
string dataDir = "Your Document Directory";
```

> Remplacez `"Your Document Directory"` par le chemin absolu ou relatif de votre dossier source.

## Étape 2 : Ajouter des fichiers au tar et créer une archive TarBz2

Le cœur du processus consiste à créer un `TarArchive`, ajouter des entrées, puis l’envelopper avec un `Bzip2Archive`. Le code ci‑dessous montre **comment créer un tarbz2** en suivant le modèle disposable.

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

- `CreateEntry` ajoute chaque fichier au conteneur **tar**.  
- `bz2.SetSource(archive)` indique à l’archive Bzip2 de compresser l’ensemble du flux tar.  
- `bz2.Save(...)` écrit le fichier final **tar.bz2** sur le disque.

**Conseil :** Pour **compresser des fichiers en tarbz2** en masse, répétez simplement `archive.CreateEntry` pour chaque fichier nécessaire.

## Problèmes courants & Solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Fichier introuvable** | Chemin `dataDir` incorrect ou extension manquante | Vérifiez le chemin complet et assurez‑vous que le fichier existe. |
| **Archive vide** | Aucune entrée ajoutée avant `bz2.Save` | Ajoutez au moins un appel `CreateEntry`. |
| **Permission refusée** | L’application n’a pas les droits d’écriture sur le dossier de sortie | Exécutez l’application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

## Foire aux questions

**Q : Aspose.Zip est‑il compatible avec toutes les applications .NET ?**  
R : Oui. Il fonctionne avec .NET Framework, .NET Core, .NET 5/6 et les runtimes plus récents.

**Q : Puis‑je compresser plusieurs fichiers simultanément ?**  
R : Absolument. Appelez `CreateEntry` pour chaque fichier avant d’enregistrer l’archive.

**Q : Où puis‑je trouver de la documentation supplémentaire ?**  
R : La documentation détaillée est disponible [ici](https://reference.aspose.com/zip/net/).

**Q : Comment obtenir une licence temporaire pour Aspose.Zip ?**  
R : Vous pouvez en demander une [ici](https://purchase.aspose.com/temporary-license/).

**Q : Existe‑t‑il une version d’essai gratuite ?**  
R : Oui, téléchargez une version d’essai [ici](https://releases.aspose.com/).

## Conclusion

Vous avez maintenant appris comment **ajouter des fichiers à un tar**, les envelopper dans un flux Bzip2, et produire une archive **TarBz2** en utilisant Aspose.Zip pour .NET. Cette technique est rapide, fiable et fonctionne sur toutes les plateformes .NET modernes. N’hésitez pas à expérimenter avec des ensembles de fichiers plus volumineux, des noms d’entrée personnalisés, ou à intégrer le code dans vos propres pipelines de sauvegarde ou de déploiement.

Si vous rencontrez des difficultés, la communauté Aspose.Zip est prête à vous aider — rendez‑vous simplement sur le [forum de support Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Dernière mise à jour :** 2025-11-29  
**Testé avec :** Aspose.Zip pour .NET (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}