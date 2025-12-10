---
date: 2025-12-10
description: Apprenez à stocker des fichiers sans compression avec Aspose.Zip pour
  .NET. Ce guide vous montre comment créer un zip non compressé, enregistrer des fichiers
  dans le zip et gérer les archives efficacement.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment stocker des fichiers non compressés avec Aspose.Zip pour .NET
url: /fr/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment stocker des fichiers non compressés avec Aspose.Zip pour .NET

Dans le développement .NET moderne, **comment stocker des fichiers** efficacement peut faire une grande différence en termes de performances et de coûts de stockage. Lorsque vous devez conserver les fichiers exactement tels quels—sans aucune compression—Aspose.Zip pour .NET fournit une API claire et simple. Dans ce tutoriel, nous parcourrons les étapes pour créer une archive ZIP non compressée, enregistrer des fichiers dans le ZIP et intégrer la solution dans votre application.

## Réponses rapides
- **Que signifie « zip non compressé » ?** C’est une archive ZIP où chaque entrée est stockée en utilisant la méthode « store », laissant les octets du fichier original intacts.  
- **Pourquoi éviter la compression ?** Pour accélérer l’archivage, préserver les tailles originales des fichiers pour le traitement en aval, ou répondre à des exigences réglementaires interdisant toute altération des données.  
- **Quelle classe Aspose.Zip gère cela ?** `ArchiveEntrySettings` combinée avec `StoreCompressionSettings`.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Versions .NET prises en charge ?** .NET Framework, .NET Core, .NET 5/6/7 et ultérieures.

## Qu’est‑ce que le stockage de plusieurs fichiers sans compression ?
Stocker plusieurs fichiers sans compression signifie ajouter chaque fichier à un conteneur ZIP en utilisant la méthode de compression *store*. Les fichiers restent identiques octet par octet aux originaux, ce qui est idéal lorsque vous souhaitez un archivage rapide ou devez conserver les données inchangées.

## Pourquoi utiliser Aspose.Zip pour les archives non compressées ?
- **Vitesse :** Aucun algorithme de compression gourmand en CPU n’est exécuté.  
- **Taille prévisible :** La taille de l’archive équivaut à la somme des fichiers originaux plus un overhead ZIP minimal.  
- **Compatibilité :** Le ZIP résultant fonctionne avec n’importe quel utilitaire de décompression standard.  
- **Flexibilité :** Vous pouvez toujours mélanger des entrées compressées et non compressées dans la même archive si nécessaire.

## Prérequis
- **Aspose.Zip for .NET** – intégré à votre projet. Consultez la [documentation](https://reference.aspose.com/zip/net/) officielle pour les étapes d’installation.  
- **Environnement de développement .NET** – Visual Studio, VS Code ou tout IDE de votre choix.  
- **Répertoire de documents** – un dossier sur votre machine contenant les fichiers que vous souhaitez archiver (par ex., « Your Document Directory »).

## Importer les espaces de noms
Avant d’écrire du code, importez les espaces de noms requis afin que le compilateur sache où trouver les classes Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Étape 1 : définir le répertoire de documents
Définissez le chemin où résident vos fichiers source. Remplacez le texte de substitution par le dossier réel sur votre système.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : créer une archive Zip sans compression
Le cœur du tutoriel – nous créons une instance `Archive` configurée avec `StoreCompressionSettings`. Cela indique à Aspose.Zip de *stocker* (c’est‑à‑dire de ne pas compresser) chaque entrée.

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

> **Astuce :** Si vous devez **enregistrer des fichiers dans le zip** tout en compressant certains et en laissant d’autres non compressés, créez des instances `ArchiveEntrySettings` séparées pour chaque fichier et ajoutez‑les à la même `Archive`.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Fichier non trouvé** | Chemin `dataDir` incorrect ou extension de fichier manquante. | Vérifiez le chemin et assurez‑vous que les fichiers existent. Utilisez `Path.Combine` pour une concaténation plus sûre. |
| **Accès refusé** | Le processus n’a pas les permissions nécessaires pour lire les fichiers source ou écrire le ZIP. | Exécutez l’application avec les droits appropriés ou choisissez un dossier avec accès en écriture. |
| **Taille de fichier inattendue dans le ZIP** | L’archive a été créée avec la compression par défaut. | Assurez‑vous que `new StoreCompressionSettings()` est passé à `ArchiveEntrySettings`. |

## Questions fréquemment posées

**Q : Puis‑je compresser certains types de fichiers tout en stockant d’autres sans compression ?**  
R : Oui, vous pouvez créer différents `ArchiveEntrySettings` pour chaque fichier et mélanger des entrées compressées et non compressées dans la même archive.

**Q : Aspose.Zip pour .NET est‑il compatible avec .NET Core et .NET 5/6 ?**  
R : Absolument. La bibliothèque prend en charge .NET Framework, .NET Core, .NET Standard et les dernières versions de .NET.

**Q : Comment gérer les exceptions pendant le processus d’archivage ?**  
R : Enveloppez le code d’archivage dans un bloc `try‑catch` et consignez les détails de l’exception. Cela assure un échec gracieux et facilite le débogage.

**Q : Aspose.Zip prend‑il en charge l’archivage multithread ?**  
R : Oui, vous pouvez traiter plusieurs fichiers en parallèle et les ajouter à l’archive, mais souvenez‑vous que l’objet `Archive` n’est pas thread‑safe ; synchronisez l’accès lors de l’ajout d’entrées.

**Q : Puis‑je intégrer Aspose.Zip dans un projet existant sans modifications majeures du code ?**  
R : Définitivement. L’API est conçue pour une utilisation simple en mode « drop‑in ». Consultez la [documentation](https://reference.aspose.com/zip/net/) officielle pour les conseils de migration.

---

**Dernière mise à jour :** 2025-12-10  
**Testé avec :** Aspose.Zip for .NET 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}