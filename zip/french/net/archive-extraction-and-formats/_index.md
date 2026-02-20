---
date: 2026-02-20
description: Apprenez à compresser des fichiers tarbz2, à créer des archives targz
  et à extraire des archives .NET avec extraction de zip protégé par mot de passe
  en utilisant Aspose.Zip pour .NET. Améliorez l’efficacité du stockage et la sécurité.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser des fichiers TarBz2 avec Aspose.Zip pour .NET
url: /fr/net/archive-extraction-and-formats/
weight: 23
---

 shortcode unchanged.

Then "---" line.

Then "**Last Updated:** 2026-02-20" keep same.

"**Tested With:** Aspose.Zip for .NET 24.11" keep same.

"**Author:** Aspose" keep same.

Now produce final content.

Be careful to preserve markdown formatting exactly.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment compresser des fichiers TarBz2 avec Aspose.Zip pour .NET

## Introduction

Dans ce guide, vous apprendrez **comment compresser des fichiers tarbz2** avec Aspose.Zip pour .NET tout en découvrant comment créer des archives TarGz et effectuer l’extraction d’archives .net de fichiers zip protégés par mot de passe. Une gestion efficace des fichiers est une pierre angulaire du développement .NET moderne, et maîtriser ces formats vous permet de réduire les coûts de stockage, d’accélérer le transfert de données et de garder les informations sensibles en sécurité. Que vous construisiez un service de sauvegarde, un client de stockage cloud ou un pipeline de traitement de données, les techniques présentées ici rendront vos tâches de gestion de fichiers plus fluides et plus fiables.

## Réponses rapides
- **Qu’est‑ce que TarBz2 ?** Une archive compressée qui combine l’empaquetage TAR avec la compression BZIP2 pour des ratios de compression élevés.  
- **Pourquoi choisir Aspose.Zip pour .NET ?** Il offre une API unique et fluide pour créer et extraire de nombreux formats d’archive sans dépendances externes.  
- **Puis‑je créer une archive TarGz ?** Oui – Aspose.Zip prend en charge TarGz, TarLz, TarXz, TarZ, et plus encore.  
- **Comment extraire une archive zip protégée par mot de passe ?** Utilisez la propriété `Password` sur l’objet `ArchiveEntry` lors de l’extraction.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible pour l’évaluation.

## Comment compresser des fichiers TarBz2
Compresser des fichiers en TarBz2 signifie d’abord regrouper plusieurs fichiers et répertoires dans un conteneur **TAR** unique, puis appliquer la compression **BZIP2**. Le résultat est un fichier unique `.tar.bz2` à la fois facile à transporter et fortement compressé.

