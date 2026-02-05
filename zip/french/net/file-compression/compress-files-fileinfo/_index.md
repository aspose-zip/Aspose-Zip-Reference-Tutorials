---
date: 2026-02-05
description: Apprenez à compresser plusieurs fichiers en C# et à créer une archive
  zip .NET avec Aspose.Zip. Ce guide étape par étape montre comment compresser des
  fichiers avec FileInfo dans les projets ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser plusieurs fichiers en C# avec Aspose.Zip pour .NET
url: /fr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment zipper plusieurs fichiers c# avec Aspose.Zip pour .NET

## Introduction

Si vous devez **zipper plusieurs fichiers c#** de façon programmatique, Aspose.Zip pour .NET vous offre une API propre et haute performance qui fonctionne dans n’importe quelle application .NET (y compris ASP.NET). Dans ce tutoriel, nous parcourrons la compression de fichiers avec la classe `FileInfo`, vous montrerons comment **ajouter des fichiers à un zip**, et expliquerons pourquoi cette approche est idéale pour les projets .NET modernes. C’est parti !

## Réponses rapides
- **Quelle est la façon la plus simple de créer une archive zip ?** Utilisez la classe `Archive` d’Aspose.Zip avec des objets `FileInfo`.  
- **Puis‑je ajouter plusieurs fichiers en même temps ?** Oui – créez simplement un `FileInfo` pour chaque fichier et appelez `CreateEntry`.  
- **Ai‑je besoin d’une licence spéciale pour ASP.NET ?** Une licence commerciale Aspose.Zip est requise en production ; un essai gratuit suffit pour l’évaluation.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **L’API est‑elle thread‑safe ?** Oui, tant que chaque thread travaille avec sa propre instance `Archive`.  
- **Comment zipper des fichiers c# sans les charger en mémoire ?** Utilisez des objets `FileInfo` – ils diffusent les données directement.  

## Comment zipper plusieurs fichiers c#
Une archive zip regroupe un ou plusieurs fichiers dans un seul conteneur compressé. Cela réduit l’espace de stockage, accélère les transferts réseau et simplifie la distribution. Que vous livriez des journaux, exportiez des rapports ou empaquetiez des ressources pour un client, savoir **comment zipper des fichiers c#** de façon programmatique est une compétence précieuse pour tout développeur .NET.

## Pourquoi utiliser Aspose.Zip pour ajouter des fichiers à un zip ?
- **Aucune dépendance externe** – implémentation pure .NET.  
- **Contrôle total du niveau de compression et de l’encodage** (ASCII, UTF‑8, etc.).  
- **Prise en charge des gros fichiers** (> 4 GB) et de la protection par mot de passe.  
- **API cohérente sur .NET Framework, .NET Core et .NET 5+**.

## Prérequis

Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Aspose.Zip pour .NET** installé. Téléchargez le dernier package depuis la [page de téléchargement d’Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Un dossier sur votre machine contenant les fichiers à compresser (par ex., `alice29.txt` et `fields.c`).  

## Importer les espaces de noms

Dans tout fichier C# où vous travaillerez avec des archives zip, ajoutez les instructions `using` suivantes :

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Ces espaces de noms vous donnent accès à la classe `Archive`, aux options de sauvegarde et aux utilitaires d’E/S standards.

## Guide étape par étape

### Étape 1 : Configurer votre répertoire de documents

Tout d’abord, définissez le dossier qui contient les fichiers source. Remplacez le texte de substitution par le chemin absolu ou relatif sur votre système :

```csharp
string dataDir = "Your Document Directory";
```

> **Astuce :** Utilisez `Path.Combine` pour construire les chemins de façon multiplateforme.

### Étape 2 : Ouvrir un fichier Zip en écriture

Créez un `FileStream` qui pointe vers le fichier zip de sortie. Le flux est ouvert en mode **Create**, ce qui écrase tout fichier existant du même nom :

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Étape 3 : Préparer les objets `FileInfo` pour chaque fichier source

`FileInfo` donne à Aspose.Zip un accès direct aux fichiers physiques sur le disque. Créez une instance par fichier que vous souhaitez compresser :

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Pourquoi utiliser `FileInfo` ?** Cela évite de charger le fichier entier en mémoire, ce qui est particulièrement utile pour les gros fichiers.

### Étape 4 : Créer l’archive et ajouter les entrées

Instanciez un objet `Archive`, puis appelez `CreateEntry` pour chaque `FileInfo`. Le premier argument est le nom que le fichier aura dans le zip, le second argument est le `FileInfo` source :

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Étape 5 : Enregistrer l’archive Zip avec l’encodage souhaité

Enfin, persistez l’archive dans le `FileStream` que vous avez ouvert précédemment. Ici nous utilisons l’encodage ASCII pour les noms d’entrée, mais vous pouvez passer à UTF‑8 si vos noms de fichiers contiennent des caractères non ASCII :

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Lorsque les blocs `using` se terminent, les flux sont fermés automatiquement et le fichier zip est prêt à l’emploi.

## Problèmes courants & solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Fichier zip vide** | `FileInfo` pointe vers un chemin inexistant | Vérifiez `dataDir` et les noms de fichiers ; utilisez `File.Exists` pour valider avant de créer les entrées. |
| **Encodage de nom de fichier incorrect** | Utilisation de l’encodage par défaut avec des noms non ASCII | Définissez `Encoding = Encoding.UTF8` dans `ArchiveSaveOptions`. |
| **OutOfMemoryException sur de gros fichiers** | Chargement complet du fichier en mémoire | `FileInfo` diffuse le fichier ; assurez‑vous de ne pas le lire dans un tableau d’octets ailleurs. |
| **Permission refusée** | L’application n’a pas les droits d’écriture sur le dossier de sortie | Exécutez l’application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

## Questions fréquentes

**Q : Puis‑je ajouter une protection par mot de passe à l’archive zip ?**  
R : Oui. Après avoir créé l’`Archive`, définissez `archive.Password = "yourPassword"` avant d’appeler `Save`.

**Q : Est‑il possible de mettre à jour un fichier zip existant ?**  
R : Aspose.Zip permet d’ouvrir une archive existante avec `Archive.Open` puis d’ajouter de nouvelles entrées.

**Q : Comment compresser des fichiers dans un contrôleur ASP.NET MVC ?**  
R : Le même code fonctionne ; assurez‑vous simplement que le flux de sortie est renvoyé comme un `FileResult` au client.

**Q : Aspose.Zip prend‑il en charge les algorithmes de chiffrement ?**  
R : Il prend en charge le ZipCrypto standard et le chiffrement AES‑256.

**Q : Et si je dois compresser un dossier de façon récursive ?**  
R : Parcourez `Directory.GetFiles` (et les sous‑dossiers), créez un `FileInfo` pour chaque fichier, puis ajoutez‑les à l’archive.

## Existing FAQ Section (kept unchanged)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusion

Vous savez maintenant **comment zipper plusieurs fichiers c#** avec Aspose.Zip pour .NET, comment **ajouter des fichiers à un zip**, et pourquoi cette méthode est idéale pour ASP.NET et les autres applications .NET. Expérimentez avec différents niveaux de compression, encodages et options de chiffrement pour adapter l’archive à vos besoins précis. Bonne compression !

---

**Dernière mise à jour :** 2026-02-05  
**Testé avec :** Aspose.Zip pour .NET 24.12 (latest)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}