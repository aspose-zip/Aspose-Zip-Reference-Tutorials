---
date: 2026-06-29
description: Apprenez à compresser un dossier en 7z avec Aspose.Zip for .NET, couvrant
  les méthodes de compression Seven Zip telles que LZMA2, BZip2 et Store. Parfait
  pour créer des archives 7z de façon programmatique.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip avec diverses méthodes de compression
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser un dossier en 7z – Tutoriel Aspose.Zip for .NET
url: /fr/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment compresser un dossier en 7z – Tutoriel Aspose.Zip pour .NET

## Introduction

Si vous devez **compresser un dossier en 7z** de façon programmatique dans une application .NET, vous êtes au bon endroit. Aspose.Zip pour .NET simplifie la génération d’archives Seven Zip avec n’importe lequel des algorithmes de compression pris en charge, que vous souhaitiez regrouper un répertoire complet pour la distribution ou simplement disposer d’une solution fiable de **seven zip archive .net**. Dans ce guide, nous parcourrons trois méthodes de compression populaires — LZMA2, BZip2 et Store (sans compression) — et vous montrerons exactement comment produire un fichier 7z en quelques lignes de code C#.

## Réponses rapides
- **Quelle bibliothèque devrais-je utiliser ?** Aspose.Zip pour .NET fournit l’ensemble le plus complet de fonctionnalités Seven Zip.  
- **Quelle méthode de compression offre le meilleur taux ?** LZMA2 offre généralement la compression la plus élevée pour des données mixtes.  
- **Puis-je créer un 7z sans aucune compression ?** Oui—utilisez la méthode Store (sans compression).  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit est disponible ; une licence est requise pour une utilisation en production.  
- **Cette solution est‑elle compatible avec .NET 6/7 ?** Absolument—Aspose.Zip prend en charge .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 et .NET 5–10.

## Quelles sont les méthodes de compression Seven Zip ?

Seven Zip prend en charge plusieurs algorithmes, chacun optimisé pour différents scénarios. **LZMA2** offre le taux de compression le plus élevé (souvent 30‑40 % plus petit que BZip2), **BZip2** fournit une compression solide avec une prise en charge plus large des outils hérités, et **Store** archive simplement les fichiers sans les réduire, en conservant parfaitement les horodatages d’origine.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Connaissances de base en C# et Visual Studio.  
- La bibliothèque Aspose.Zip pour .NET installée. Téléchargez‑la depuis la page officielle **[ici](https://releases.aspose.com/zip/net/)**.  
- Un dossier (`dataDir`) contenant les fichiers que vous souhaitez archiver.

## Importer les espaces de noms

Tout d’abord, ajoutez les espaces de noms requis à votre fichier C# :

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Ces classes vous donnent accès aux paramètres de compression et à la gestion des archives.

## Compression LZMA2 – Comment créer un 7z avec le meilleur taux

La classe `Archive` représente une archive 7z pouvant contenir plusieurs fichiers.  
L’algorithme LZMA2 fournit le taux de compression le plus élevé parmi les méthodes prises en charge. Il fonctionne en divisant l’entrée en blocs et en appliquant une compression dictionnaire sophistiquée. Dans Aspose.Zip, vous définissez `CompressionMethod` sur `CompressionMethod.Lzma2` sur l’objet `Archive` avant d’ajouter les fichiers.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Astuce :** LZMA2 fonctionne mieux lorsque les fichiers source dépassent 1 Mo. Pour de nombreux petits fichiers, BZip2 peut être plus rapide.

## Compression BZip2 – Un choix équilibré

La classe `Archive` représente une archive 7z pouvant contenir plusieurs fichiers.  
BZip2 offre une compression solide avec une bonne compatibilité pour les anciens outils. Il utilise la transformation Burrows‑Wheeler et le codage Huffman pour réduire la taille. Dans Aspose.Zip, vous sélectionnez `CompressionMethod.BZip2` lors de la configuration de l’instance `Archive`, ce qui équilibre vitesse et taux de compression pour la plupart des fichiers texte et binaires.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 offre une compression solide tout en maintenant une vitesse raisonnable, ce qui en fait une bonne alternative lorsque LZMA2 n’est pas pris en charge par l’environnement cible.

## Stockage (sans compression) – Quand la taille n’a pas d’importance

La classe `Archive` représente une archive 7z pouvant contenir plusieurs fichiers.  
La méthode Store crée une archive sans compresser les données. Elle copie simplement les fichiers originaux dans le conteneur 7z, en préservant les horodatages et la structure des répertoires. Pour l’utiliser dans Aspose.Zip, définissez `CompressionMethod.Store` sur l’`Archive` avant d’ajouter les fichiers que vous souhaitez regrouper.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Utilisez la méthode Store si vous avez simplement besoin de regrouper des fichiers sans modifier leur taille—parfait pour conserver les horodatages d’origine ou lorsque l’archive sera décompressée à la volée.

## Comment ajouter des fichiers à un 7z ?

Ajoutez des fichiers à une archive 7z en créant une instance `Archive`, en définissant la `CompressionMethod` souhaitée, puis en appelant `AddAllFiles(dataDir)`. La méthode parcourt le dossier spécifié de façon récursive, en préservant la hiérarchie des répertoires à l’intérieur de l’archive. Cette approche vous permet de **compresser un dossier en 7z** avec une seule ligne de code après la configuration initiale.

## Cas d’utilisation courants

| Scénario | Méthode recommandée |
|----------|----------------------|
| Distribuer de grands installateurs | LZMA2 |
| Partager des journaux avec des outils anciens | BZip2 |
| Regrouper des fichiers pour une extraction rapide | Store (sans compression) |
| Besoin de **compresser un dossier en 7z** à la volée dans un service web | LZMA2 (pour le meilleur taux) |

## Dépannage et astuces

- **Fichiers manquants dans l’archive ?** Vérifiez que `dataDir` pointe vers le bon répertoire et que le processus possède les droits de lecture.  
- **L’archive ne s’ouvre pas avec d’anciennes versions de 7‑Zip ?** Optez pour BZip2 ou Store, car LZMA2 peut nécessiter des bibliothèques de décompression plus récentes.  
- **Goulot d’étranglement de performance ?** Pour des ensembles de données massifs, envisagez de diffuser l’archive au lieu de charger toutes les entrées en mémoire.

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Zip pour .NET avec n’importe quel type de fichier ?**  
R : Oui, Aspose.Zip prend en charge une large gamme de formats de fichiers, vous permettant de compresser et décompresser pratiquement n’importe quel type de fichier.

**Q : Une version d’essai gratuite est‑elle disponible pour Aspose.Zip pour .NET ?**  
R : Oui, vous pouvez obtenir une version d’essai gratuite **[ici](https://releases.aspose.com/)**.

**Q : Où puis‑je trouver la documentation d’Aspose.Zip pour .NET ?**  
R : La référence complète de l’API est disponible **[ici](https://reference.aspose.com/zip/net/)**.

**Q : Comment obtenir des licences temporaires pour Aspose.Zip pour .NET ?**  
R : Les licences temporaires peuvent être obtenues **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Où puis‑je obtenir du support pour Aspose.Zip pour .NET ?**  
R : Vous pouvez demander de l’aide sur le **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

---

**Dernière mise à jour :** 2026-06-29  
**Testé avec :** Aspose.Zip pour .NET 24.12  
**Auteur :** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [compress files c# – Create 7z archive with Aspose.Zip for .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [How to Zip Folder Using Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [How to Compress LZMA in Aspose.Zip for .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}