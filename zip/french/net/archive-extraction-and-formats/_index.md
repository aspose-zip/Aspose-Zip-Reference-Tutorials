---
date: 2026-10-25
description: Apprenez comment extraire le mot de passe zip et définir l'algorithme
  de compression lors de la compression de fichiers tar avec Aspose.Zip pour .NET,
  améliorant l'efficacité du stockage et la sécurité.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Extraction d'archives et formats
og_description: Apprenez comment extraire le mot de passe zip et définir l'algorithme
  de compression lors de la compression de fichiers tar avec Aspose.Zip pour .NET,
  améliorant l'efficacité du stockage et la sécurité.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Extraire le mot de passe zip et compresser des fichiers tar avec Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Extraire le mot de passe zip et compresser des fichiers tar avec Aspose.Zip
url: /fr/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraire le mot de passe zip et compresser les fichiers tar avec Aspose.Zip

## Introduction

Dans ce guide, vous découvrirez les techniques **extract zip password**, apprendrez comment définir l'algorithme de compression lors de la création d'archives basées sur tar, et verrez comment créer TarGz, TarBz2 et d’autres formats avec Aspose.Zip pour .NET. Que vous développiez un service de sauvegarde, un client de stockage cloud ou un pipeline de traitement de données, maîtriser ces opérations réduit les coûts de stockage, accélère les transferts et sécurise les fichiers sensibles.

## Réponses rapides
- **Qu’est‑ce que TarBz2 ?** Une archive compressée qui combine l'empaquetage TAR avec la compression BZIP2 pour des taux de compression élevés.  
- **Pourquoi choisir Aspose.Zip pour .NET ?** Il prend en charge plus de 50 formats d'archives et de compression, fonctionne sous Windows, Linux et macOS, et maintient l'utilisation de la mémoire en dessous de 10 Mo pour des archives de plusieurs centaines de mégaoctets.  
- **Puis‑je créer une archive TarGz ?** Oui – Aspose.Zip propose TarGz, TarLz, TarXz, TarZ, et plus encore.  
- **Comment extraire une archive zip protégée par mot de passe ?** Définissez la propriété `Password` sur chaque `ArchiveEntry` avant d’appeler `Extract`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible pour l’évaluation.

## Qu’est‑ce que la compression tar ?

La compression tar combine le conteneur TAR avec un algorithme de compression tel que BZIP2, GZIP, LZMA ou XZ. Le résultat est un fichier unique (par ex., `.tar.gz`, `.tar.bz2`) qui peut être décompressé sous Linux, macOS et Windows. Elle préserve la hiérarchie de répertoires d'origine, permet une extraction en accès aléatoire, et est largement prise en charge par les outils en ligne de commande et les bibliothèques de programmation, ce qui la rend idéale pour la distribution multiplateforme et le stockage d'archives.

## Pourquoi utiliser Aspose.Zip pour .NET pour gérer ces formats ?

Aspose.Zip fournit une API unifiée, sans dépendances, qui prend en charge **50+** formats d'archives et de compression, y compris tous les principaux types basés sur tar. Son architecture de streaming traite des archives de plus de 10 Go tout en maintenant l'utilisation de la RAM en dessous de 10 Mo, ce qui la rend idéale pour les charges de travail serveur à haut débit.

**Réponse directe :** Vous utilisez Aspose.Zip car il vous permet de créer, compresser et extraire des archives basées sur tar et des fichiers zip protégés par mot de passe avec une API fluide unique, sans outils externes, tout en gérant des archives multi‑gigaoctets de manière efficace en mémoire grâce au streaming.

## Prérequis
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, ou .NET 5–10.  
- Package NuGet Aspose.Zip pour .NET (`Install-Package Aspose.Zip`).  
- Familiarité de base avec les entrées/sorties de fichiers C# et le système de projets .NET.

## Guide étape par étape

### Comment compresser les fichiers tar – réponse directe
Créez une instance `Archive`, ajoutez les fichiers que vous souhaitez regrouper, définissez `CompressionType.BZip2` (ou un autre algorithme), et appelez `Save` avec `ArchiveFormat.TarBz2`. La bibliothèque écrit le conteneur TAR et le compresse en un seul passage en streaming, de sorte que vous ne chargez jamais l'archive entière en mémoire.

### Étape 1 : Choisissez le format d'archive dont vous avez besoin
Décidez quel format basé sur tar correspond le mieux à votre compromis compression‑vitesse :

- **TarBz2** – Ratio de compression le plus élevé (≈30 % plus petit que TarGz) mais plus lent.  
- **TarGz** – Bon équilibre entre vitesse et taille ; idéal pour la plupart des scénarios de stockage cloud.  
- **TarLz / TarXz** – Compression très élevée avec une vitesse modérée, utile pour le stockage d'archives.  
- **TarZ** – Format hérité pour la compatibilité avec les anciens outils Unix.

### Étape 2 : Créez une nouvelle instance `Archive`
`Archive` représente un fichier d'archive unique et fournit des méthodes pour ajouter des entrées et enregistrer l'archive.

