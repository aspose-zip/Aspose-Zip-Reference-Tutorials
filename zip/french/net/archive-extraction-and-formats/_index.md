---
date: 2026-06-19
description: Apprenez à compresser des fichiers tar, créer des archives targz et extraire
  des fichiers zip protégés par mot de passe en utilisant Aspose.Zip pour .NET – améliorant
  l'efficacité du stockage et la sécurité.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Extraction d'archives et formats
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser des fichiers Tar avec Aspose.Zip pour .NET
url: /fr/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment compresser des fichiers Tar avec Aspose.Zip pour .NET

## Introduction

Dans ce guide, vous découvrirez **comment compresser des fichiers tar** à l'aide d'Aspose.Zip pour .NET, apprendrez à créer des archives TarGz et verrez comment extraire des archives zip protégées par mot de passe. La gestion efficace des archives est une compétence essentielle pour les développeurs .NET modernes — que vous construisiez un service de sauvegarde, un client de stockage cloud ou un pipeline de traitement de données, maîtriser ces formats réduit les coûts de stockage, accélère les transferts et protège les données sensibles.

## Réponses rapides
- **Qu'est-ce que TarBz2 ?** Une archive compressée qui combine l'empaquetage TAR avec la compression BZIP2 pour des ratios de compression élevés.  
- **Pourquoi choisir Aspose.Zip pour .NET ?** Il offre une API unique et fluide pour créer et extraire de nombreux formats d'archive sans dépendances externes.  
- **Puis-je créer une archive TarGz ?** Oui – Aspose.Zip prend en charge TarGz, TarLz, TarXz, TarZ, et plus encore.  
- **Comment extraire une archive zip protégée par mot de passe ?** Utilisez la propriété `Password` de l'objet `ArchiveEntry` lors de l'extraction.  
- **Ai-je besoin d'une licence pour une utilisation en production ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible pour l'évaluation.

## Qu'est-ce que la compression Tar ?
Tar (Tape Archive) est un format conteneur qui regroupe plusieurs fichiers et répertoires en un seul flux sans compression. Lorsque vous appliquez un algorithme de compression tel que BZIP2, GZip, LZMA ou XZ, le résultat est une **archive basée sur tar** comme `.tar.bz2`, `.tar.gz`, `.tar.lz`, etc. Ces formats sont largement pris en charge sous Linux, macOS et Windows, ce qui les rend idéaux pour l'échange de données multiplateforme.

## Pourquoi utiliser Aspose.Zip pour .NET pour gérer ces formats ?
Aspose.Zip fournit une **API unifiée, sans dépendances** qui prend en charge plus de 50 formats d'archive et de compression, y compris TarBz2, TarGz, TarLz, TarXz et TarZ. Elle fonctionne sous Windows, Linux et macOS, et son architecture basée sur les flux maintient l'utilisation de la mémoire en dessous de 10 Mo même pour des archives de plusieurs centaines de mégaoctets. La protection par mot de passe est intégrée, permettant le chiffrement par entrée sans bibliothèques supplémentaires.

## Prérequis
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, ou .NET 5–10.  
- Package NuGet Aspose.Zip pour .NET installé (`Install-Package Aspose.Zip`).  
- Familiarité de base avec la gestion de fichiers C# et le système de projets .NET.

## Guide étape par étape

### Comment compresser des fichiers Tar – Réponse directe
`Archive` représente un fichier d'archive et fournit des méthodes pour ajouter des entrées et l'enregistrer.  
Créez une instance `Archive`, ajoutez les fichiers que vous souhaitez regrouper, définissez `CompressionType.BZip2` et appelez `Save` avec `ArchiveFormat.TarBz2`. La bibliothèque écrit le conteneur TAR et le compresse en un seul passage en flux, de sorte que vous ne chargez jamais l'intégralité de l'archive en mémoire.

### Étape 1 : Choisissez le format d'archive dont vous avez besoin
Déterminez quel format basé sur tar correspond le mieux à votre compromis compression‑vitesse :

- **TarBz2** – Ratio de compression le plus élevé (≈30 % plus petit que TarGz) mais plus lent.  
- **TarGz** – Bon équilibre entre vitesse et taille ; idéal pour la plupart des scénarios de stockage cloud.  
- **TarLz / TarXz** – Compression très élevée avec une vitesse modérée, utile pour le stockage d'archives.  
- **TarZ** – Format hérité pour la compatibilité avec les anciens outils Unix.

### Étape 2 : Créez une nouvelle instance `Archive`
`Archive` est l'objet de niveau supérieur qui représente un seul fichier d'archive en mémoire.  

La classe `Archive` gère le flux de travail d'empaquetage et de compression, exposant des méthodes pour ajouter des entrées et écrire le fichier final.

### Étape 3 : Ajoutez des fichiers et des dossiers
Vous pouvez ajouter un arbre de répertoires complet avec `AddAll` ou ajouter des fichiers individuels avec `AddFile`. Préserver la hiérarchie de dossiers d'origine est aussi simple que de fournir le chemin du répertoire de base.

### Étape 4 : Définissez le type de compression souhaité
`CompressionType` énumère les algorithmes pris en charge.  

`CompressionType` définit l'algorithme (BZip2, GZip, LZMA, XZ, etc.) qui sera appliqué au flux TAR lors de l'enregistrement.

