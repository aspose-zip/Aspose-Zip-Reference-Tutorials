---
date: 2025-12-20
description: Apprenez à créer des archives zip protégées par mot de passe en .NET
  avec Aspose.Zip. Ce guide étape par étape montre comment compresser des fichiers
  avec des mots de passe, définir le mot de passe d’une entrée zip et utiliser le
  chiffrement AES.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Créer des fichiers ZIP protégés par mot de passe en .NET avec Aspose.Zip
url: /fr/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer des fichiers ZIP protégés par mot de passe en .NET avec Aspose.Zip

## Introduction

Si vous devez **créer des archives zip protégées par mot de passe** dans une application .NET, Aspose.Zip rend cela simple. En attribuant un mot de passe unique à chaque entrée, vous pouvez garder les documents sensibles en sécurité tout en profitant de la commodité de la compression ZIP. Dans ce tutoriel, vous apprendrez comment compresser des fichiers avec des mots de passe individuels, choisir différentes méthodes de chiffrement et définir un mot de passe d’entrée zip — le tout avec du code clair, prêt pour la production.

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Zip pour .NET.  
- **Puis‑je attribuer un mot de passe différent par fichier ?** Oui, chaque entrée peut avoir son propre mot de passe.  
- **Quels algorithmes de chiffrement sont pris en charge ?** ZipCrypto traditionnel, AES‑128 et AES‑256.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai gratuite suffit pour les tests ; une licence commerciale est requise en production.  
- **Est‑ce compatible avec .NET 6+ ?** Absolument – l’API cible .NET Standard 2.0 et versions ultérieures.

## Qu’est‑ce que « create password protected zip » ?
Créer un zip protégé par mot de passe signifie ajouter du chiffrement à une ou plusieurs entrées d’une archive ZIP afin que le contenu ne puisse pas être ouvert sans le mot de passe correct. C’est idéal pour transmettre des fichiers confidentiels, stocker des sauvegardes ou se conformer aux politiques de protection des données.

## Pourquoi utiliser Aspose.Zip pour les archives protégées par mot de passe ?
- **Contrôle fin** – définir un mot de passe distinct par fichier.  
- **Multiples options de chiffrement** – du legacy ZipCrypto à l’AES‑128/256 robuste.  
- **Aucune dépendance externe** – bibliothèque pure .NET, facile à intégrer.  
- **Documentation complète** – inclut un **aspose zip tutorial** pour des scénarios plus avancés.

## Prérequis

Avant de commencer le tutoriel, assurez‑vous de disposer des prérequis suivants :

- Aspose.Zip pour .NET : assurez‑vous que la bibliothèque Aspose.Zip est installée dans votre projet .NET. Vous pouvez consulter la documentation nécessaire [ici](https://reference.aspose.com/zip/net/).

- Téléchargement : si ce n’est pas déjà fait, téléchargez la bibliothèque Aspose.Zip pour .NET depuis [ce lien](https://releases.aspose.com/zip/net/).

- Répertoire de documents : préparez un répertoire contenant les fichiers que vous souhaitez compresser.

## Importer les espaces de noms

Dans votre projet .NET, importez les espaces de noms nécessaires :

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Étape 1 : Définir le chemin du répertoire de ressources

Déclarez le chemin vers le répertoire de ressources où se trouvent vos fichiers source.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Compresser les fichiers avec des mots de passe individuels

Compressez maintenant les fichiers avec des mots de passe individuels. Nous utiliserons trois fichiers d’exemple (`alice29.txt`, `asyoulik.txt` et `fields.c`) avec des mots de passe distincts pour chacun. Cela montre comment **compresser des fichiers avec des mots de passe** et aussi comment **définir le mot de passe d’une entrée zip** en utilisant différents schémas de chiffrement, y compris un **zip archive with aes**.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Comment cela fonctionne
- **TraditionalEncryptionSettings** utilise l’algorithme plus ancien ZipCrypto (compatible avec la plupart des utilitaires ZIP).  
- **AesEcryptionSettings** vous permet de choisir AES‑128 ou AES‑256 pour une sécurité renforcée.  
- Chaque appel `CreateEntry` reçoit un objet `ArchiveEntrySettings` où nous spécifions à la fois la méthode de compression et les paramètres de chiffrement, protégeant ainsi les entrées de l’**archive zip** par mot de passe.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| “Invalid password” lors de l’ouverture du ZIP | Incohérence entre le mot de passe utilisé dans le code et celui saisi dans l’extracteur | Vérifiez la chaîne exacte passée à `TraditionalEncryptionSettings` ou `AesEcryptionSettings`. |
| Les anciens outils d’extraction ne peuvent pas ouvrir les entrées AES‑chiffrées | Tous les utilitaires ZIP ne supportent pas le chiffrement AES | Utilisez la méthode ZipCrypto traditionnelle pour une compatibilité maximale, ou conseillez aux utilisateurs d’utiliser un outil moderne (par ex., 7‑Zip). |
| Les gros fichiers provoquent `OutOfMemoryException` | Chargement de fichiers volumineux en mémoire avant la compression | Diffusez le fichier directement avec `FileStream` sans le charger entièrement dans un objet `FileInfo`. |

## Questions fréquentes (FAQ)

### Puis‑je utiliser différentes méthodes de chiffrement pour chaque fichier ?
Oui, Aspose.Zip pour .NET vous permet d’utiliser différentes méthodes de chiffrement pour chaque fichier lors de la compression.

### Existe‑t‑il une version d’essai disponible ?
Oui, vous pouvez accéder à la version d’essai gratuite d’Aspose.Zip pour .NET [ici](https://releases.aspose.com/).

### Comment obtenir de l’aide en cas de problème ?
Visitez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour obtenir de l’assistance de la communauté et du support Aspose.

### Où trouver la documentation détaillée d’Aspose.Zip pour .NET ?
La documentation est disponible [ici](https://reference.aspose.com/zip/net/).

### Puis‑je acheter une licence temporaire pour les tests ?
Oui, vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

## FAQ rapide supplémentaire

**Q : La bibliothèque prend‑elle en charge .NET Core et .NET 5/6 ?**  
R : Oui, Aspose.Zip cible .NET Standard, ce qui le rend compatible avec .NET Framework, .NET Core et .NET 5/6.

**Q : Puis‑je ajouter un commentaire à chaque entrée ZIP ?**  
R : Bien qu’Aspose.Zip se concentre sur la compression et le chiffrement, vous pouvez stocker des métadonnées dans un fichier manifeste séparé à l’intérieur de l’archive.

**Q : Est‑il possible de chiffrer l’ensemble de l’archive avec un seul mot de passe ?**  
R : Vous pouvez définir un mot de passe sur chaque entrée individuellement (comme montré) ou appliquer le même mot de passe à toutes les entrées pour une approche plus simple de “zip archive with aes”.

## Conclusion

Vous avez maintenant maîtrisé la création de **fichiers zip protégés par mot de passe** en .NET avec Aspose.Zip. En attribuant des mots de passe individuels et en choisissant la méthode de chiffrement appropriée, vous pouvez sécuriser vos données sans sacrifier la commodité de la compression ZIP. Explorez d’autres fonctionnalités d’Aspose.Zip telles que le streaming de gros fichiers, l’ajout de métadonnées personnalisées et l’intégration avec le stockage cloud pour des scénarios encore plus puissants.

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.Zip pour .NET 23.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}