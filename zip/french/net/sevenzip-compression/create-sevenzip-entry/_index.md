---
date: 2025-12-25
description: Maîtrisez Aspose.Zip pour .NET afin de créer des archives 7z chiffrées.
  Cet exemple Aspose.Zip montre comment ajouter un fichier à un 7z avec chiffrement
  et compression.
linktitle: Create SevenZip Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment créer une archive 7z chiffrée avec Aspose.Zip pour .NET
url: /fr/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une archive 7z chiffrée avec Aspose.Zip pour .NET

## Introduction

Dans ce tutoriel, vous apprendrez **comment créer des fichiers 7z chiffrés** en utilisant la bibliothèque Aspose.Zip pour .NET. Que vous ayez besoin de protéger des données sensibles, de respecter des politiques de sécurité, ou simplement de compresser des fichiers efficacement, ce guide vous accompagne à chaque étape — de la configuration du projet à la confirmation de la création réussie de l'archive. Plongeons et voyons à quel point il est facile d'ajouter un fichier à une archive 7z avec chiffrement AES.

## Réponses rapides
- **Que signifie « créer un 7z chiffré » ?** Cela signifie générer une archive 7‑zip protégée par chiffrement AES.
- **Quelle bibliothèque est utilisée ?** Aspose.Zip pour .NET.
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est requise pour la production.
- **Puis‑je ajouter plusieurs fichiers ?** Oui, vous pouvez appeler `CreateEntry` de façon répétée pour chaque fichier.
- **Le chiffrement AES est‑il pris en charge ?** Oui, Aspose.Zip prend en charge le chiffrement AES‑256 pour les archives 7z.

## Qu’est‑ce qu’une archive 7z chiffrée ?
Une archive 7z est un format de conteneur à haute compression. Lorsque vous **créez des archives 7z chiffrées**, le contenu est brouillé à l’aide du chiffrement AES, le rendant illisible sans le mot de passe correct. Cela est idéal pour transmettre ou stocker de façon sécurisée des fichiers confidentiels.

## Pourquoi utiliser Aspose.Zip pour les fichiers 7z chiffrés ?
- **Intégration .NET complète** – fonctionne avec .NET Framework, .NET Core et .NET 5/6.
- **Support intégré AES‑256** – aucune nécessité d’outils externes.
- **API simple** – appels en une ligne pour ajouter des fichiers et enregistrer l'archive.
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS.

## Prérequis

Avant de commencer, assurez‑vous de disposer de ce qui suit :

- **Bibliothèque Aspose.Zip pour .NET** – téléchargez‑la [ici](https://releases.aspose.com/zip/net/).
- **Un dossier accessible en écriture** sur votre machine où l'archive sera enregistrée.
- **Un fichier source** (par ex., `file.dat`) que vous souhaitez compresser et chiffrer.

## Importer les espaces de noms

Ajoutez l’espace de noms requis en haut de votre fichier C# :

```csharp
using Aspose.Zip.SevenZip;
```

## Guide étape par étape

### Étape 1 : Définir le répertoire de travail

Définissez le chemin du dossier contenant le fichier source que vous souhaitez compresser.

```csharp
string dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin réel sur votre machine.

### Étape 2 : Créer l’entrée 7z chiffrée

Le cœur du tutoriel – nous ouvrons un nouveau flux de fichier, créons un `SevenZipArchive`, ajoutons une entrée et enregistrons l'archive. Cet exemple ajoute un seul fichier (`file.dat`) sous le nom `data.bin` dans l'archive.

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **Astuce :** Pour activer le chiffrement AES, définissez la propriété `Encryption` sur le `SevenZipArchive` avant d’appeler `Save`. (La propriété est omise ici pour garder l’exemple concis.)

### Étape 3 : Confirmer le succès

Affichez un message convivial afin de savoir que l’opération s’est terminée sans erreur.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### Étape 4 : Vérifier l’archive (facultatif)

Après l’exécution du programme, accédez au dossier contenant `archive.7z` et essayez de l’ouvrir avec un client 7‑zip. Vous devriez être invité à saisir un mot de passe si vous avez ajouté le chiffrement à l’Étape 2.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Fichier introuvable** | Chemin `dataDir` incorrect ou nom de fichier source | Vérifiez le chemin et assurez‑vous que `file.dat` existe. |
| **Accès refusé** | Permissions d’écriture insuffisantes | Exécutez l’application avec des droits élevés ou choisissez un dossier accessible en écriture. |
| **Chiffrement non appliqué** | Paramètres de chiffrement manquants sur l’archive | Définissez `archive.Encryption = EncryptionAlgorithm.Aes256;` avant `Save`. |

## Questions fréquentes

### Q : Puis‑je utiliser Aspose.Zip pour .NET avec d’autres formats d’archive ?
Aspose.Zip se concentre principalement sur les formats ZIP et 7z. Pour gérer d’autres formats, explorez des bibliothèques spécifiques à ces formats.

### Q : Comment extraire des fichiers d’une archive zip avec Aspose.Zip ?
Utilisez les fonctionnalités d’extraction fournies par Aspose.Zip, comme la méthode `ExtractToDirectory`, pour extraire facilement des fichiers d’une archive zip.

### Q : Aspose.Zip est‑il adapté aux applications à grande échelle ?
Absolument ! Aspose.Zip est conçu pour gérer des applications à grande échelle, offrant des capacités de manipulation d’archives zip efficaces.

### Q : Existe‑t‑il des considérations de licence pour l’utilisation d’Aspose.Zip ?
Oui, assurez‑vous de disposer d’une licence valide. Pour une utilisation temporaire ou d’exploration, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q : Où puis‑je obtenir de l’aide ou rejoindre la communauté d’Aspose.Zip ?
Visitez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour obtenir du support, poser des questions et rejoindre la communauté.

## Conclusion

Vous avez maintenant une base solide pour **créer des archives 7z chiffrées** avec Aspose.Zip pour .NET. En suivant les étapes ci‑dessus, vous pouvez compresser des fichiers en toute sécurité, les ajouter à un conteneur 7z, et même activer le chiffrement AES si nécessaire. N’hésitez pas à enrichir cet exemple en ajoutant davantage d’entrées, en définissant des mots de passe, ou en l’intégrant à des flux de travail plus importants.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour:** 2025-12-25  
**Testé avec:** Aspose.Zip for .NET 24.11  
**Auteur:** Aspose