---
date: 2026-02-28
description: Apprenez à compresser des fichiers avec mot de passe et à chiffrer des
  archives ZIP à l'aide d'Aspose.Zip pour .NET, en couvrant la protection par mot
  de passe des fichiers 7z et le mot de passe par fichier ZIP en C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment compresser des fichiers avec un mot de passe et chiffrer les entrées
  ZIP avec des mots de passe différents en utilisant Aspose.Zip pour .NET
url: /fr/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment compresser des fichiers avec mot de passe et chiffrer les entrées ZIP avec des mots de passe différents en utilisant Aspose.Zip pour .NET

## Introduction

Si vous devez **compresser des fichiers avec mot de passe** et attribuer à chaque entrée son propre mot de passe, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue les étapes exactes pour créer une archive 7‑zip où chaque fichier est protégé par un mot de passe unique, en utilisant la bibliothèque Aspose.Zip pour .NET. À la fin, vous comprendrez pourquoi le chiffrement par entrée est important, comment le configurer et comment vérifier le résultat dans vos propres projets.

## Réponses rapides
- **Que signifie « encrypt zip » ?** Cela signifie appliquer une protection basée sur un mot de passe (AES ou ZipCrypto) au contenu d’une archive ZIP/7z.  
- **Chaque entrée peut‑elle avoir un mot de passe différent ?** Oui — Aspose.Zip vous permet d’attribuer des mots de passe distincts par fichier.  
- **Quelles versions de .NET sont prises en charge ?** Toutes les versions modernes de .NET Framework, .NET Core et .NET 5/6.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour une utilisation en production ; un essai gratuit est disponible.  
- **Quel format de compression est utilisé dans l’exemple ?** L’exemple crée une archive 7z avec chiffrement AES‑256.

## Comment compresser des fichiers avec mot de passe en utilisant Aspose.Zip pour .NET
Dans cette section, nous répondons directement à la question principale et préparons le terrain pour le guide pas à pas qui suit.

## Qu’est‑ce que « how to encrypt zip » avec Aspose.Zip ?
Chiffrer un fichier ZIP (ou 7z) signifie sécuriser ses entrées afin qu’elles ne puissent pas être ouvertes sans le mot de passe correct. Aspose.Zip pour .NET prend en charge à la fois le ZipCrypto classique et le chiffrement AES plus robuste, et il vous permet de spécifier les paramètres de chiffrement par entrée, vous offrant ainsi un contrôle granulaire de la sécurité.

## Pourquoi utiliser des mots de passe différents pour chaque entrée ?
- **Segmentation de la sécurité :** Si un mot de passe est compromis, les autres fichiers restent protégés.  
- **Conformité réglementaire :** Certaines industries exigent des identifiants séparés pour différentes catégories de données.  
- **Accès spécifique à l’utilisateur :** Vous pouvez distribuer une archive unique à plusieurs utilisateurs, chacun ne débloquant que les fichiers auxquels il est autorisé.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Aspose.Zip for .NET** installé – consultez la [documentation officielle](https://reference.aspose.com/zip/net/) pour les instructions de téléchargement et d’installation.  
- Un dossier sur votre machine où vous conserverez les fichiers source (le « Document Directory »).  
- Une connaissance de base du C# et de Visual Studio (ou de votre IDE .NET préféré).

## Import Namespaces

Nous commençons par importer les espaces de noms contenant les classes nécessaires.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 1 : Définir votre répertoire de documents

Définissez le chemin qui contient les fichiers que vous souhaitez archiver.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Créer des entrées avec des mots de passe différents

Voici le cœur du tutoriel. Nous ouvrons un nouveau fichier 7z, créons trois objets `FileInfo`, et ajoutons chacun comme entrée avec son propre mot de passe AES.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Comment cela fonctionne

- `SevenZipArchive` est le conteneur d’une archive 7‑z.  
- `CreateEntry` prend le nom de l’entrée, le fichier source, un indicateur de remplacement, et un objet `SevenZipEntrySettings`.  
- Dans `SevenZipEntrySettings`, nous fournissons deux objets de paramètres : un pour la compression (`SevenZipStoreCompressionSettings`) et un pour le chiffrement (`SevenZipAESEncryptionSettings`).  
- Chaque appel fournit un **mot de passe différent** (`"test1"`, `"test2"`, `"test3"`), réalisant ainsi une protection par entrée.

## Étape 3 : Vérification

Après avoir enregistré l’archive, vous pouvez afficher un simple message de confirmation.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Exécutez le programme, puis essayez d’ouvrir `archive.7z` avec un outil comme 7‑Zip. Il vous demandera un mot de passe pour chaque entrée, confirmant que les mots de passe sont bien distincts.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Erreur de mot de passe incorrect** | La chaîne du mot de passe contient des espaces superflus ou des caractères invisibles. | Supprimez les espaces superflus (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Archive non ouvrable avec des outils anciens** | Certains outils ZIP hérités ne prennent pas en charge le chiffrement AES‑256 utilisé par 7z. | Utilisez un extracteur moderne (7‑Zip 19.00+). |
| **Fichier non ajouté à l’archive** | Le chemin du fichier source est incorrect ou le fichier n’existe pas. | Vérifiez `dataDir` et les noms de fichiers, ou utilisez `Path.Combine(dataDir, "data1.bin")`. |

## Questions fréquentes

### Q1 : Aspose.Zip pour .NET est‑il compatible avec toutes les versions de .NET ?

R1 : Oui, Aspose.Zip pour .NET est conçu pour s’intégrer de façon transparente à toutes les versions du framework .NET.

### Q2 : Puis‑je utiliser Aspose.Zip pour .NET dans mes projets commerciaux ?

R2 : Absolument ! Aspose.Zip pour .NET propose des licences commerciales, et vous pouvez obtenir plus d’informations sur l’achat [ici](https://purchase.aspose.com/buy).

### Q3 : Un essai gratuit est‑il disponible ?

R3 : Oui, vous pouvez explorer les fonctionnalités d’Aspose.Zip pour .NET avec un essai gratuit. Commencez [ici](https://releases.aspose.com/).

### Q4 : Comment obtenir du support pour Aspose.Zip pour .NET ?

R4 : Pour toute question ou assistance, rendez‑vous sur le [Forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

### Q5 : Puis‑je utiliser Aspose.Zip pour .NET sans licence permanente ?

R5 : Oui, vous pouvez obtenir une licence temporaire pour vos besoins à court terme. Plus de détails [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion

Vous venez d’apprendre **comment compresser des fichiers avec mot de passe** et chiffrer des archives ZIP avec des mots de passe par entrée en utilisant Aspose.Zip pour .NET. Cette technique vous offre la flexibilité de protéger chaque fichier individuellement, répondant à des exigences de sécurité plus strictes et simplifiant la distribution spécifique à chaque utilisateur. N’hésitez pas à expérimenter d’autres paramètres de compression, des ensembles de fichiers plus volumineux, ou à intégrer cette logique dans un service web qui génère des archives sécurisées à la volée.

---

**Dernière mise à jour :** 2026-02-28  
**Testé avec :** Aspose.Zip for .NET 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}