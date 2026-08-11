---
date: 2026-05-30
description: Apprenez à créer un zip sans compression en .NET avec Aspose.Zip pour
  .NET. Ce guide vous montre comment zipper des fichiers sans compression, stocker
  les fichiers non compressés et gérer les archives efficacement.
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: Stockage de plusieurs fichiers sans compression
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Créer un zip sans compression en .NET avec Aspose.Zip
url: /fr/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un zip sans compression en .NET avec Aspose.Zip

Dans le développement .NET moderne, **créer un zip sans compression** peut améliorer considérablement la vitesse d'archivage et garder les tailles de fichiers prévisibles. Lorsque vous devez **zipper des fichiers sans compression** — par exemple, pour respecter des règles réglementaires, accélérer le traitement en aval, ou garantir que la séquence d'octets originale reste intacte — Aspose.Zip pour .NET fournit une API propre et simple. Dans ce tutoriel, nous parcourrons les étapes exactes pour créer une archive ZIP non compressée, ajouter des fichiers et intégrer la solution dans votre application.

## Réponses rapides
- **Que signifie « zip non compressé » ?** C’est une archive ZIP où chaque entrée est stockée en utilisant la méthode « store », laissant les octets du fichier original intacts.  
- **Pourquoi éviter la compression ?** Pour accélérer l'archivage, préserver les tailles de fichiers originales pour le traitement en aval, ou respecter les exigences réglementaires qui interdisent la modification des données.  
- **Quelle classe Aspose.Zip gère cela ?** `ArchiveEntrySettings` combiné avec `StoreCompressionSettings`.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit fonctionne pour les tests ; une licence commerciale est requise pour la production.  
- **Versions .NET prises en charge ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, et .NET 5–10.  

## Qu'est-ce qu'un zip sans compression ?
**Zip sans compression** est une archive ZIP où chaque entrée de fichier utilise la méthode *store*, ce qui signifie que les données sont copiées mot pour mot dans l'archive sans aucun algorithme de compression appliqué. Cela donne une archive dont la taille est essentiellement la somme des fichiers originaux plus quelques octets de surcharge ZIP.

## Pourquoi utiliser Aspose.Zip pour les fichiers zip sans compression ?
Aspose.Zip est optimisé pour l'archivage à haute performance, vous permettant de stocker des fichiers instantanément sans la surcharge des algorithmes de compression. Il garantit une compatibilité ZIP complète, vous permet de mélanger des entrées stockées et compressées, et fournit une API simple qui abstrait les structures ZIP de bas niveau, rendant l'implémentation rapide et fiable.

## Prérequis
- **Aspose.Zip for .NET** – intégré à votre projet. Consultez la [documentation](https://reference.aspose.com/zip/net/) officielle pour les étapes d'installation.  
- **Environnement de développement .NET** – Visual Studio, VS Code, ou tout IDE de votre choix.  
- **Répertoire de documents** – un dossier sur votre machine contenant les fichiers que vous souhaitez archiver (par ex., « Your Document Directory »).

## Importer les espaces de noms
Avant d'écrire du code, importez les espaces de noms requis afin que le compilateur sache où trouver les classes Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Étape 1 : définir le répertoire de documents
Définissez le chemin où résident vos fichiers source. Remplacez le texte de substitution par le dossier réel sur votre système.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : créer une archive Zip sans compression
Le cœur du tutoriel – nous créons une instance `Archive` configurée avec `StoreCompressionSettings`. `Archive` représente un conteneur ZIP pouvant contenir plusieurs entrées. `StoreCompressionSettings` indique qu'une entrée doit être stockée sans compression. Cela indique à Aspose.Zip de *stocker* (c’est‑à‑dire de ne pas compresser) chaque entrée.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Astuce :** Si vous devez **enregistrer des fichiers dans un zip** tout en compressant certains et en laissant d’autres non compressés, créez des instances séparées de `ArchiveEntrySettings` pour chaque fichier et ajoutez‑les au même `Archive`.

## Comment créer un zip sans compression en .NET ?
Chargez vos fichiers source, créez une instance d’objet `Archive`, et ajoutez chaque fichier en utilisant `ArchiveEntrySettings` avec `new StoreCompressionSettings()`. L’opération complète ne nécessite que trois lignes de code et s’exécute en temps linéaire par rapport à la taille totale des fichiers, vous offrant l’expérience d’archivage la plus rapide possible.

### Guide étape par étape
1. **Créer l'archive** – instancier `Archive` avec un flux cible ou un chemin de fichier.  
2. **Configurer les paramètres d'entrée** – pour chaque fichier, créez un objet `ArchiveEntrySettings` et assignez `new StoreCompressionSettings()` à sa propriété `Compression`.  
3. **Ajouter les entrées** – appelez `archive.Add(entrySettings)` pour chaque fichier, puis finalisez avec `archive.Save()`.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Fichier non trouvé** | Chemin `dataDir` incorrect ou extension de fichier manquante. | Vérifiez le chemin et assurez‑vous que les fichiers existent. Utilisez `Path.Combine` pour une concaténation plus sûre. |
| **Accès refusé** | Le processus n’a pas les permissions nécessaires pour lire les fichiers source ou écrire le ZIP. | Exécutez l’application avec les droits appropriés ou choisissez un dossier avec des droits d’écriture. |
| **Taille de fichier inattendue dans le ZIP** | L’archive a été créée avec la compression par défaut. | Assurez‑vous que `new StoreCompressionSettings()` est passé à `ArchiveEntrySettings`. |

## Questions fréquentes

**Q : Puis‑je compresser certains types de fichiers tout en stockant d’autres sans compression ?**  
A : Oui, vous pouvez créer différents `ArchiveEntrySettings` pour chaque fichier et mélanger des entrées compressées et non compressées dans la même archive.

**Q : Aspose.Zip pour .NET est‑il compatible avec .NET Core et .NET 5/6 ?**  
A : Absolument. La bibliothèque prend en charge .NET Framework, .NET Core, .NET Standard et les dernières versions de .NET.

**Q : Comment devrais‑je gérer les exceptions pendant le processus d’archivage ?**  
A : Enveloppez le code d’archivage dans un bloc `try‑catch` et consignez les détails de l’exception. Cela assure un échec gracieux et facilite le débogage.

**Q : Aspose.Zip prend‑il en charge l’archivage multi‑threadé ?**  
A : Oui, vous pouvez traiter plusieurs fichiers en parallèle et les ajouter à l’archive, mais rappelez‑vous que l’objet `Archive` n’est pas thread‑safe ; synchronisez l’accès lors de l’ajout d’entrées.

**Q : Puis‑je intégrer Aspose.Zip dans un projet existant sans modifications majeures du code ?**  
A : Définitivement. L’API est conçue pour une utilisation simple en insertion directe. Consultez la [documentation](https://reference.aspose.com/zip/net/) officielle pour les conseils de migration.

---

**Dernière mise à jour :** 2026-05-30  
**Testé avec :** Aspose.Zip for .NET (latest version at time of writing)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}