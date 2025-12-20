---
date: 2025-12-20
description: Apprenez à protéger par mot de passe une archive zip en utilisant Aspose.Zip
  pour .NET avec le chiffrement traditionnel. Ce guide montre comment chiffrer les
  fichiers zip et ajouter des fichiers à une archive zip de manière efficace.
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Protéger une archive Zip par mot de passe avec Aspose.Zip .NET
url: /fr/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Protéger par mot de passe une archive Zip avec Aspose.Zip .NET

## Introduction

Bienvenue dans ce tutoriel pas à pas sur **comment protéger par mot de passe des fichiers d'archive zip** avec le chiffrement traditionnel à l'aide d'Aspose.Zip pour .NET. Aspose.Zip est une bibliothèque puissante qui permet aux développeurs de créer, lire et manipuler des archives zip sans effort. Dans ce guide, nous vous montrerons comment compresser plusieurs fichiers, les ajouter à un zip et sécuriser l'archive avec un mot de passe — tout en conservant un code propre et maintenable.

## Réponses rapides
- **Que signifie « protéger par mot de passe une archive zip » ?** Cela consiste à chiffrer un fichier zip afin que son contenu ne puisse être ouvert qu'après saisie du mot de passe correct.  
- **Quelle bibliothèque gère cela sous .NET ?** Aspose.Zip pour .NET offre une prise en charge intégrée du chiffrement traditionnel.  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise pour un usage en production ; une version d’essai gratuite est disponible.  
- **Puis‑je exécuter cela sous Linux ?** Absolument — Aspose.Zip est multiplateforme et fonctionne sous Windows, Linux et macOS.  
- **Combien de fichiers puis‑je ajouter ?** Vous pouvez ajouter un nombre illimité de fichiers ; l’exemple montre trois fichiers, mais l’approche est extensible.

## Qu’est‑ce qu’une « archive zip protégée par mot de passe » ?

Une archive zip protégée par mot de passe utilise le chiffrement (dans ce cas, le chiffrement PKZIP traditionnel) pour brouiller les données des fichiers à l’intérieur de l’archive. Lorsqu’un utilisateur tente d’extraire l’archive, le mot de passe correct doit être fourni pour déchiffrer le contenu.

## Pourquoi utiliser Aspose.Zip pour cette tâche ?

- **API simple** – Une seule ligne de code pour activer le chiffrement.  
- **Aucune dépendance externe** – Pure .NET, aucune DLL native.  
- **Multiplateforme** – Fonctionne avec .NET Framework, .NET Core et .NET 5/6+.  
- **Optimisé pour les performances** – Gère efficacement les gros fichiers.

## Prérequis

Avant de commencer, assurez‑vous de disposer de :

- **Aspose.Zip pour .NET** – Téléchargez‑le depuis le site officiel [ici](https://releases.aspose.com/zip/net/).  
- **Un dossier contenant des fichiers** – Remplacez `"Your Document Directory"` dans le code d’exemple par le chemin réel contenant les fichiers que vous souhaitez zipper.

## Importer les espaces de noms

Commencez par importer les espaces de noms requis afin de pouvoir travailler avec les classes Aspose.Zip :

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Comment chiffrer un zip avec le chiffrement traditionnel

### Étape 1 : Configurer le fichier Zip (Protéger l’archive zip par mot de passe)

Créez le fichier zip et configurez les paramètres de chiffrement traditionnel. Le mot de passe `"p@s$"` n’est qu’un exemple — remplacez‑le par un mot de passe fort pour les projets réels.

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### Ajouter des fichiers à l’archive zip

Ajoutez maintenant chaque fichier que vous souhaitez inclure. La méthode `CreateEntry` prend le nom du fichier à l’intérieur du zip et un flux (`source1`, `source2`, `source3`) qui pointe vers les données réelles du fichier.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### Enregistrer le fichier Zip (compresser les fichiers avec mot de passe)

Enfin, persistez l’archive sur le disque. Cette étape écrit le fichier zip chiffré à l’emplacement que vous avez spécifié précédemment.

```csharp
archive.Save(zipFile);
```

> **Astuce :** Fermez toujours les flux (`using` statements) pour libérer rapidement les poignées de fichiers, surtout lorsqu’il s’agit de gros fichiers.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Erreur de mot de passe incorrect** | Incohérence du mot de passe ou faute de frappe dans `TraditionalEncryptionSettings` | Vérifiez la chaîne du mot de passe et assurez‑vous d’utiliser le même mot de passe lors de l’extraction. |
| **Fichier non ajouté** | Le flux source (`sourceX`) est nul ou a été libéré | Ouvrez les flux source avec `File.OpenRead` avant de les passer à `CreateEntry`. |
| **Ralentissement des performances sur de gros fichiers** | Utilisation du niveau de compression par défaut avec de nombreuses entrées volumineuses | Envisagez de définir `CompressionLevel` dans `ArchiveEntrySettings` pour un traitement plus rapide. |

## Questions fréquentes

**Q : Puis‑je utiliser cela à la fois sous Windows et Linux ?**  
R : Oui, Aspose.Zip pour .NET est entièrement multiplateforme et fonctionne sous Windows, Linux et macOS.

**Q : Une version d’essai gratuite est‑elle disponible ?**  
R : Absolument — vous pouvez explorer une version d’essai gratuite d’Aspose.Zip pour .NET [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir de l’aide si j’ai des problèmes ?**  
R : Consultez le forum officiel [Aspose.Zip](https://forum.aspose.com/c/zip/37) pour l’aide de la communauté et le support officiel.

**Q : Les licences temporaires sont‑elles une option pour l’évaluation ?**  
R : Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où se trouve la documentation complète de l’API ?**  
R : La référence détaillée est disponible [ici](https://reference.aspose.com/zip/net/).

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.Zip 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}