### Étape 5 : Enregistrez l'archive
`ArchiveFormat` est un ensemble d'énumérations (par ex., `TarBz2`, `TarGz`) qui indique au writer quel conteneur et quelle compression utiliser.  

Appeler `Save` écrit l'archive sur le disque en utilisant le format sélectionné.

### Étape 6 : Extraction d'archives avec mots de passe
`ArchiveEntry` représente une entrée de fichier ou de répertoire unique à l'intérieur d'une archive.  

Pour extraire un zip protégé par mot de passe, ouvrez l'archive, localisez chaque `ArchiveEntry`, attribuez sa propriété `Password`, puis appelez `Extract`. Ce modèle de mot de passe par entrée vous permet de protéger des fichiers individuels à l'intérieur d'un même zip.

### Étape 7 : Vérifiez le résultat
Après l'extraction, comparez les tailles de fichiers et les sommes de contrôle SHA‑256 pour confirmer que le cycle complet de l'archive a préservé l'intégrité des données.

## Cas d'utilisation courants
- **Utilitaires de sauvegarde** – Stockez les sauvegardes quotidiennes au format `.tar.bz2` pour réduire les coûts de stockage jusqu'à 30 %.  
- **Échange de données multiplateforme** – Les formats basés sur Tar sont compris nativement par les outils Linux, macOS et Windows.  
- **Distribution sécurisée** – Attribuez des mots de passe aux entrées sensibles, répondant aux exigences de conformité sans outils de chiffrement supplémentaires.

## Dépannage et astuces
- **Grandes archives** – Privilégiez l'API de streaming (`Archive.CreateEntryFromFile`) pour maintenir une faible utilisation de la mémoire.  
- **Mots de passe non correspondants** – Le mot de passe défini sur chaque `ArchiveEntry` doit correspondre exactement ; sinon une `InvalidPasswordException` est levée.  
- **Niveau de compression** – BZIP2 n'expose pas de niveaux personnalisés ; si vous avez besoin d'un contrôle plus fin, passez à LZMA (`CompressionType.LZMA`) ou XZ (`CompressionType.XZ`).  

## Questions fréquentes

**Q : Comment créer une archive TarGz ?**  
R : Définissez `CompressionType.GZip` et utilisez `ArchiveFormat.TarGz` lors de l'appel à `Save`. Cela produit un fichier `.tar.gz` en une seule étape.

**Q : Puis-je extraire une archive protégée par mot de passe sans connaître le mot de passe ?**  
R : Non. Chaque entrée doit être fournie avec le mot de passe correct ; sinon l'extraction échoue avec une `InvalidPasswordException`.

**Q : Aspose.Zip prend‑il en charge l'extraction d'archives avec des mots de passe différents par entrée ?**  
R : Oui. Attribuez un mot de passe à chaque `ArchiveEntry` individuellement avant d'appeler `Extract`.

**Q : Quel format offre la meilleure compression ?**  
R : TarBz2 donne généralement la taille la plus petite, suivi de TarLz et TarXz. TarGz offre une alternative plus rapide tout en restant efficace.

**Q : Existe‑t‑il une limite au nombre de fichiers que je peux ajouter à une archive TAR ?**  
R : Pratiquement aucune, mais les archives extrêmement volumineuses (>10 GB) peuvent bénéficier d'une division en plusieurs parties pour faciliter la gestion.

## Tutoriels d'extraction d'archives et de formats
### [Compression de fichiers en TarBz2 avec Aspose.Zip pour .NET](./compress-to-tar-bz2/)
Apprenez à compresser des fichiers au format TarBz2 en .NET avec Aspose.Zip. Suivez notre guide étape par étape pour une compression efficace des fichiers.  
### [Compression en TarGz avec Aspose.Zip pour .NET](./compress-to-tar-gz/)
Explorez la compression de fichiers efficace en .NET avec Aspose.Zip. Compressez en TarGz sans effort.  
### [Compression en TarLz avec Aspose.Zip pour .NET](./compress-to-tar-lz/)
Compressez des fichiers en .NET avec Aspose.Zip sans effort. Apprenez à créer des archives TarLz étape par étape.  
### [Compression en TarXz avec Aspose.Zip pour .NET](./compress-to-tar-xz/)
Apprenez à compresser des fichiers au format TarXz en .NET avec Aspose.Zip. Suivez notre guide pour un stockage et une transmission efficaces.  
### [Compression en TarZ avec Aspose.Zip pour .NET](./compress-to-tar-z/)
Explorez la compression étape par étape en TarZ avec Aspose.Zip pour .NET. Gestion efficace des fichiers pour vos projets .NET.  
### [Extraction d'entrées d'archive avec différents mots de passe dans Aspose.Zip pour .NET](./extract-archive-different-passwords/)
Apprenez à extraire des entrées d'archive avec différents mots de passe dans Aspose.Zip pour .NET. Renforcez la sécurité et la flexibilité de vos applications.

---

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## Tutoriels associés

- [Créer une archive tar et ajouter des fichiers au tar avec Aspose.Zip pour .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Comment compresser tar et créer TarBz2 avec Aspose.Zip pour .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Ajouter des fichiers au tar et créer une archive tarxz avec Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}