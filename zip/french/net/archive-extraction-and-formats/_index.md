---
date: 2026-01-28
description: Apprenez à extraire une archive avec mot de passe, à compresser des fichiers
  en TarBz2, à créer des archives TarGz en utilisant Aspose.Zip pour .NET. Augmentez
  l’efficacité du stockage et la sécurité.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Extraire une archive avec mot de passe et compresser en TarBz2 (.NET)
url: /fr/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraire une archive avec mot de passe et compresser en TarBz2 (.NET)

Dans ce guide, vous découvrirez **comment extraire une archive avec mot de passe** et maîtriserez également **la compression de fichiers en TarBz2** à l’aide d’Aspose.Zip pour .NET. Que vous construisiez un service de sauvegarde, un client de stockage cloud ou un pipeline de traitement de données, ces techniques vous permettent de réduire l’empreinte de stockage, d’accélérer les transferts et de protéger les données sensibles.

## Réponses rapides
- **Qu’est‑ce que le TarBz2 ?** Une archive compressée qui combine l’empaquetage TAR avec la compression BZIP2 pour des ratios de compression élevés.  
- **Pourquoi choisir Aspose.Zip pour .NET ?** Il offre une API unique et fluide pour de nombreux formats d’archive sans dépendances natives.  
- **Puis‑je créer une archive TarGz ?** Oui – Aspose.Zip prend en charge TarGz, TarLz, TarXz, TarZ, et plus encore.  
- **Comment extraire une archive protégée par mot de passe ?** Définissez la propriété `Password` sur chaque `ArchiveEntry` avant l’extraction.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible pour l’évaluation.

## Comment extraire une archive avec mot de passe en utilisant Aspose.Zip pour .NET
Extraire une archive **protégée par mot de passe** est simple. Vous ouvrez l’archive, localisez l’entrée souhaitée, attribuez son mot de passe, puis appelez `Extract`. Cette approche fonctionne pour TarBz2, TarGz et les autres formats pris en charge.

## Que signifie réellement « compresser des fichiers en TarBz2 » ?
Compresser des fichiers en TarBz2 consiste d’abord à regrouper plusieurs fichiers et répertoires dans un seul conteneur **TAR**, puis à appliquer la compression **BZIP2**. Le résultat est un fichier `.tar.bz2` à la fois facile à transporter et fortement compressé.