## Pourquoi utiliser Aspose.Zip pour .NET pour gérer ces formats ?
- **API unifiée** – Une bibliothèque, de nombreux formats (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Aucune dépendance native** – Fonctionne sur Windows, Linux et macOS dès le départ.  
- **Support du mot de passe** – Protégez et extrayez les archives en toute sécurité avec des mots de passe par entrée.  
- **Performance‑orientée** – Le traitement basé sur les flux minimise l’empreinte mémoire.

## Prérequis
- .NET 6.0 ou ultérieur (ou .NET Core 3.1+ / .NET Framework 4.5+).  
- Package NuGet Aspose.Zip pour .NET installé (`Install-Package Aspose.Zip`).  
- Connaissances de base en C# et I/O de fichiers.

## Guide étape par étape

### Étape 1 : Choisissez le format d’archive dont vous avez besoin
Déterminez si **TarBz2**, **TarGz**, **TarLz**, **TarXz** ou **TarZ** correspond le mieux à votre ratio de compression et à vos exigences de compatibilité.  
- **TarBz2** – Meilleure compression, traitement plus lent.  
- **TarGz** – Bon compromis entre vitesse et taille (couvre le mot‑clé secondaire *how to create targz*).  
- **TarZ** – Format hérité, utile pour la compatibilité avec d’anciens outils Unix.

### Étape 2 : Créez une nouvelle instance `Archive`
Instanciez la classe `Archive` et indiquez le chemin du fichier de sortie. Cet objet gérera le processus d’empaquetage et de compression.

### Étape 3 : Ajoutez des fichiers et des dossiers
Utilisez les méthodes `AddAll` ou `AddFile` pour inclure les fichiers que vous souhaitez compresser. Vous pouvez préserver la structure des répertoires en ajoutant un dossier de base.

### Étape 4 : Définissez le type de compression souhaité
Spécifiez l’algorithme de compression (`CompressionType.BZip2`, `CompressionType.GZip`, etc.) lors de l’enregistrement de l’archive. C’est ici que vous **compressez réellement les fichiers en TarBz2** ou tout autre format.

### Étape 5 : Enregistrez l’archive
Appelez `Save` avec l’énumération de format appropriée (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, etc.). La bibliothèque écrit le conteneur TAR et applique la compression choisie en une seule passe.

### Étape 6 : Extraction d’archives avec mots de passe
Si vous devez **extraire des entrées d’archive avec des mots de passe différents** (mot‑clé secondaire *password protected zip extraction*), ouvrez l’archive, localisez chaque entrée, attribuez son mot de passe, puis extrayez‑la.

### Étape 7 : Vérifiez le résultat
Après l’extraction, comparez les tailles de fichiers et les sommes de contrôle pour vous assurer que l’archive a été créée et décompressée correctement.

## Cas d’utilisation courants
- **Utilitaires de sauvegarde** – Stockez les sauvegardes quotidiennes au format `.tar.bz2` pour minimiser les coûts de stockage.  
- **Échange de données multiplateforme** – Les formats basés sur Tar sont universellement compris sous Linux, macOS et Windows.  
- **Distribution sécurisée** – Protégez les entrées individuelles avec des mots de passe pour les environnements soumis à des exigences de conformité.

## Dépannage & Conseils
- **Grandes archives** – Utilisez les API de flux (`Archive.CreateEntryFromFile`) pour éviter de charger des fichiers entiers en mémoire.  
- **Mots de passe non correspondants** – Assurez‑vous que le mot de passe défini sur chaque `ArchiveEntry` correspond à celui utilisé lors de l’extraction ; sinon, vous rencontrerez `InvalidPasswordException`.  
- **Niveau de compression non pris en charge** – BZIP2 ne supporte pas de niveaux de compression personnalisés ; si vous avez besoin d’un contrôle plus fin, envisagez TarLz ou TarXz.

## FAQ

**Q : Comment créer une archive TarGz ?**  
R : Définissez le type de compression sur `CompressionType.GZip` et le format sur `ArchiveFormat.TarGz` lors de l’appel à `Save`.

**Q : Puis‑je extraire une archive protégée par mot de passe sans connaître le mot de passe ?**  
R : Non. Chaque entrée doit recevoir le mot de passe correct ; sinon l’extraction échouera.

**Q : Aspose.Zip prend‑il en charge l’extraction d’archives avec des mots de passe différents par entrée ?**  
R : Oui. Vous pouvez attribuer un mot de passe à chaque `ArchiveEntry` individuellement avant l’extraction.

**Q : Quel format offre la meilleure compression ?**  
R : TarBz2 fournit généralement le meilleur ratio de compression, suivi de TarLz et TarXz. TarGz offre un bon équilibre vitesse‑taille.

**Q : Existe‑t‑il une limite au nombre de fichiers que je peux ajouter à une archive TAR ?**  
R : Pratiquement aucune, mais les archives extrêmement volumineuses peuvent bénéficier d’une division en plusieurs parties pour faciliter leur gestion.

## Tutoriels d’extraction d’archives et de formats
### [Compression de fichiers en TarBz2 avec Aspose.Zip pour .NET](./compress-to-tar-bz2/)
Apprenez à compresser des fichiers au format TarBz2 en .NET avec Aspose.Zip. Suivez notre guide étape par étape pour une compression efficace des fichiers.  
### [Compression en TarGz avec Aspose.Zip pour .NET](./compress-to-tar-gz/)
Découvrez la compression efficace de fichiers en .NET avec Aspose.Zip. Compressez en TarGz sans effort.  
### [Compression en TarLz avec Aspose.Zip pour .NET](./compress-to-tar-lz/)
Compressez facilement des fichiers en .NET avec Aspose.Zip. Apprenez à créer des archives TarLz étape par étape.  
### [Compression en TarXz avec Aspose.Zip pour .NET](./compress-to-tar-xz/)
Apprenez à compresser des fichiers au format TarXz en .NET avec Aspose.Zip. Suivez notre guide pas à pas pour un stockage et une transmission de fichiers efficaces.  
### [Compression en TarZ avec Aspose.Zip pour .NET](./compress-to-tar-z/)
Explorez la compression étape par étape en TarZ avec Aspose.Zip pour .NET. Gestion de fichiers efficace pour vos projets .NET.  
### [Extraction d’entrées d’archive avec des mots de passe différents dans Aspose.Zip pour .NET](./extract-archive-different-passwords/)
Apprenez à extraire des entrées d’archive avec des mots de passe différents dans Aspose.Zip pour .NET. Renforcez la sécurité et la flexibilité de vos applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose