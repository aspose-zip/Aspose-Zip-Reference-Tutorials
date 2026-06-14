---
date: 2026-06-14
description: Apprenez à lire les fichiers GZIP et à les extraire vers un MemoryStream
  en utilisant Aspose.Zip pour .NET – un tutoriel concis pour les développeurs C#.
keywords:
- how to read gzip
- how to extract zip
- extract zip to stream
- c# extract zip stream
linktitle: Extraction vers Memory Stream
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read GZIP files and extract them to a MemoryStream using
    Aspose.Zip for .NET – a concise tutorial for C# developers.
  headline: How to Read GZIP and Extract to MemoryStream with Aspose.Zip
  type: TechArticle
- description: Learn how to read GZIP files and extract them to a MemoryStream using
    Aspose.Zip for .NET – a concise tutorial for C# developers.
  name: How to Read GZIP and Extract to MemoryStream with Aspose.Zip
  steps:
  - name: Set Up Your Document Directory
    text: Define the path where your sample archive resides.
  - name: Initialize a MemoryStream
    text: Create an empty `MemoryStream` that will receive the extracted data.
  - name: Open the GZIP Archive and Extract
    text: The `CopyTo` method **copies the archive to MemoryStream**, giving you an
      in‑memory representation of the original file. `CopyTo` copies data from one
      stream to another efficiently.
  - name: Verify the Extraction
    text: A simple console message confirms success.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip supports .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10, making it versatile for modern applications.
    question: Is Aspose.Zip compatible with all versions of .NET?
  - answer: Absolutely. The library provides both extraction and creation APIs, allowing
      you to build ZIP files programmatically.
    question: Can I use Aspose.Zip to create ZIP archives as well?
  - answer: Visit the [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) for community
      help and official guidance.
    question: Where can I find additional support or examples?
  - answer: Yes, you can start a free trial by downloading from the Aspose website
      [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: A temporary license can be requested from the Aspose portal [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment lire les fichiers GZIP et les extraire vers MemoryStream avec Aspose.Zip
url: /fr/net/other-compression-techniques/extract-to-memory-stream/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire un GZIP et extraire vers MemoryStream avec Aspose.Zip

## Introduction

Si vous cherchez un moyen fiable de **lire des archives gzip** directement en mémoire, Aspose.Zip pour .NET le rend simple. Dans ce tutoriel, nous allons parcourir l'extraction d'un fichier GZIP vers un `MemoryStream`, que vous pouvez ensuite traiter comme toute autre source de données en mémoire — parfait pour traiter des fichiers à la volée, envoyer des données sur un réseau, ou éviter les fichiers temporaires sur le disque.  
`MemoryStream` est un flux .NET qui stocke les données en mémoire, permettant une lecture/écriture rapide sans I/O disque.

## Réponses rapides
- **Quelle bibliothèque gère l'extraction ZIP/GZIP ?** Aspose.Zip for .NET  
- **Puis-je extraire vers un MemoryStream ?** Oui – utilisez `CopyTo` sur l'archive ouverte.  
- **Formats pris en charge ?** ZIP, GZIP, TAR, et plus.  
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit fonctionne pour les tests ; une licence est requise pour la production.  
- **Quelles versions de .NET sont compatibles ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, et .NET 5–10

## Qu'est-ce qu'Aspose.Zip ?

Aspose.Zip est une bibliothèque .NET qui simplifie la manipulation d'archives compressées. Elle abstrait les détails de bas niveau des formats ZIP et GZIP, vous permettant de vous concentrer sur la logique métier — comme **copier l'archive vers memorystream** — au lieu de la plomberie du système de fichiers.

## Pourquoi extraire vers MemoryStream ?

Extraire vers un `MemoryStream` évite la surcharge de création de fichiers temporaires, réduit la latence I/O et facilite le passage des données aux API qui attendent un flux (par ex., réponses HTTP, processeurs d'images, ou bases de données en mémoire). Cela est particulièrement pratique dans les architectures cloud‑native ou micro‑services.

## Prérequis
- **Visual Studio** (toute édition récente).  
- **Aspose.Zip for .NET** – téléchargez‑le depuis le site officiel [ici](https://releases.aspose.com/zip/net/).  
- Un dossier contenant une archive GZIP d'exemple nommée `sample.gz`.

## Importer les espaces de noms

Ajoutez les espaces de noms requis à votre fichier C# :

```csharp
using Aspose.Zip.Gzip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Comment lire un fichier GZIP en .NET ?

Chargez l'archive GZIP avec `GzipArchive.Open` et copiez son entrée dans un `MemoryStream`. Ce modèle en deux étapes lit les données compressées directement en mémoire sans toucher au système de fichiers, vous donnant un accès instantané aux octets décompressés. La méthode `GzipArchive.Open` ouvre un fichier GZIP et renvoie un objet GzipArchive pour lire ses entrées. Vous pouvez également spécifier un chemin relatif ou absolu, et la bibliothèque gérera l'ouverture du flux de fichier en interne, assurant une libération correcte après l'extraction.

### Étape 1 : Configurer votre répertoire de documents

Définissez le chemin où se trouve votre archive d'exemple.

```csharp
string dataDir = "Your Document Directory";
```

### Étape 2 : Initialiser un MemoryStream

Créez un `MemoryStream` vide qui recevra les données extraites.

```csharp
var ms = new MemoryStream();
```

### Étape 3 : Ouvrir l'archive GZIP et extraire

La méthode `CopyTo` **copie l'archive vers MemoryStream**, vous offrant une représentation en mémoire du fichier original. `CopyTo` copie les données d'un flux à un autre de manière efficace.

```csharp
//ExStart: ExtractToMemoryStream
using (GzipArchive archive = new GzipArchive(File.OpenRead(dataDir + "sample.gz")))
{
    archive.Open().CopyTo(ms);
    Console.WriteLine(archive.Name);
}
//ExEnd: ExtractToMemoryStream
```

### Étape 4 : Vérifier l'extraction

Un simple message console confirme le succès.

```csharp
Console.WriteLine("Successfully Extracted to Memory Stream");
```

## Comment extraire un ZIP vers un flux en C# ?

Utilisez le même flux de travail — remplacez `GzipArchive` par `ZipArchive`. `ZipArchive` représente un fichier ZIP et fournit des méthodes pour lire ou extraire ses entrées. Appelez `zipArchive.ExtractAllToStream(memoryStream)` (ou parcourez les entrées et utilisez `CopyTo`) et vous disposerez de tout le contenu du ZIP dans un `MemoryStream`. `ExtractAllToStream` extrait toutes les entrées de l'archive directement dans le flux fourni. De plus, vous pouvez définir les niveaux de compression ou préserver la structure des répertoires en configurant les options de l'archive avant l'extraction. Cette approche fonctionne pour tout type d'archive pris en charge par Aspose.Zip.

## Pièges courants et astuces
- **Réinitialiser le MemoryStream :** Après l'extraction, définissez `ms.Position = 0` avant de lire le flux ailleurs.  
- **Fichiers volumineux :** Pour des archives très grandes, envisagez de traiter le flux par morceaux afin d'éviter une consommation élevée de mémoire. Aspose.Zip peut gérer des archives contenant **plus de 500 fichiers** et d'une taille totale allant jusqu'à **2 GB** sans charger l'intégralité de l'archive en mémoire.  
- **Libération des ressources :** Le bloc `using` garantit que le handle du fichier d'archive est libéré rapidement.

## Questions fréquentes

**Q : Aspose.Zip est‑il compatible avec toutes les versions de .NET ?**  
R : Oui, Aspose.Zip prend en charge .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, et .NET 5–10, ce qui le rend polyvalent pour les applications modernes.

**Q : Puis‑je utiliser Aspose.Zip pour créer des archives ZIP également ?**  
R : Absolument. La bibliothèque fournit à la fois des API d'extraction et de création, vous permettant de générer des fichiers ZIP par programme.

**Q : Où puis‑je trouver un support supplémentaire ou des exemples ?**  
R : Consultez le [Forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour l'aide de la communauté et les directives officielles.

**Q : Une version d'essai gratuite est‑elle disponible ?**  
R : Oui, vous pouvez démarrer un essai gratuit en téléchargeant depuis le site Aspose [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Une licence temporaire peut être demandée via le portail Aspose [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion

Dans ce **tutoriel Aspose Zip** nous avons couvert le processus complet de lecture d'une archive GZIP et de son extraction vers un `MemoryStream` en utilisant Aspose.Zip pour .NET. En suivant ces étapes, vous pouvez efficacement **copier l'archive vers memorystream**, éviter les fichiers temporaires et intégrer les données extraites directement dans la logique de votre application. N'hésitez pas à explorer d'autres formats d'archive et des fonctionnalités avancées comme la protection par mot de passe ou l'extraction multithread.

---

**Dernière mise à jour :** 2026-06-14  
**Testé avec :** Aspose.Zip 24.12 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment ouvrir une archive GZip et autres techniques de compression avec Aspose.Zip pour .NET](/zip/net/other-compression-techniques/)
- [Comment décompresser des fichiers avec Aspose.Zip pour .NET](/zip/net/file-decompression/)
- [Décompresser des fichiers AES - Tutoriel Aspose.Zip .NET](/zip/net/password-protection-and-encryption/decompress-aes-encrypted-file/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}