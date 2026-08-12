---
date: 2026-06-04
description: Apprenez à extraire un zip vers un dossier en utilisant Aspose.Zip pour
  .NET, y compris les archives protégées par mot de passe et l'extraction de zip chiffré.
keywords:
- extract zip to folder
- how to unzip zip
- extract zip with password
- unzip files in c#
- read zip archive c#
linktitle: extraire zip vers un dossier
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  headline: How to extract zip to folder with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  name: How to extract zip to folder with Aspose.Zip for .NET
  steps:
  - name: Open the ZIP file (or encrypted archive)
    text: The `FileStream` class provides a read‑only stream to the physical ZIP file
      on disk. Using a stream lets Aspose.Zip work with files located on network shares
      or embedded resources without first copying them to a temporary location.
  - name: Create an `Archive` instance (provide password when needed)
    text: The `Archive` class is the core object that represents a ZIP archive in
      memory. `ArchiveLoadOptions` defines settings used when loading an archive,
      such as the decryption password. Passing an `ArchiveLoadOptions` object with
      the `DecryptionPassword` property enables decryption of AES‑encrypted entri
  - name: Extract the contents to a destination folder
    text: '`ExtractToDirectory` iterates over every entry in the archive and writes
      it to the target path, preserving the original folder hierarchy. The method
      creates missing directories automatically and can also filter entries if you
      only need a subset. > **Pro tip:** If you only need to extract a subset of'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET supports ZIP, GZIP, and several other common
      formats.
    question: Does Aspose.Zip support other compression formats like GZIP?
  - answer: Absolutely. A valid license is required for production, but you can use
      the free trial for evaluation.
    question: Can I use Aspose.Zip in both commercial and non‑commercial projects?
  - answer: You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: How do I get a temporary license for testing?
  - answer: Visit the Aspose.Zip trial page [here](https://releases.aspose.com/) to
      download the latest version.
    question: Where can I download a free trial of Aspose.Zip?
  - answer: 'The Aspose.Zip community forum is a great place to get assistance: [support
      forum](https://forum.aspose.com/c/zip/37).'
    question: Where can I ask for help if I run into issues?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment extraire un zip vers un dossier avec Aspose.Zip pour .NET
url: /fr/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment extraire un zip vers un dossier avec Aspose.Zip pour .NET

## Introduction

If you need to **extract zip to folder** quickly and reliably in a .NET application, Aspose.Zip for .NET gives you a clean, cross‑platform API that handles plain and encrypted archives alike. In this tutorial we’ll walk through everything you need—from setting up the library to extracting a password‑protected ZIP file—so you can focus on your business logic instead of low‑level archive handling.

## Réponses rapides
- **Quel est le but principal d'Aspose.Zip ?** Créer, lire et **extraire un zip vers un dossier** dans les applications .NET.  
- **Comment extraire un zip avec mot de passe ?** Transmettez le mot de passe via `ArchiveLoadOptions.DecryptionPassword`.  
- **Puis-je décompresser une archive chiffrée sans mot de passe ?** Non — Aspose.Zip nécessite le mot de passe correct pour ouvrir les archives chiffrées.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 et .NET 5–10.  
- **Une licence est‑elle requise pour la production ?** Oui, une licence valide d'Aspose.Zip est nécessaire pour une utilisation commerciale.

## Qu’est‑ce que **extraire un zip vers un dossier** ?

Extraire un fichier ZIP consiste à lire les données compressées et à écrire les fichiers originaux dans un répertoire cible sur le disque. Aspose.Zip abstrait les détails de bas niveau, vous permettant d’appeler une seule méthode pour effectuer l’opération complète tout en prenant en charge **plus de 30 formats d’archive** et en gérant des fichiers jusqu’à **2 GB** sans charger l’ensemble de l’archive en mémoire.

## Pourquoi utiliser Aspose.Zip pour les tâches de **décompression de zip** ?

Aspose.Zip fournit une API simple qui vous permet de décompresser des fichiers en quelques lignes de code seulement, prend en charge les archives protégées par mot de passe et chiffrées AES, et fonctionne sous Windows, Linux et macOS. Il traite **des archives ZIP de 500 pages en moins de 2 seconds** sur un serveur typique, éliminant le besoin d’utilitaires zip natifs et réduisant la complexité du déploiement.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Bibliothèque Aspose.Zip pour .NET : téléchargez et installez la bibliothèque depuis la [documentation Aspose.Zip pour .NET](https://reference.aspose.com/zip/net/).
- Un environnement de développement .NET (Visual Studio, VS Code ou tout IDE de votre choix).
- (Facultatif) Un fichier ZIP protégé par mot de passe si vous souhaitez essayer **extraire un zip avec mot de passe**.

## Importer les espaces de noms

Dans votre projet .NET, importez les espaces de noms nécessaires pour exploiter les fonctionnalités d’Aspose.Zip :

```csharp
using Aspose.Zip;
using System.IO;
```

Décomposons maintenant le processus d'extraction étape par étape.

## Comment **extraire un zip vers un dossier** – Guide étape par étape

Chargez votre archive ZIP, fournissez éventuellement un mot de passe de déchiffrement, et appelez `ExtractToDirectory` — c’est le flux complet d’extraction en trois étapes concises. L’API crée automatiquement le dossier de destination s’il n’existe pas, et elle diffuse les entrées vers le disque pour maintenir une faible utilisation de la mémoire, même pour les archives de plusieurs gigaoctets.

### Étape 1 : Ouvrir le fichier ZIP (ou l'archive chiffrée)

La classe `FileStream` fournit un flux en lecture seule vers le fichier ZIP physique sur le disque. L’utilisation d’un flux permet à Aspose.Zip de travailler avec des fichiers situés sur des partages réseau ou des ressources intégrées sans les copier d’abord dans un emplacement temporaire.

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

### Étape 2 : Créer une instance `Archive` (fournir le mot de passe si nécessaire)

La classe `Archive` est l’objet principal qui représente une archive ZIP en mémoire. `ArchiveLoadOptions` définit les paramètres utilisés lors du chargement d’une archive, comme le mot de passe de déchiffrement. Passer un objet `ArchiveLoadOptions` avec la propriété `DecryptionPassword` active le déchiffrement des entrées chiffrées AES.

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

### Étape 3 : Extraire le contenu vers un dossier de destination

`ExtractToDirectory` parcourt chaque entrée de l’archive et l’écrit dans le chemin cible, en préservant la hiérarchie de dossiers d’origine. La méthode crée automatiquement les dossiers manquants et peut également filtrer les entrées si vous ne avez besoin que d’un sous‑ensemble.

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

> **Astuce :** Si vous n’avez besoin d’extraire qu’un sous‑ensemble de fichiers, utilisez la surcharge qui accepte un délégué de filtre au lieu d’extraire tout.

## Problèmes courants et dépannage

- **Mot de passe incorrect** – Aspose.Zip lève une exception d’authentification. Vérifiez à nouveau la chaîne du mot de passe ou récupérez‑le de manière sécurisée depuis une source de configuration.  
- **Chemin de destination introuvable** – Assurez‑vous que le chemin du répertoire de destination est valide ; `ExtractToDirectory` créera les dossiers manquants, mais le chemin parent doit être accessible.  
- **Archives volumineuses** – Pour des fichiers ZIP très gros, envisagez d’extraire entrée par entrée en utilisant l’API de streaming afin de maintenir une faible utilisation de la mémoire.  

## Questions fréquemment posées

**Q : Aspose.Zip prend‑il en charge d’autres formats de compression comme GZIP ?**  
R : Oui, Aspose.Zip pour .NET prend en charge ZIP, GZIP et plusieurs autres formats courants.

**Q : Puis‑je utiliser Aspose.Zip dans des projets commerciaux et non commerciaux ?**  
R : Absolument. Une licence valide est requise pour la production, mais vous pouvez utiliser l’essai gratuit pour l’évaluation.

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Vous pouvez obtenir une licence temporaire depuis [ici](https://purchase.aspose.com/temporary-license/) à des fins de test.

**Q : Où puis‑je télécharger un essai gratuit d’Aspose.Zip ?**  
R : Consultez la page d’essai d’Aspose.Zip [ici](https://releases.aspose.com/) pour télécharger la dernière version.

**Q : Où puis‑je demander de l’aide en cas de problème ?**  
R : Le forum communautaire d’Aspose.Zip est un excellent endroit pour obtenir de l’aide : [forum de support](https://forum.aspose.com/c/zip/37).

---

**Dernière mise à jour :** 2026-06-04  
**Testé avec :** Aspose.Zip for .NET (latest release)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment extraire un zip avec mot de passe en utilisant Aspose.Zip pour .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [Comment extraire un WIM vers un dossier en utilisant Aspose.Zip pour .NET](/zip/net/file-decompression/decompress-wim-folder/)
- [Comment décompresser des fichiers avec Aspose.Zip pour .NET](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}