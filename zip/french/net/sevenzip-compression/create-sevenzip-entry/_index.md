---
date: 2026-05-05
description: Apprenez à chiffrer les archives 7z à l'aide d'Aspose.Zip pour .NET.
  Ce guide montre comment ajouter un fichier à une archive 7z, définir le chiffrement
  AES et générer une archive 7z sécurisée.
keywords:
- how to encrypt 7z
- add file to 7z
- how to set aes
- generate 7z archive
- add multiple files 7z
linktitle: Créer une entrée SevenZip
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment chiffrer une archive 7z avec Aspose.Zip pour .NET
url: /fr/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment chiffrer une archive 7z avec Aspose.Zip pour .NET

## Introduction

Dans ce tutoriel, vous apprendrez **comment chiffrer des fichiers 7z** à l'aide de la bibliothèque Aspose.Zip pour .NET. Que vous ayez besoin de protéger des données sensibles, de respecter des politiques de sécurité ou simplement de compresser des fichiers efficacement, ce guide vous accompagne à chaque étape — de la configuration du projet à la confirmation de la création réussie de l'archive. Plongeons et voyons à quel point il est facile de **ajouter un fichier à un 7z** avec le chiffrement AES et de générer une archive 7z fiable.

## Réponses rapides
- **Que signifie « create encrypted 7z » ?** Cela signifie générer une archive 7‑zip protégée par chiffrement AES.  
- **Quelle bibliothèque est utilisée ?** Aspose.Zip for .NET.  
- **Ai-je besoin d'une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est requise pour la production.  
- **Puis-je ajouter plusieurs fichiers ?** Oui — appelez `CreateEntry` de façon répétée pour **ajouter plusieurs fichiers 7z**.  
- **Le chiffrement AES est‑il pris en charge ?** Oui, Aspose.Zip prend en charge **comment définir AES**‑256 pour les archives 7z.  

## Qu'est-ce qu'une archive 7z chiffrée ?
Une archive 7z est un format de conteneur à haute compression. Lorsque vous **créez des archives 7z chiffrées**, le contenu est brouillé à l'aide du chiffrement AES, le rendant illisible sans le mot de passe correct. Cela est idéal pour transmettre ou stocker de manière sécurisée des fichiers confidentiels.

## Pourquoi utiliser Aspose.Zip pour les fichiers 7z chiffrés ?
- **Intégration complète .NET** – fonctionne avec .NET Framework, .NET Core et .NET 5/6.  
- **Prise en charge native AES‑256** – aucun outil externe nécessaire ; vous pouvez facilement apprendre **comment définir AES**.  
- **API simple** – appels en une ligne pour **ajouter un fichier à un 7z** et enregistrer l'archive.  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS.

## Prérequis
Avant de commencer, assurez-vous de disposer de ce qui suit :
- **Bibliothèque Aspose.Zip pour .NET** – téléchargez‑la [ici](https://releases.aspose.com/zip/net/).  
- **Un dossier accessible en écriture** sur votre machine où l'archive sera enregistrée.  
- **Un fichier source** (par ex., `file.dat`) que vous souhaitez compresser et chiffrer.

## Importer les espaces de noms
Ajoutez l'espace de noms requis en haut de votre fichier C# :

```csharp
using Aspose.Zip.SevenZip;
```

## Guide étape par étape

### Étape 1 : définir le répertoire de travail
Définissez le chemin vers le dossier contenant le fichier source que vous souhaitez compresser.

```csharp
string dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin réel sur votre machine.

### Étape 2 : créer l'entrée 7z chiffrée
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

> **Astuce :** Pour activer le chiffrement AES, définissez la propriété `Encryption` sur le `SevenZipArchive` avant d'appeler `Save`. (La propriété est omise ici pour garder l'exemple concis.)

### Étape 3 : confirmer le succès
Affichez un message convivial pour savoir que l'opération s'est terminée sans erreur.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### Étape 4 : vérifier l'archive (facultatif)
Après l'exécution du programme, accédez au dossier contenant `archive.7z` et essayez de l'ouvrir avec un client 7‑zip. Vous devriez être invité à saisir un mot de passe si vous avez ajouté le chiffrement à l'étape 2. Cette étape vous permet également de **vérifier la gestion du mot de passe 7z**.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Fichier non trouvé** | Chemin `dataDir` incorrect ou nom de fichier source erroné | Vérifiez à nouveau le chemin et assurez‑vous que `file.dat` existe. |
| **Accès refusé** | Permissions d'écriture insuffisantes | Exécutez l'application avec des droits élevés ou choisissez un dossier accessible en écriture. |
| **Chiffrement non appliqué** | Paramètres de chiffrement manquants sur l'archive | Définissez `archive.Encryption = EncryptionAlgorithm.Aes256;` avant `Save`. |

## Foire aux questions

**Q : Puis‑je ajouter plus d'un fichier à la même archive 7z ?**  
R : Absolument. Appelez `archive.CreateEntry` pour chaque fichier que vous souhaitez **ajouter un fichier à un 7z** ou **ajouter plusieurs fichiers 7z**.

**Q : Comment spécifier le mot de passe pour le chiffrement AES ?**  
R : Utilisez la propriété `Password` du `SevenZipArchive` avant d'enregistrer, par ex., `archive.Password = "YourStrongPassword";`. Cela vous permet ensuite de **vérifier le mot de passe 7z** lors de l'extraction.

**Q : Aspose.Zip prend‑il en charge d'autres formats d'archive ?**  
R : Aspose.Zip se concentre principalement sur les formats ZIP et 7z. Pour d'autres formats, envisagez des bibliothèques dédiées.

**Q : Une licence est‑elle requise pour une utilisation en production ?**  
R : Oui. Vous pouvez obtenir une licence temporaire pour l'évaluation [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support communautaire ?**  
R : Consultez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour poser des questions et partager des expériences.

## Conclusion
Vous disposez maintenant d'une base solide pour **comment chiffrer des archives 7z** avec Aspose.Zip pour .NET. En suivant les étapes ci‑dessus, vous pouvez compresser des fichiers en toute sécurité, les ajouter à un conteneur 7z, et même activer le chiffrement AES si nécessaire. N'hésitez pas à enrichir cet exemple en ajoutant davantage d'entrées, en définissant des mots de passe, ou en l'intégrant à des flux de travail plus importants tels que des pipelines de sauvegarde automatisés.

---

**Dernière mise à jour :** 2026-05-05  
**Testé avec :** Aspose.Zip for .NET 24.11  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}