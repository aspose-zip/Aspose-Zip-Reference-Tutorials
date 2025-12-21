---
date: 2025-12-21
description: Apprenez à créer des fichiers zip protégés par mot de passe en .NET,
  à chiffrer des dossiers et à modifier le mot de passe du zip à l'aide d'Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Créer une archive zip protégée par mot de passe pour les répertoires .NET –
  Tutoriel Aspose.Zip
url: /fr/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une archive zip protégée par mot de passe pour les répertoires .NET – Tutoriel Aspose.Zip

Dans ce guide, vous allez **créer des archives zip protégées par mot de passe** pour des répertoires entiers à l’aide de la bibliothèque Aspose.Zip pour .NET. Que vous ayez besoin de **chiffrer un dossier**, de sécuriser des fichiers de sauvegarde, ou simplement de restreindre l’accès à des données sensibles, ce tutoriel pas à pas vous montre exactement comment le faire avec du code C# propre.

## Réponses rapides
- **Quelle bibliothèque est recommandée ?** Aspose.Zip pour .NET  
- **Puis‑je chiffrer un dossier complet ?** Oui – il suffit de pointer l’API vers le dossier que vous souhaitez zipper.  
- **La modification du mot de passe du zip est‑elle prise en charge ?** Absolument, utilisez `TraditionalEncryptionSettings`.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence valide Aspose.Zip est requise pour une utilisation commerciale.  
- **Fonctionne avec .NET Core/5/6 ?** Oui, l’API est entièrement compatible avec les runtimes .NET modernes.  

## Qu’est‑ce que « créer une archive zip protégée par mot de passe » ?
Créer une archive zip protégée par mot de passe signifie compresser des fichiers ou des répertoires dans une archive ZIP tout en appliquant un chiffrement afin que l’archive ne puisse être ouverte qu’avec le mot de passe correct. Cela protège le contenu contre tout accès non autorisé.

## Pourquoi utiliser Aspose.Zip pour protéger un répertoire .NET par mot de passe ?
Aspose.Zip offre une API simple et haute performance qui prend en charge **c# zip password protection**, le chiffrement traditionnel ZipCrypto ainsi que le chiffrement AES. Elle gère efficacement les grands répertoires et s’intègre parfaitement à tout projet .NET.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Des connaissances de base en programmation C#.  
- Visual Studio (toute version récente).  
- La bibliothèque Aspose.Zip pour .NET – téléchargez‑la **[ici](https://releases.aspose.com/zip/net/)**.  
- Un dossier sur le disque que vous souhaitez protéger par mot de passe.

## Importer les espaces de noms
Ajoutez les espaces de noms requis à votre fichier C# afin que le compilateur sache où trouver les classes Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Étape 1 : Définir le chemin du répertoire source
Déclarez le chemin qui pointe vers le répertoire que vous avez l’intention de zipper et de protéger.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Protéger le répertoire par mot de passe
Utilisez `TraditionalEncryptionSettings` pour spécifier le mot de passe et créer l’archive chiffrée. C’est le cœur de **c# zip password protection**.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Étape 3 : Explication du code
- **Création du fichier de sortie :** `File.Open(..., FileMode.Create)` ouvre (ou crée) le fichier ZIP qui contiendra les données chiffrées.  
- **Sélection du dossier source :** `new DirectoryInfo(".\\CanterburyCorpus")` indique à Aspose.Zip quel répertoire compresser.  
- **Application du mot de passe :** `new TraditionalEncryptionSettings("p@s$")` définit le mot de passe qui protégera l’archive.  
- **Ajout des entrées & sauvegarde :** `archive.CreateEntries(corpus)` ajoute chaque fichier du dossier, et `archive.Save(zipFile)` écrit le ZIP chiffré sur le disque.

## Comment changer le mot de passe du zip ultérieurement ?
Si vous devez **changer le mot de passe du zip**, recréez simplement l’archive avec une nouvelle instance de `TraditionalEncryptionSettings` contenant le nouveau mot de passe, puis enregistrez‑la à nouveau.

## Problèmes courants & astuces
- **Dossiers volumineux :** Aspose.Zip diffuse les données, de sorte que l’utilisation de la mémoire reste faible même pour d’énormes répertoires.  
- **Complexité du mot de passe :** Utilisez un mot de passe fort (mélange de lettres, chiffres, symboles) pour améliorer la sécurité.  
- **Erreurs de licence :** Assurez‑vous d’avoir appliqué un fichier de licence valide ; sinon la bibliothèque fonctionne en mode d’évaluation avec des limitations.

## Foire aux questions

### Aspose.Zip pour .NET convient‑il aux grands répertoires ?
Oui, Aspose.Zip pour .NET est conçu pour gérer efficacement de grands répertoires, offrant des performances optimales.

### Puis‑je modifier le mot de passe d’un répertoire déjà protégé ?
Oui, vous pouvez modifier le mot de passe en ajustant le `TraditionalEncryptionSettings` dans le code en conséquence.

### Y a‑t‑il des exigences de licence pour utiliser Aspose.Zip pour .NET ?
Oui, une licence valide est requise pour utiliser Aspose.Zip pour .NET dans un environnement de production. Vous pouvez obtenir une licence **[ici](https://purchase.aspose.com/buy)**.

### Existe‑t‑il un essai gratuit d’Aspose.Zip pour .NET ?
Oui, vous pouvez accéder à un essai gratuit **[ici](https://releases.aspose.com/)**.

### Où puis‑je trouver un support supplémentaire pour Aspose.Zip pour .NET ?
Vous pouvez visiter le **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** pour toute assistance ou question.

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.Zip pour .NET (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}