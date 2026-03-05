---
date: 2026-03-05
description: Apprenez à créer des fichiers 7z avec chiffrement AES dans .NET en utilisant
  Aspose.Zip pour un archivage sécurisé.
linktitle: Archive with Encrypted Entry
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment créer des fichiers 7z avec une archive sécurisée en .NET à l'aide d'Aspose.Zip
url: /fr/net/password-protection-and-encryption/archive-with-encrypted-entry/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer des fichiers 7z avec une archivage sécurisé en .NET à l'aide d'Aspose.Zip

## Introduction

Si vous devez **comment créer des 7z** archives qui sont à la fois compactes et protégées, vous êtes au bon endroit. Dans les applications .NET modernes, l'archivage sécurisé est essentiel pour protéger la propriété intellectuelle, se conformer aux réglementations de confidentialité des données et réduire les coûts de stockage. Aspose.Zip pour .NET vous fournit une API simple pour générer des archives **Seven Zip**, appliquer le **chiffrement AES**, et même **protéger par mot de passe les fichiers 7z** — le tout sans quitter le confort de C#.

Dans ce tutoriel, nous parcourrons le processus complet de création d'une archive 7z, de chiffrement d'une entrée zip, et d'enregistrement du résultat sur le disque. À la fin, vous comprendrez comment **comment chiffrer zip** fichiers, utiliser la **compression seven zip**, et intégrer l'archivage sécurisé dans n'importe quel projet .NET.

## Quick Answers
- **Quelle bibliothèque prend en charge la création de 7z ?** Aspose.Zip for .NET  
- **Puis-je chiffrer une seule entrée ?** Oui, en utilisant `SevenZipAESEncryptionSettings`  
- **La protection par mot de passe est‑elle disponible ?** Absolument – la clé AES agit comme le mot de passe  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Ai‑je besoin d'une licence pour la production ?** Une licence commerciale est requise pour une utilisation en production  

## What is a 7z Archive and Why Use AES Encryption?
Un fichier **7z** est un format d'archive à haute compression créé par l'utilitaire 7‑Zip. Il prend en charge des algorithmes avancés comme LZMA/LZMA2 et un chiffrement **AES‑256** robuste, ce qui le rend idéal pour les scénarios **secure archiving .net** où la taille et la confidentialité sont importantes.

## Why Choose Aspose.Zip for .NET?
- **API .NET native** – aucun exécutable externe ou interop natif requis.  
- **Contrôle total** sur les niveaux de compression, les paramètres de chiffrement et les flux d'entrées.  
- **Support multiplateforme** pour Windows, Linux et macOS.  
- **Documentation complète** et support communautaire actif.

## Prerequisites

Avant de commencer, assurez‑vous d'avoir :

