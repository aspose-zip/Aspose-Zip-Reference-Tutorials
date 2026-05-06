---
date: 2026-02-28
description: Apprenez comment ajouter un dossier à un zip et ajouter des fichiers
  à un zip en utilisant Aspose.Zip pour .NET. Ce guide étape par étape montre comment
  compresser des fichiers avec FileInfo dans les projets ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment ajouter un dossier à une archive zip avec Aspose.Zip pour .NET – Compresser
  des fichiers avec FileInfo
url: /fr/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Commenter ajouter un dossier à un zip avec Aspose.Zip pour .NET

## Introduction

Si vous devez **créer une archive zip** de manière programmatique, Aspose.Zip pour .NET vous offre une API propre et haute performance qui fonctionne dans n'importe quelle application .NET (y compris ASP.NET). Dans ce tutoriel, nous parcourrons la compression de fichiers avec la classe `FileInfo`, vous montrerons comment **ajouter des fichiers au zip**, et expliquerons pourquoi cette approche est idéale pour les projets .NET modernes. Nous aborderons également comment **ajouter un dossier au zip** afin que vous puissiez regrouper des répertoires entiers en une seule étape. Commençons!

## Réponses rapides
- **Quel est le moyen le plus simple de créer une archive zip ?** Utilisez la classe `Archive` d'Aspose.Zip avec des objets `FileInfo`.
- **Puis-je ajouter plusieurs fichiers à la fois ?** Oui – créez simplement un `FileInfo` pour chaque fichier et appelez `CreateEntry`.
- **Dois-je avoir une licence spéciale pour ASP.NET ?** Une licence commerciale Aspose.Zip est requise pour la production ; un essai gratuit suffit pour l’évaluation.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework4.5+, .NETCore3.1+, .NET5/6/7.
- **L'API est-elle thread‑safe ?** Oui, tant que chaque thread travaille avec sa propre instance `Archive`.

## Qu'est-ce qu'une archive Zip et pourquoi en créer une ?
Une archive zip regroupe un ou plusieurs fichiers dans un seul conteneur compressé. Cela réduit l’espace de stockage, accélère les transferts réseau et simplifie la distribution. Que vous livriez des journaux, exportiez des rapports ou empaquetiez des ressources pour un client, savoir **how to create zip archive** de façon programmatique est une compétence précieuse pour tout développeur .NET.

## Pourquoi utiliser Aspose.Zip pour ajouter des fichiers à compresser ?
- **Zéro dépendance externe** – implémentation pure .NET.
- **Contrôle total du niveau de compression et de l'encodage** (ASCII, UTF‑8, etc.).
- **Prend en charge les fichiers volumineux** (> 4 Go) et la protection par mot de passe.
- **API cohérente sur .NET Framework, .NET Core et .NET 5+**.

## Prérequis

Avant de sous-marin dans le code, assurez-vous d’avoir :