## Pourquoi utiliser Aspose.Zip pour .NET pour gérer ces formats ?
- **API unifiée** – Une bibliothèque, de nombreux formats (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Aucune dépendance native** – Fonctionne sur Windows, Linux et macOS dès l’installation.  
- **Support du mot de passe** – Protégez et extrayez les archives de façon sécurisée avec des mots de passe par entrée.  
- **Optimisé pour la performance** – Le traitement basé sur les flux minimise l’utilisation de la mémoire.

## Prérequis
- .NET 6.0 ou ultérieur (ou .NET Core 3.1+ / .NET Framework 4.5+).  
- Le package NuGet Aspose.Zip pour .NET installé (`Install-Package Aspose.Zip`).  
- Connaissances de base en C# et en I/O de fichiers.

## Guide étape par étape

### Étape 1 : Choisissez le format d’archive dont vous avez besoin
Déterminez si **TarBz2**, **TarGz**, **TarLz**, **TarXz** ou **TarZ** correspond le mieux à votre ratio de compression et à vos exigences de compatibilité.  
- **TarBz2** – Meilleure compression, traitement plus lent.  
- **TarGz** – Bon équilibre entre vitesse et taille (couvre le mot‑clé secondaire *compress files to targz*).  
- **TarZ** – Format hérité pour les anciens outils Unix.

### Étape 2 : Créez une nouvelle instance `Archive`
Instanciez la classe `Archive` et indiquez le chemin du fichier de sortie. Cet objet gérera le processus d’empaquetage et de compression.

### Étape 3 : Ajoutez des fichiers et dossiers
Utilisez les méthodes `AddAll` ou `AddFile` pour inclure les fichiers à compresser. Conservez la structure des répertoires en ajoutant un dossier de base.

### Étape 4 : Définissez le type de compression souhaité
Spécifiez l’algorithme de compression (`CompressionType.BZip2`, `CompressionType.GZip`, etc.) lors de la sauvegarde de l’archive. C’est ici que vous **compressez réellement les fichiers en tarbz2** ou tout autre format.

### Étape 5 : Enregistrez l’archive
Appelez `Save` avec l’énumération de format appropriée (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, etc.). La bibliothèque écrit le conteneur TAR et applique la compression choisie en une seule passe.

### Étape 6 : Extrayez les archives avec mots de passe
Si vous devez **extraire des entrées d’archive avec différents mots de passe** (mot‑clé secondaire *how to extract password protected archive*), ouvrez l’archive, localisez chaque entrée, attribuez son mot de passe, puis extrayez.

### Étape 7 : Vérifiez le résultat
Après l’extraction, comparez les tailles de fichiers et les sommes de contrôle pour vous assurer que l’archive a été créée et décompressée correctement.

## Cas d’utilisation courants
- **Utilitaires de sauvegarde** – Stockez les sauvegardes quotidiennes au format `.tar.bz2` pour réduire les coûts de stockage.  
- **Échange de données multiplateforme** – Les formats basés sur TAR sont universellement compris sous Linux, macOS et Windows.  
- **Distribution sécurisée** – Protégez les entrées individuelles avec des mots de passe pour les environnements soumis à des exigences de conformité.

## Dépannage et astuces
- **Grandes archives** – Utilisez les API de streaming (`Archive.CreateEntryFromFile`) pour éviter de charger des fichiers entiers en mémoire.  
- **Mots de passe non concordants** – Assurez‑vous que le mot de passe défini sur chaque `ArchiveEntry` correspond à celui utilisé lors de l’extraction ; sinon vous rencontrerez `InvalidPasswordException`.  
- **Niveau de compression non pris en charge** – BZIP2 ne supporte pas de niveaux de compression personnalisés ; si vous avez besoin d’un contrôle plus fin, envisagez TarLz ou TarXz.  
- **Astuce de performance** – Lors de la création d’un **archive tarbz2**, activez le tamponnage sur le flux sous‑jacent pour améliorer la vitesse d’écriture.

## Foire aux questions

**Q : Comment créer une archive TarGz ?**  
R : Définissez le type de compression sur `CompressionType.GZip` et le format sur `ArchiveFormat.TarGz` lors de l’appel à `Save`.

**Q : Puis‑je extraire une archive protégée par mot de passe sans connaître le mot de passe ?**  
R : Non. Chaque entrée doit recevoir le mot de passe correct ; sinon l’extraction échouera.

**Q : Aspose.Zip prend‑il en charge l’extraction d’archives avec des mots de passe différents par entrée ?**  
R : Oui. Vous pouvez attribuer un mot de passe à chaque `ArchiveEntry` individuellement avant l’extraction.

**Q : Quel format offre la meilleure compression ?**  
R : TarBz2 fournit généralement le meilleur ratio de compression, suivi de TarLz et TarXz. TarGz offre un bon compromis vitesse‑taille.

**Q : Existe‑t‑il une limite au nombre de fichiers que je peux ajouter à une archive TAR ?**  
R : Pratiquement aucune, mais les archives extrêmement volumineuses peuvent bénéficier d’une division en plusieurs parties pour faciliter leur gestion.

## Tutoriels d’extraction d’archives et de formats
### [Compression de fichiers en TarBz2 avec Aspose.Zip pour .NET](./compress-to-tar-bz2/)
Apprenez à compresser des fichiers au format TarBz2 en .NET avec Aspose.Zip. Suivez notre guide étape par étape pour une compression efficace.
### [Compression en TarGz avec Aspose.Zip pour .NET](./compress-to-tar-gz/)
Découvrez la compression de fichiers en .NET avec Aspose.Zip. Compressez en TarGz sans effort.
### [Compression en TarLz avec Aspose.Zip pour .NET](./compress-to-tar-lz/)
Compressez facilement des fichiers en .NET avec Aspose.Zip. Apprenez à créer des archives TarLz étape par étape.
### [Compression en TarXz avec Aspose.Zip pour .NET](./compress-to-tar-xz/)
Apprenez à compresser des fichiers au format TarXz en .NET avec Aspose.Zip. Suivez notre guide détaillé pour un stockage et une transmission efficaces.
### [Compression en TarZ avec Aspose.Zip pour .NET](./compress-to-tar-z/)
Explorez la compression étape par étape en TarZ avec Aspose.Zip pour .NET. Gestion efficace des fichiers pour vos projets .NET.
### [Extraction d’entrées d’archive avec différents mots de passe dans Aspose.Zip pour .NET](./extract-archive-different-passwords/)
Apprenez à extraire des entrées d’archive avec différents mots de passe dans Aspose.Zip pour .NET. Renforcez la sécurité et la flexibilité de vos applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-28  
**Testé avec :** Aspose.Zip pour .NET 24.11  
**Auteur :** Aspose  

---