- Un environnement de développement .NET (Visual Studio, VS Code ou Rider).  
- Aspose.Zip pour .NET installé – voir la documentation **[ici](https://reference.aspose.com/zip/net/)**.  
- La bibliothèque téléchargée depuis le **[lien de téléchargement](https://releases.aspose.com/zip/net/)**.  
- Familiarité de base avec C# et les entrées/sorties de fichiers.

## Import Namespaces

Dans votre projet C#, commencez par importer les espaces de noms requis :

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Step 1: Set the Resource Directory Path

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create a Seven Zip File with AES Encryption

```csharp
//ExStart: ArchiveWithEncryptedEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", 
            new MemoryStream(new byte[] { 0x00, 0xFF }), 
            new SevenZipEntrySettings(new SevenZipLZMACompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.Save(sevenZipFile);
    }
}
//ExEnd: ArchiveWithEncryptedEntry
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

**Explication :**  
Dans cette étape, nous ouvrons (ou créons) un fichier nommé **archive.7z**, ajoutons une seule entrée appelée **entry1.bin**, et appliquons le **chiffrement AES** avec le mot de passe `"test1"`. L'objet `SevenZipLZMACompressionSettings` contrôle l'algorithme de compression, tandis que `SevenZipAESEncryptionSettings` gère le chiffrement. Vous pouvez répéter l'appel `CreateEntry` pour ajouter d'autres fichiers, chacun avec sa propre configuration de chiffrement si nécessaire.

### How to encrypt zip entry individually
Si vous devez **encrypt zip entry** des objets avec des mots de passe différents, il suffit d'instancier un nouveau `SevenZipAESEncryptionSettings` pour chaque appel à `CreateEntry`.

### How to password protect 7z files
Le mot de passe que vous fournissez dans `SevenZipAESEncryptionSettings` agit comme la **password protection** pour l'ensemble de l'archive. Lors de l'ouverture de l'archive, le même mot de passe doit être fourni.

## Common Issues and Troubleshooting

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| “Erreur « Mot de passe invalide » lors de l'ouverture de l'archive” | Incompatibilité du mot de passe ou absence de `SevenZipAESEncryptionSettings` | Vérifiez que la chaîne du mot de passe correspond exactement (sensible à la casse). |
| Taille de l'archive supérieure à la normale | Utilisation du niveau de compression par défaut | Ajustez `SevenZipLZMACompressionSettings` (par ex., définissez `CompressionLevel = CompressionLevel.High`). |
| Exception d'exécution sur un OS non Windows | Dépendances natives manquantes | Assurez‑vous d'utiliser la dernière version d'Aspose.Zip qui inclut les bibliothèques natives requises. |

## Conclusion

Vous avez maintenant appris **comment créer des 7z** archives avec chiffrement AES en utilisant Aspose.Zip pour .NET. Cette technique vous permet de créer des solutions **secure archiving .net** qui protègent les données sensibles tout en maintenant des tailles de fichiers minimales. N'hésitez pas à explorer des paramètres supplémentaires — tels que des niveaux de compression personnalisés ou l'archivage multithread — pour affiner les performances selon votre scénario spécifique.

## FAQs

### Puis‑je utiliser Aspose.Zip pour .NET dans mes projets non commerciaux ?
Oui, Aspose.Zip pour .NET peut être utilisé à la fois dans des projets commerciaux et non commerciaux.

### Comment obtenir une licence temporaire pour Aspose.Zip pour .NET ?
Obtenez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

### Existe‑t‑il un support communautaire disponible pour Aspose.Zip pour .NET ?
Oui, visitez le **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** pour le support communautaire.

### D’autres algorithmes de compression sont‑ils supportés en plus de LZMA ?
Aspose.Zip pour .NET prend en charge plusieurs algorithmes, dont LZMA, LZMA2, BZIP2 et PPMd. Consultez la documentation pour tous les détails.

### Puis‑je personnaliser davantage les paramètres de chiffrement ?
Absolument ! Explorez la documentation pour des options de chiffrement avancées telles que des longueurs de clé personnalisées et des nombres d’itérations.

## Frequently Asked Questions

**Q : Comment ajouter plusieurs entrées chiffrées à la même archive 7z ?**  
R : Appelez `archive.CreateEntry` de façon répétée, en fournissant un `SevenZipAESEncryptionSettings` distinct pour chaque entrée si vous avez besoin de mots de passe différents.

**Q : Aspose.Zip prend‑il en charge le streaming de gros fichiers sans les charger entièrement en mémoire ?**  
R : Oui, vous pouvez passer un `FileStream` ou tout autre flux à `CreateEntry`, ce qui vous permet de travailler avec de gros fichiers de manière efficace.

**Q : Puis‑je déchiffrer une archive 7z existante avec Aspose.Zip ?**  
R : Utilisez le constructeur `SevenZipArchive` qui accepte un flux et fournissez le mot de passe correct via `SevenZipAESEncryptionSettings`.

**Q : Est‑il possible de définir un niveau de compression pour chaque entrée individuellement ?**  
R : Oui, configurez `SevenZipLZMACompressionSettings` par entrée avant d’appeler `CreateEntry`.

**Q : Quels runtimes .NET sont officiellement testés avec Aspose.Zip ?**  
R : .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 et les versions ultérieures.

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}