1. **Aspose.Zip pour .NET** installé. Téléchargez le dernier package depuis la [page de téléchargement Aspose.Zip](https://releases.aspose.com/zip/net/).
2. Un dossier sur votre machine contenant les fichiers que vous souhaitez compresser (par ex., `alice29.txt` et `fields.c`).

## Importer des espaces de noms

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

### Étape 1 : Configurez votre répertoire de documents

Tout d’abord, définissez le dossier qui contient les fichiers source. Remplacez le texte de substitution par le chemin absolu ou relatif sur votre système :

```csharp
string dataDir = "Your Document Directory";
```

> **Conseil pro :** Utilisez `Path.Combine` pour construire les chemins de manière multiplateforme.

### Étape 2 : Ouvrir un fichier Zip pour l'écriture

Créez un `FileStream` qui pointe vers le fichier zip de sortie. Le flux est ouvert en mode **Create**, ce qui écrase tout fichier existant du même nom :

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Étape 3 : Préparer les objets `FileInfo` pour chaque fichier source

`FileInfo` donne à Aspose.Zip un accès direct aux fichiers physiques sur le disque. Créez une instance par fichier que vous souhaitez compresser :

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** Cela évite de charger le fichier entier en mémoire, ce qui est particulièrement utile pour les gros fichiers.

### Étape 4 : Créer l'archive et ajouter des entrées

Instanciez un objet `Archive`, puis appelez `CreateEntry` pour chaque `FileInfo`. Le premier argument est le nom que le fichier aura à l’intérieur du zip, le second argument est le `FileInfo` source :

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Étape 5 : Enregistrez l'archive Zip avec l'encodage souhaité

Enfin, persistez l’archive dans le `FileStream` que vous avez ouvert précédemment. Ici nous utilisons l’encodage ASCII pour les noms d’entrée, mais vous pouvez passer à UTF‑8 si vos noms de fichiers contiennent des caractères non ASCII :

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Lorsque les blocs `using` se terminent, les flux sont automatiquement fermés et le fichier zip est prêt à l’emploi.

## Comment ajouter un dossier à Zip à l'aide d'Aspose.Zip

Si vous devez **ajouter un dossier au zip** plutôt que des fichiers individuels, le processus est simple :

1. **Énumérez le dossier** avec `DirectoryInfo.GetFiles` (et éventuellement `GetDirectories` pour la récursion).
2. **Créez un `FileInfo`** pour chaque fichier découvert.
3. **Call `CreateEntry`** avec un chemin relatif incluant le nom du dossier, par exemple, `"MyFolder/Report.pdf"`.

Comme l’API fonctionne avec `FileInfo`, vous n’avez jamais à charger des fichiers entiers en mémoire, ce qui la rend sûre pour les grands répertoires. Cette technique fonctionne également pour les scénarios **zip multiple files asp.net** où vous générerez un ensemble de rapports à la volée et devez le livrer sous forme d'une archive unique.

## Problèmes courants et solutions

| Problème | Parce que | Solutions |
|--------------|-------|--------------|
| **Fichier zip vide** | `FileInfo` pointe vers un chemin inexistant | Vérifiez `dataDir` et les noms de fichiers ; utilisez `File.Exists` pour valider avant de créer les entrées. |
| **Encodage incorrect du nom de fichier** | Utilisation de l’encodage par défaut avec des noms non ASCII | Définissez `Encoding = Encoding.UTF8` dans `ArchiveSaveOptions`. |
| **OutOfMemoryException sur les fichiers volumineux** | Chargement complet du fichier en mémoire | `FileInfo` diffuse le fichier; Assurez-vous de ne pas lire le fichier dans un tableau d’octets ailleurs. |
| **Autorisation refusée** | L’application n’a pas les droits d’écriture sur le dossier de sortie | Exécutez l’application avec les droits appropriés ou choisissez un répertoire accessible en écriture. |

### FAQ

#### Q1 : Aspose.Zip est-il compatible avec tous les types de fichiers ?

A1 : Aspose.Zip prend en charge un large éventail de types de fichiers, garantissant une grande polyvalence en matière de compression.

#### Q2 : Puis-je utiliser Aspose.Zip pour des projets commerciaux ?

A2 : Absolument ! Consultez notre [page d'achat](https://purchase.aspose.com/buy) pour découvrir nos options de licence.

#### Q3 : Comment obtenir de l'aide pour Aspose.Zip ?

A3 : Rejoignez notre communauté sur le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour obtenir de l'aide et participer aux discussions.

#### Q4 : Existe-t-il une version d'essai gratuite ?

A4 : Oui, vous pouvez télécharger votre [version d'essai gratuite](https://releases.aspose.com/).

#### Q5 : Comment obtenir une licence temporaire pour Aspose.Zip ?

A5 : Visitez [ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir des informations sur l'obtention d'une licence temporaire.

## Conclusion

Vous savez maintenant **comment ajouter un dossier au zip** et **comment créer une archive zip** avec Aspose.Zip pour .NET, commenter **ajouter des fichiers au zip**, et pourquoi cette méthode est idéale pour ASP.NET et les autres applications .NET. Expérimentez avec différents niveaux de compression, encodages et options de chiffrement pour adapter l’archive à vos besoins précis. Bonne compression !

---

**Dernière mise à jour :** 2026-02-28
**Testé avec :** Aspose.Zip pour .NET 24.12 (dernier)
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}