La classe `Archive` gère le flux d'empaquetage et de compression, exposant des méthodes pour ajouter des entrées et écrire le fichier final.

### Étape 3 : Ajoutez des fichiers et des dossiers
Vous pouvez ajouter un arbre de répertoires complet avec `AddAll` ou ajouter des fichiers individuels avec `AddFile`.

`AddAll` ajoute un arbre de répertoires complet à l'archive, en préservant sa structure.

`AddFile` ajoute un fichier unique à l'archive. Préserver la hiérarchie de dossiers d'origine est aussi simple que de fournir le chemin du répertoire de base.

### Étape 4 : Définissez le type de compression souhaité
L'énumération `CompressionType` spécifie l'algorithme de compression appliqué au flux TAR.

`CompressionType` énumère les algorithmes pris en charge (BZip2, GZip, LZMA, XZ, etc.) qui seront appliqués lors de l'enregistrement.

### Étape 5 : Enregistrez l'archive
L'énumération `ArchiveFormat` sélectionne la combinaison conteneur et compression pour le fichier de sortie.

Appeler `Save` écrit l'archive sur le disque en utilisant le format sélectionné.

### Étape 6 : Extraction d'archives avec mots de passe
`ArchiveEntry` représente une entrée de fichier ou de répertoire unique à l'intérieur d'une archive.

Pour extraire un zip protégé par mot de passe, ouvrez l'archive, localisez chaque `ArchiveEntry`, attribuez sa propriété `Password`, puis appelez `Extract`. La propriété `Password` définit le mot de passe de déchiffrement pour une entrée zip. Ce modèle de mot de passe par entrée vous permet de protéger des fichiers individuels à l'intérieur d'un même zip.

### Étape 7 : Vérifiez le résultat
Après l'extraction, comparez les tailles de fichiers et les sommes de contrôle SHA‑256 pour confirmer que le cycle complet de l'archive a préservé l'intégrité des données.

## Cas d'utilisation courants
- **Backup utilities** – Stockez les sauvegardes quotidiennes au format `.tar.bz2` pour réduire les coûts de stockage jusqu'à 30 %.  
- **Cross‑platform data exchange** – Les formats basés sur tar sont compris nativement par les outils Linux, macOS et Windows.  
- **Secure distribution** – Attribuez des mots de passe aux entrées sensibles, répondant aux exigences de conformité sans outils de chiffrement supplémentaires.

## Dépannage et astuces
- **Large archives** – Utilisez l'API de streaming (`Archive.CreateEntryFromFile`) pour maintenir une faible utilisation de la mémoire.  
- **Password mismatches** – Le mot de passe défini sur chaque `ArchiveEntry` doit correspondre exactement ; sinon une `InvalidPasswordException` est levée.  
- **Compression level** – BZIP2 n'expose pas de niveaux personnalisés ; si vous avez besoin d'un contrôle plus fin, passez à LZMA (`CompressionType.LZMA`) ou XZ (`CompressionType.XZ`).  

## Questions fréquentes

**Q : Comment créer une archive TarGz ?**  
A : Définissez `CompressionType.GZip` et utilisez `ArchiveFormat.TarGz` lors de l'appel à `Save`. Cela produit un fichier `.tar.gz` en une seule étape.

**Q : Puis‑je extraire une archive protégée par mot de passe sans connaître le mot de passe ?**  
A : Non. Chaque entrée doit être fournie avec le mot de passe correct ; sinon l'extraction échoue avec une `InvalidPasswordException`.

**Q : Aspose.Zip prend‑il en charge l'extraction d'archives avec des mots de passe différents par entrée ?**  
A : Oui. Attribuez un mot de passe à chaque `ArchiveEntry` individuellement avant d'appeler `Extract`.

**Q : Quel format offre la meilleure compression ?**  
A : TarBz2 donne généralement la taille la plus petite, suivi de TarLz et TarXz. TarGz offre une alternative plus rapide tout en restant efficace.

**Q : Existe‑t‑il une limite au nombre de fichiers que je peux ajouter à une archive TAR ?**  
A : Pratiquement aucune, mais les archives extrêmement volumineuses (>10 GB) peuvent bénéficier d'une division en plusieurs parties pour faciliter la manipulation.

## Tutoriels d'extraction d'archives et de formats

### [Compression de fichiers en TarBz2 avec Aspose.Zip pour .NET](./compress-to-tar-bz2/)
Apprenez à compresser des fichiers au format TarBz2 en .NET avec Aspose.Zip. Suivez notre guide étape par étape pour une compression de fichiers efficace.

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

## Tutoriels associés

- [Créer une archive tar et ajouter des fichiers à tar avec Aspose.Zip pour .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Comment compresser tar et créer TarBz2 avec Aspose.Zip pour .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Ajouter des fichiers à tar et créer une archive tarxz avec Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Dernière mise à jour :** 2026-10-25  
**Testé avec :** Aspose.Zip for .NET 24.11  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}