---
date: 2026-06-09
description: Apprenez comment ajouter un mot de passe à un zip et créer des archives
  zip LZMA en utilisant Aspose.Zip pour .NET. Ce tutoriel couvre Bzip2, LZMA (taille
  du dictionnaire), PPMd, Enhanced Deflate, la compression Store, et la compression
  de fichiers ASP.NET de gros fichiers.
keywords:
- add password to zip
- LZMA compression .NET
- Aspose.Zip encryption
linktitle: Optimisation des paramètres de compression
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  headline: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to add password to zip and create LZMA zip archives using
    Aspose.Zip for .NET. This tutorial covers Bzip2, LZMA (dictionary size), PPMd,
    Enhanced Deflate, Store compression, and ASP.NET file compression of large files.
  name: Add password to zip and create LZMA archive with Aspose.Zip for .NET
  steps:
  - name: Initialize Bzip2 Compression with Traditional Encryption
    text: '`Bzip2CompressionSettings` configures the Bzip2 algorithm (block size,
      etc.). `TraditionalEncryptionSettings` applies legacy ZipCrypto encryption to
      an entry. *Password protection is applied via `TraditionalEncryptionSettings`
      passed directly to `ArchiveEntrySettings`.*'
  - name: Initialize LZMA Compression with AES256 Encryption
    text: '`LzmaCompressionSettings` controls LZMA‑specific parameters such as dictionary
      size and fast bytes. `AesEncryptionSettings` provides AES‑256 encryption for
      the archive entries. **Direct answer (40‑70 words):** Instantiate `LzmaCompressionSettings`
      with a chosen `DictionarySize`, create an `AesEncryp'
  - name: Initialize PPMd Compression with AES256 Encryption
    text: '`PpmdCompressionSettings` defines the order and memory usage for the PPMd
      algorithm. `AesEncryptionSettings` provides AES‑256 encryption for the archive
      entries. **Direct answer (40‑70 words):** Create a `PpmdCompressionSettings`
      instance, combine it with an `AesEncryptionSettings` object containing'
  - name: Initialize Enhanced Deflate Compression with AES256 Encryption
    text: '`EnhancedDeflateCompressionSettings` lets you specify a compression level
      that balances speed and size. `AesEncryptionSettings` provides AES‑256 encryption
      for the archive entries. **Direct answer (40‑70 words):** Instantiate `EnhancedDeflateCompressionSettings`
      with your desired level (0‑9), pair i'
  - name: Initialize Store Compression with Traditional Encryption
    text: '`StoreCompressionSettings` tells Aspose.Zip to skip compression entirely,
      preserving the source file byte‑for‑byte. `TraditionalEncryptionSettings` applies
      legacy ZipCrypto encryption. **Direct answer (40‑70 words):** Create a `StoreCompressionSettings`
      instance (which performs no compression), comb'
  type: HowTo
- questions:
  - answer: Aspose.Zip is designed to work with its built‑in algorithms. Integrating
      third‑party libraries is possible but requires custom handling outside the Aspose
      API.
    question: Can I use Aspose.Zip for .NET with other compression libraries?
  - answer: Pass either `TraditionalEncryptionSettings` or `AesEncryptionSettings`
      as the second argument to `ArchiveEntrySettings` when constructing the `Archive`.
      See the [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/)
      for full examples.
    question: How can I add password protection to a zip created with Aspose.Zip?
  - answer: Yes, you can access the trial version [here](https://releases.aspose.com/).
    question: Is there a trial version I can test?
  - answer: For support and community discussions, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: Where can I get community help or ask questions?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Ajouter un mot de passe à un zip et créer une archive LZMA avec Aspose.Zip
  pour .NET
url: /fr/net/file-compression/optimizing-compression-settings/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un mot de passe à un zip et créer une archive LZMA avec Aspose.Zip pour .NET

Dans les applications .NET modernes, **add password to zip** lors de la création d’une archive zip LZMA à haut taux de compression peut protéger les données sensibles tout en offrant la meilleure compression possible. Que vous construisiez un service de compression de fichiers ASP.NET, un utilitaire de bureau qui gère des fichiers de plusieurs gigaoctets, ou un flux de travail basé sur le cloud, ce tutoriel vous guide à travers les étapes exactes pour sécuriser et compresser vos fichiers avec Aspose.Zip pour .NET.

## Réponses rapides
- **Quel est le principal avantage de la compression LZMA ?** Le meilleur taux de compression avec une vitesse raisonnable pour la plupart des types de fichiers.  
- **Quelle méthode stocke les fichiers sans compression ?** Compression de stockage (également appelée « store compression zip »).  
- **Puis-je utiliser ces paramètres dans une application ASP.NET ?** Oui — il suffit de référencer Aspose.Zip dans votre projet et d’appeler la même API.  
- **Ai-je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, et .NET 5–10.

## Qu’est‑ce que « add password to zip » dans Aspose.Zip ?
**L’ajout d’un mot de passe zip chiffre chaque entrée à l’intérieur d’une archive ZIP afin que seuls les utilisateurs connaissant le mot de passe puissent extraire les fichiers.** Aspose.Zip prend en charge à la fois le chiffrement traditionnel ZipCrypto et le chiffrement AES (128, 192 ou 256 bits). Les paramètres de chiffrement sont fournis comme deuxième argument à `ArchiveEntrySettings` lors de la construction d’un `Archive` ; il n’existe pas de méthode séparée `SetPassword`.

## Pourquoi utiliser Aspose.Zip pour la compression de fichiers .NET ?
Aspose.Zip fournit une API unique et cohérente qui couvre de nombreux algorithmes tout en offrant des performances élevées et une faible consommation de mémoire. Elle permet aux développeurs de choisir la meilleure méthode de compression pour chaque scénario et d’appliquer le chiffrement en une seule étape, simplifiant le code et réduisant la charge de maintenance.

- **API unifiée** – Une interface cohérente pour Bzip2, LZMA, PPMd, Enhanced Deflate et Store.  
- **Optimisée pour la performance** – L’implémentation native optimisée traite **jusqu’à des fichiers de 10 Go** sans charger le fichier complet en mémoire.  
- **Compatibilité ASP.NET** – Fonctionne de manière transparente dans les projets web, les services en arrière‑plan et les Azure Functions.  
- **Contrôle fin** – Ajustez la taille du dictionnaire, le niveau de compression et le chiffrement avec un seul appel au constructeur.  
- **Prise en charge de plus de 10 algorithmes de compression** – couvrant les cas d’utilisation les plus courants dans les pipelines de données d’entreprise.

## Prérequis
- **Bibliothèque Aspose.Zip pour .NET** – Téléchargez et installez depuis la [documentation Aspose](https://reference.aspose.com/zip/net/).  
- **Fichier texte d’exemple** – Préparez un fichier d’exemple (par ex., `sample.txt`) que vous allez compresser.  
- **Environnement de développement .NET** – Visual Studio 2022 ou tout IDE compatible.  

## Importer les espaces de noms

Les classes `Archive`, `ArchiveEntrySettings` et les classes de chiffrement se trouvent dans l’espace de noms `Aspose.Zip`. Importez‑les en haut de votre fichier :

- `Archive` représente un conteneur d’archive ZIP.  
- `ArchiveEntrySettings` contient les options de compression et de chiffrement pour chaque entrée.  
- Les classes de chiffrement (par ex., `AesEncryptionSettings`) définissent la façon dont les données sont chiffrées.

```csharp
using Aspose.Zip;
using Aspose.Zip.Compression;
using Aspose.Zip.Encryption;
using System.IO;
```

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Explorons maintenant chaque paramètre de compression et voyons comment **add password to zip** le cas échéant.

## Utiliser les paramètres de compression Bzip2

### Étape 1 : Initialiser la compression Bzip2 avec le chiffrement traditionnel

`Bzip2CompressionSettings` configure l’algorithme Bzip2 (taille de bloc, etc.). `TraditionalEncryptionSettings` applique le chiffrement ZipCrypto hérité à une entrée.

```csharp
var bzip2Settings = new Bzip2CompressionSettings();
var encryption = new TraditionalEncryptionSettings("MySecretPwd");
var entrySettings = new ArchiveEntrySettings(bzip2Settings, encryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "Bzip2Compression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new Bzip2CompressionSettings(),
            new TraditionalEncryptionSettings("MySecret123"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

*La protection par mot de passe est appliquée via `TraditionalEncryptionSettings` passé directement à `ArchiveEntrySettings`.*

## Comment ajouter un mot de passe à un zip avec Aspose.Zip pour .NET

Chargez votre fichier source, créez un `Archive` avec les paramètres d’entrée, et ajoutez le fichier à l’archive. Le chiffrement est appliqué automatiquement car il a été fourni lors de la création de l’instance `ArchiveEntrySettings`.

**Réponse directe (40‑70 mots) :**  
Créez un objet `ArchiveEntrySettings` qui inclut à la fois les paramètres de compression souhaités et soit `TraditionalEncryptionSettings` soit `AesEncryptionSettings`. Puis passez cet objet au constructeur `Archive` et ajoutez les fichiers avec `AddEntry`. L’archive est écrite avec le mot de passe déjà intégré, aucune étape supplémentaire n’est requise après la création.

`ArchiveEntrySettings` est le conteneur de configuration qui indique à Aspose.Zip comment chaque entrée doit être compressée et chiffrée.  

```csharp
var archivePath = Path.Combine(dataDir, "bzip2_protected.zip");
using (var archive = new Archive(archivePath, entrySettings))
{
    archive.AddEntry("sample.txt", File.OpenRead(Path.Combine(dataDir, "sample.txt")));
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "LZMACompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new LzmaCompressionSettings(),
            new AesEcryptionSettings("StrongPwd!2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Comment créer une archive zip LZMA avec Aspose.Zip

### Étape 1 : Initialiser la compression LZMA avec le chiffrement AES256

`LzmaCompressionSettings` contrôle les paramètres spécifiques à LZMA tels que la taille du dictionnaire et les octets rapides. `AesEncryptionSettings` fournit le chiffrement AES‑256 pour les entrées de l’archive.

**Réponse directe (40‑70 mots) :**  
Instanciez `LzmaCompressionSettings` avec un `DictionarySize` choisi, créez un objet `AesEncryptionSettings` avec votre mot de passe et `EncryptionMethod.AES256`, puis construisez un `ArchiveEntrySettings` à partir des deux. Passez‑le au constructeur `Archive` et ajoutez vos fichiers ; le zip résultant sera compressé en LZMA et protégé par AES en une seule opération.

`LzmaCompressionSettings` est la classe qui contrôle les paramètres spécifiques à LZMA tels que la taille du dictionnaire et les octets rapides.  

```csharp
var lzmaSettings = new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 };
var aesEncryption = new AesEncryptionSettings("StrongPwd123", EncryptionMethod.AES256);
var lzmaEntrySettings = new ArchiveEntrySettings(lzmaSettings, aesEncryption);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "PPMdCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new PPMdCompressionSettings(),
            new AesEcryptionSettings("PPMdPwd#2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

> **Astuce :** LZMA offre une **taille de dictionnaire LZMA** configurable qui influence à la fois le taux de compression et l’utilisation de la mémoire. Vous pouvez la définir via `new LzmaCompressionSettings { DictionarySize = 8 * 1024 * 1024 }` si vous devez affiner pour des fichiers très volumineux.

## Utiliser les paramètres de compression PPMd

### Étape 1 : Initialiser la compression PPMd avec le chiffrement AES256

`PpmdCompressionSettings` définit l’ordre et l’utilisation de la mémoire pour l’algorithme PPMd. `AesEncryptionSettings` fournit le chiffrement AES‑256 pour les entrées de l’archive.

**Réponse directe (40‑70 mots) :**  
Créez une instance `PpmdCompressionSettings`, combinez‑la avec un objet `AesEncryptionSettings` contenant votre mot de passe, et transmettez les deux à `ArchiveEntrySettings`. Utilisez cet objet de paramètres lors de la construction du `Archive ; le zip résultant sera compressé en PPMd et protégé par mot de passe sans appels supplémentaires.

`PpmdCompressionSettings` définit l’ordre et l’utilisation de la mémoire pour l’algorithme PPMd.  

```csharp
var ppmdSettings = new PpmdCompressionSettings { Order = 4 };
var aes = new AesEncryptionSettings("MyPwd!", EncryptionMethod.AES256);
var ppmdEntrySettings = new ArchiveEntrySettings(ppmdSettings, aes);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "EnhancedDeflateCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new EnhancedDeflateCompressionSettings(),
            new AesEcryptionSettings("DeflatePwd2026", EncryptionMethod.AES256))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Utiliser les paramètres de compression Enhanced Deflate

### Étape 1 : Initialiser la compression Enhanced Deflate avec le chiffrement AES256

`EnhancedDeflateCompressionSettings` vous permet de spécifier un niveau de compression qui équilibre vitesse et taille. `AesEncryptionSettings` fournit le chiffrement AES‑256 pour les entrées de l’archive.

**Réponse directe (40‑70 mots) :**  
Instanciez `EnhancedDeflateCompressionSettings` avec le niveau souhaité (0‑9), associez‑le à `AesEncryptionSettings` et enveloppez‑les dans `ArchiveEntrySettings`. Passez cet objet au constructeur `Archive` et ajoutez les fichiers ; l’archive sera créée avec la compression Enhanced Deflate et la protection par mot de passe AES‑256 en une seule passe.

`EnhancedDeflateCompressionSettings` vous permet de spécifier un niveau de compression qui équilibre vitesse et taille.  

```csharp
var edSettings = new EnhancedDeflateCompressionSettings { CompressionLevel = 9 };
var aesEnc = new AesEncryptionSettings("Pwd2026!", EncryptionMethod.AES256);
var edEntrySettings = new ArchiveEntrySettings(edSettings, aesEnc);
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreCompression_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "sample.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(
            new StoreCompressionSettings(),
            new TraditionalEncryptionSettings("StorePwd2026"))))
        {
            // Step 2: Create Entry
            archive.CreateEntry("sample.txt", source1);

            // Step 3: Save Archive
            archive.Save(zipFile);
        }
    }
}
```

## Utiliser les paramètres de compression Store (store compression zip)

### Étape 1 : Initialiser la compression Store avec le chiffrement traditionnel

`StoreCompressionSettings` indique à Aspose.Zip de ne pas compresser du tout, préservant le fichier source octet par octet. `TraditionalEncryptionSettings` applique le chiffrement ZipCrypto hérité.

**Réponse directe (40‑70 mots) :**  
Créez une instance `StoreCompressionSettings` (qui ne réalise aucune compression), combinez‑la avec `TraditionalEncryptionSettings` contenant votre mot de passe, et enveloppez les deux dans `ArchiveEntrySettings`. Passez cet objet au constructeur `Archive ; le zip résultant contiendra le fichier original non compressé mais protégé par mot de passe.

`StoreCompressionSettings` indique à Aspose.Zip de ne pas compresser du tout, préservant le fichier source octet par octet.  

```csharp
var storeSettings = new StoreCompressionSettings();
var tradEnc = new TraditionalEncryptionSettings("SimplePwd");
var storeEntrySettings = new ArchiveEntrySettings(storeSettings, tradEnc);
```

> **Astuce pro :** Ajustez la variable `dataDir` pour qu’elle pointe vers votre répertoire de travail réel, et réutilisez la même instance `Archive` si vous devez ajouter plusieurs fichiers à une seule archive.

## Problèmes courants et solutions
- **Erreurs « File not found »** – Vérifiez que `dataDir` se termine par un séparateur de chemin (`\` ou `/`) et que `sample.txt` existe.  
- **Consommation de mémoire avec de gros fichiers** – Utilisez `ArchiveEntrySettings` pour activer le mode streaming, qui écrit les données directement dans le flux de sortie.  
- **Niveau de compression incompatible** – Certains algorithmes (par ex., LZMA) exposent des propriétés supplémentaires comme `DictionarySize`. Consultez la documentation API si vous avez besoin d’un contrôle plus fin.  
- **Mot de passe non appliqué** – Assurez‑vous que l’objet de paramètres de chiffrement est passé comme deuxième argument à `ArchiveEntrySettings` lors de la construction, et non après la création de l’archive.  

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Zip pour .NET avec d’autres bibliothèques de compression ?**  
R : Aspose.Zip est conçu pour fonctionner avec ses algorithmes intégrés. L’intégration de bibliothèques tierces est possible mais nécessite une gestion personnalisée en dehors de l’API Aspose.

**Q : Comment ajouter une protection par mot de passe à un zip créé avec Aspose.Zip ?**  
R : Passez soit `TraditionalEncryptionSettings` soit `AesEncryptionSettings` comme deuxième argument à `ArchiveEntrySettings` lors de la construction du `Archive`. Consultez la [documentation](https://docs.aspose.com/zip/net/password-protecting-archives/) pour des exemples complets.

**Q : Existe‑t‑il une version d’essai que je peux tester ?**  
R : Oui, vous pouvez accéder à la version d’essai [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir de l’aide communautaire ou poser des questions ?**  
R : Pour le support et les discussions communautaires, visitez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37).

**Q : Puis‑je obtenir une licence temporaire pour évaluation ?**  
R : Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Comment cela aide‑t‑il à la compression de fichiers ASP.NET ?**  
R : En appelant la même API depuis un contrôleur ou un middleware ASP.NET, vous pouvez compresser les fichiers à la volée avant de les envoyer au client, réduisant la bande passante et améliorant les performances perçues.

**Q : Quelle est la meilleure façon de compresser efficacement de gros fichiers ?**  
R : Combinez le mode streaming avec la compression LZMA et un `DictionarySize` approprié. Cela équilibre l’utilisation de la mémoire et le taux de compression pour les ensembles de données massifs.

---

**Dernière mise à jour :** 2026-06-09  
**Testé avec :** Aspose.Zip 24.11 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Aspose.Zip pour .NET - Protéger par mot de passe une archive Zip & stocker plusieurs fichiers sans compression](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Créer un zip protégé par mot de passe pour les répertoires .NET – Tutoriel Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-directory/)
- [zip plusieurs fichiers c# – Compression sans effort avec Aspose.Zip pour .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}