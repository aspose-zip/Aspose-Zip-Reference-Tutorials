---
date: 2026-03-02
description: Apprenez à créer une archive zip protégée par un mot de passe et à compresser
  des fichiers avec des mots de passe en .NET en utilisant Aspose.Zip. Suivez notre
  guide étape par étape.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Créer une archive ZIP protégée par mot de passe en .NET avec Aspose.Zip
url: /fr/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une archive ZIP protégée par mot de passe en .NET avec Aspose.Zip

## Introduction

Lorsque vous devez partager des données sensibles, une **archive zip protégée par mot de passe** est l'une des méthodes les plus simples et les plus efficaces pour garder les informations en sécurité. Dans les applications .NET, Aspose.Zip facilite la **compression de fichiers avec des mots de passe**, en attribuant à chaque fichier sa propre clé de chiffrement. Dans ce tutoriel, vous apprendrez exactement comment créer une telle archive, pourquoi c'est important et où vous pouvez l'appliquer dans des projets réels.

## Réponses rapides
- **Quelle bibliothèque dois-je utiliser ?** Aspose.Zip for .NET fournit un support intégré pour les mots de passe par fichier et plusieurs méthodes de chiffrement.  
- **Combien de lignes de code ?** Environ 30 lignes, incluant la configuration et l'enregistrement de l'archive.  
- **Chaque fichier peut-il avoir un mot de passe différent ?** Oui – vous pouvez attribuer un mot de passe unique à chaque entrée.  
- **Quelles méthodes de chiffrement sont disponibles ?** ZipCrypto traditionnel, AES‑128 et AES‑256.  
- **Ai‑je besoin d'une licence pour la production ?** Une licence commerciale est requise pour une utilisation en production ; un essai gratuit est disponible.

## Qu'est‑ce qu'une archive zip protégée par mot de passe ?
Une archive zip protégée par mot de passe est un fichier compressé (ZIP) qui nécessite un mot de passe pour extraire son contenu. Le mot de passe peut protéger l'ensemble de l'archive ou des entrées individuelles, et les algorithmes modernes comme AES‑128/256 offrent un chiffrement fort.

## Pourquoi compresser des fichiers avec des mots de passe en utilisant Aspose.Zip ?
- **Sécurité granulaire** – attribuez un mot de passe distinct par fichier, idéal pour les scénarios multi‑locataires.  
- **Normes de chiffrement multiples** – choisissez entre le ZipCrypto hérité et le AES fort.  
- **Pas d'outils externes** – tout est géré programmatiquement dans votre base de code .NET.  
- **Performance** – compression rapide avec Deflate tout en maintenant une petite taille d'archive.

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

- **Aspose.Zip for .NET** – installez la bibliothèque dans votre projet. La documentation détaillée est disponible [here](https://reference.aspose.com/zip/net/).  
- **Téléchargez le dernier package** si ce n'est pas déjà fait, depuis [this link](https://releases.aspose.com/zip/net/).  
- Un dossier contenant les fichiers que vous souhaitez compresser.

## Importer les espaces de noms

Ajoutez les espaces de noms requis en haut de votre fichier C# :

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Étape 1 : Définir le chemin du répertoire de ressources

Pointez le code vers le dossier qui contient les fichiers source :

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Compresser les fichiers avec des mots de passe individuels

Nous allons maintenant créer une **archive zip protégée par mot de passe** où chaque fichier utilise son propre mot de passe et sa méthode de chiffrement. L'exemple utilise trois fichiers d'exemple (`alice29.txt`, `asyoulik.txt` et `fields.c`) avec des mots de passe différents.

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
- **CreateEntry** ajoute un fichier à l'archive.  
- Le quatrième argument (`ArchiveEntrySettings`) vous permet de spécifier à la fois la compression (`DeflateCompressionSettings`) et le chiffrement (`TraditionalEncryptionSettings` ou `AesEcryptionSettings`).  
- En passant une chaîne de mot de passe différente pour chaque entrée, vous obtenez une **archive zip protégée par mot de passe** où chaque fichier ne peut être déverrouillé qu'avec sa propre clé.

## Problèmes courants & dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| L'extraction échoue avec « Mot de passe incorrect » | Mauvaise correspondance du mot de passe ou mauvaise méthode de chiffrement | Vérifiez la chaîne de mot de passe exacte et assurez‑vous d'avoir utilisé la même `EncryptionMethod` lors de l'extraction. |
| La taille de l'archive est plus grande que prévu | L'utilisation d'AES‑256 sur de petits fichiers texte peut ajouter du surcoût | Pour les petits fichiers, AES‑128 peut être suffisant et produire une archive plus petite. |
| Exception d'exécution sur `archive.Save` | Permission d'écriture manquante sur le dossier cible | Assurez‑vous que l'application a les droits d'écriture sur `dataDir` ou utilisez un autre chemin de sortie. |

## Questions fréquemment posées (FAQ)

### Puis‑je utiliser différentes méthodes de chiffrement pour chaque fichier ?
Oui, Aspose.Zip for .NET vous permet de mélanger les méthodes de chiffrement — ZipCrypto traditionnel, AES‑128 et AES‑256 — sur une base par fichier.

### Une version d'essai est‑elle disponible ?
Oui, vous pouvez accéder à la version d'essai gratuite d'Aspose.Zip for .NET [here](https://releases.aspose.com/).

### Comment obtenir de l'aide si je rencontre des problèmes ?
Visitez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour obtenir de l'aide de la communauté et du support Aspose.

### Où trouver la documentation détaillée d'Aspose.Zip for .NET ?
La documentation est disponible [here](https://reference.aspose.com/zip/net/).

### Puis‑je acheter une licence temporaire à des fins de test ?
Oui, vous pouvez obtenir une licence temporaire [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-02  
**Testé avec :** Aspose.Zip for .NET (latest release)  
**Auteur :** Aspose  

---