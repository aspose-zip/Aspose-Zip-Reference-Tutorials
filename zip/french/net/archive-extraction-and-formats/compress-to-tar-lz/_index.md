---
date: 2025-12-01
description: Apprenez à compresser des fichiers tar.lz en .NET avec Aspose.Zip et
  créez facilement une archive tar.lz.
language: fr
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser tar.lz avec Aspose.Zip pour .NET
url: /net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment compresser tar.lz avec Aspose.Zip pour .NET

Dans le développement .NET moderne, empaqueter efficacement les fichiers peut améliorer considérablement la taille du déploiement et les temps de transfert réseau. **Comment compresser tar.lz** est une exigence courante lorsque vous avez besoin d’une archive TAR légère compressée en LZ. Dans ce tutoriel, nous parcourrons un **exemple de compression tar.lz** clair, étape par étape, en utilisant la bibliothèque Aspose.Zip, afin que vous puissiez créer rapidement une archive tar.lz dans vos propres applications.

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Zip pour .NET.  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes pour un exemple de base.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis‑je compresser plusieurs fichiers à la fois ?** Oui – ajoutez simplement plus d’entrées avant d’enregistrer.

## Qu’est‑ce que la compression tar.lz ?
`tar.lz` est une archive TAR qui a été compressée à l’aide de l’algorithme LZMA (souvent appelé simplement **LZ**). Elle combine la simplicité du groupement de fichiers de TAR avec le taux de compression élevé de LZ, ce qui la rend idéale pour les sauvegardes, la distribution de paquets ou tout scénario où la bande passante est critique.

## Pourquoi utiliser Aspose.Zip pour .NET ?
Aspose.Zip abstrait les détails bas‑niveau de la création d’archives, vous offrant une API orientée objet propre. Vous bénéficiez de :

* **Aucune dépendance externe** – implémentation pure .NET.  
* **Support multiplateforme** – fonctionne sous Windows, Linux et macOS.  
* **Compression LZ intégrée** – aucune installation d’outils natifs supplémentaires.  
* **Gestion robuste des erreurs** – les exceptions sont descriptives, facilitant le débogage.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- La bibliothèque **Aspose.Zip pour .NET** – téléchargez‑la depuis [here](https://releases.aspose.com/zip/net/).  
- Un dossier contenant les fichiers à archiver. Le chemin de ce dossier sera stocké dans la variable `dataDir` (vous le définirez à l’étape 3).

## Importer les espaces de noms
Ajoutez les espaces de noms requis afin que le compilateur sache où trouver les classes que nous allons utiliser.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Comment créer une archive tar.lz – Guide étape par étape

### Étape 1 : Compresser un seul fichier
Le premier exemple montre le scénario le plus basique – ajouter un fichier à une archive TAR puis l’enregistrer sous forme de fichier **tar.lz**.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Explication**

- `new TarArchive()` crée un conteneur TAR vide.  
- `CreateEntry` ajoute le fichier `alice29.txt` depuis votre `dataDir`.  
- `SaveLzipped` écrit l’archive sur le disque et applique la compression LZ, produisant `archive.tar.lz`.

### Étape 2 : Compresser plusieurs fichiers dans une même archive
Souvent, vous devez regrouper plusieurs fichiers. Appelez simplement `CreateEntry` pour chaque fichier avant d’enregistrer.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Explication**

- Le code suit le même schéma que l’Étape 1, mais ajoute une seconde entrée (`lcet10.txt`).  
- Vous pouvez répéter `CreateEntry` autant de fois que nécessaire ; la bibliothèque gère automatiquement la structure interne du TAR.

### Étape 3 : Spécifier votre répertoire de documents
Remplacez le texte de substitution par le chemin réel où résident vos fichiers source. Ce chemin est utilisé par les exemples précédents.

```csharp
string dataDir = "Your Document Directory";
```

**Explication**

- Définissez `dataDir` avec un chemin de dossier complet, par ex. `@"C:\MyFiles\"`.  
- Conserver le répertoire dans une variable rend le code réutilisable et plus facile à maintenir.

## Problèmes courants et dépannage
| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| `FileNotFoundException` lors de l’exécution de l’exemple | `dataDir` pointe vers un dossier inexistant ou le nom du fichier est mal orthographié | Vérifiez le chemin et les noms de fichiers ; utilisez `Path.Combine` pour plus de sécurité. |
| Le fichier de sortie fait **0 KB** | `archive.SaveLzipped` a été appelé avant l’ajout d’entrées | Assurez‑vous qu’au moins un appel à `CreateEntry` précède `SaveLzipped`. |
| La compression semble lente | Fichiers volumineux avec la taille de tampon par défaut | Envisagez de traiter les fichiers par blocs ou d’utiliser I/O asynchrone si les performances sont critiques. |

## Conclusion
Vous savez maintenant **comment compresser des fichiers tar.lz** avec Aspose.Zip pour .NET, que vous traitiez un seul document ou une collection de fichiers. Cet **exemple de compression tar.lz** montre une méthode propre et prête pour la production afin de créer des archives légères, facilement transférables ou stockables.

## Questions fréquentes

**Q :** Puis‑je compresser des fichiers de n’importe quelle taille avec Aspose.Zip pour .NET ?  
**R :** Oui, la bibliothèque gère les petits comme les très gros fichiers ; assurez‑vous simplement de disposer de suffisamment de mémoire et d’espace disque pour la structure TAR temporaire.

**Q :** Le code est‑il compatible avec la dernière version d’Aspose.Zip ?  
**R :** L’exemple cible la version actuelle ; maintenez toujours le package NuGet à jour pour les correctifs et nouvelles fonctionnalités.

**Q :** Y a‑t‑il des considérations de licence ?  
**R :** Une licence commerciale est requise pour une utilisation en production. Consultez les détails de licence sur le [site Aspose](https://purchase.aspose.com/buy).

**Q :** Puis‑je utiliser cela dans un projet commercial ?  
**R :** Absolument – une fois que vous disposez d’une licence valide, vous pouvez intégrer la bibliothèque dans n’importe quelle application commerciale.

**Q :** Où puis‑je obtenir de l’aide en cas de problème ?  
**R :** Visitez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour le support communautaire et l’assistance officielle.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-01  
**Testé avec :** Aspose.Zip pour .NET (dernière version)  
**Auteur :** Aspose  

---