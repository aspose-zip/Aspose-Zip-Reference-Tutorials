---
date: 2026-03-08
description: Apprenez à créer des fichiers zip protégés par mot de passe, à protéger
  un dossier zip par mot de passe et à modifier le mot de passe d’un zip en utilisant
  Aspose.Zip pour .NET.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Créer un zip protégé par mot de passe pour les répertoires .NET – Tutoriel
  Aspose.Zip
url: /fr/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une archive zip protégée par mot de passe pour les répertoires .NET – Tutoriel Aspose.Zip

Dans ce guide, vous allez **créer des archives zip protégées par mot de passe** pour des répertoires entiers en utilisant la bibliothèque Aspose.Zip pour .NET. Que vous ayez besoin de **chiffrer un dossier**, de sécuriser des fichiers de sauvegarde, ou simplement de restreindre l'accès à des données sensibles, ce tutoriel étape par étape vous montre exactement comment le faire avec du code C# propre.

## Réponses rapides
- **Quelle bibliothèque est recommandée ?** Aspose.Zip for .NET  
- **Puis-je chiffrer un dossier entier ?** Oui – il suffit de pointer l'API vers le dossier que vous souhaitez zipper.  
- **Le changement du mot de passe du zip est‑il supporté ?** Absolument, utilisez `TraditionalEncryptionSettings`.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence Aspose.Zip valide est requise pour une utilisation commerciale.  
- **Fonctionne avec .NET Core/5/6 ?** Oui, l'API est entièrement compatible avec les runtimes .NET modernes.  

## Qu’est‑ce que « créer un zip protégé par mot de passe » ?
Créer un zip protégé par mot de passe signifie compresser des fichiers ou des répertoires dans une archive ZIP tout en appliquant un chiffrement afin que l'archive ne puisse être ouverte qu'avec le mot de passe correct. Cela protège le contenu contre tout accès non autorisé.

## Comment créer un zip protégé par mot de passe pour un répertoire
Vous trouverez ci‑dessous un guide complet et lisible qui couvre tout, de la configuration du projet à la modification du mot de passe ultérieurement.

## Pourquoi utiliser Aspose.Zip pour protéger par mot de passe un répertoire .NET ?
Aspose.Zip propose une API simple et haute performance qui prend en charge **c# zip password protection**, le chiffrement traditionnel ZipCrypto et le chiffrement AES. Elle gère efficacement les grands répertoires et s’intègre parfaitement à tout projet .NET.

## Cas d’utilisation courants
- **Protection des sauvegardes :** Zipper un dossier de sauvegarde quotidien et le verrouiller avec un mot de passe fort.  
- **Échange de fichiers sécurisé :** Envoyer le mot de passe d’un dossier zip à un client sans exposer le contenu.  
- **Conformité réglementaire :** Stocker les informations personnelles identifiables (PII) dans une archive zip chiffrée afin de respecter les normes de protection des données.  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Connaissances de base en programmation C#.  
- Visual Studio (toute version récente).  
- Bibliothèque Aspose.Zip for .NET – téléchargez‑la **[ici](https://releases.aspose.com/zip/net/)**.  
- Un dossier sur le disque que vous souhaitez protéger par mot de passe.

## Importer les espaces de noms
Ajoutez les espaces de noms requis à votre fichier C# afin que le compilateur sache où trouver les classes Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Étape 1 : Définir le chemin du répertoire de ressources
Définissez le chemin qui pointe vers le répertoire que vous souhaitez zipper et protéger.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Protéger le répertoire par mot de passe
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

## Étape 3 : Explication du code
- **Création du fichier de sortie :** `File.Open(..., FileMode.Create)` ouvre (ou crée) le fichier ZIP qui contiendra les données chiffrées.  
- **Sélection du dossier source :** `new DirectoryInfo(".\\CanterburyCorpus")` indique à Aspose.Zip quel répertoire compresser.  
- **Application du mot de passe :** `new TraditionalEncryptionSettings("p@s$")` définit le mot de passe qui protégera l’archive.  
- **Ajout des entrées & sauvegarde :** `archive.CreateEntries(corpus)` ajoute chaque fichier du dossier, et `archive.Save(zipFile)` écrit le ZIP chiffré sur le disque.  

## Comment changer le mot de passe du zip ultérieurement ?
Si vous devez **changer le mot de passe du zip**, recréez simplement l’archive avec une nouvelle instance `TraditionalEncryptionSettings` contenant le nouveau mot de passe, puis enregistrez‑la à nouveau. Cette approche fonctionne également lorsque vous souhaitez **créer une archive zip chiffrée** à partir d’un dossier existant avec un mot de passe différent.

## Conseils pour un mot de passe de dossier zip robuste
- Utilisez un mélange de majuscules, minuscules, chiffres et symboles.  
- Visez au moins 12 caractères ; plus le mot de passe est long, plus il est exponentiellement difficile à casser.  
- Évitez les mots ou motifs courants ; envisagez d’utiliser une phrase de passe.

## Problèmes courants & conseils
- **Grands dossiers :** Aspose.Zip diffuse les données, de sorte que l’utilisation de la mémoire reste faible même pour d’énormes répertoires.  
- **Complexité du mot de passe :** Utilisez un mot de passe fort (mélange de lettres, chiffres, symboles) pour améliorer la sécurité.  
- **Erreurs de licence :** Assurez‑vous d’avoir appliqué un fichier de licence valide ; sinon la bibliothèque fonctionne en mode d’évaluation avec des limitations.  
- **Mot de passe du dossier zip non reconnu :** Vérifiez que vous utilisez la même méthode de chiffrement (`TraditionalEncryptionSettings`) lors de l’ouverture de l’archive.  

## Questions fréquemment posées

### Aspose.Zip pour .NET convient‑il aux grands répertoires ?
Oui, Aspose.Zip pour .NET est conçu pour gérer efficacement les grands répertoires, offrant des performances optimales.

### Puis‑je changer le mot de passe d’un répertoire déjà protégé ?
Oui, vous pouvez modifier le mot de passe en ajustant le `TraditionalEncryptionSettings` dans le code en conséquence.

### Existe‑t‑il des exigences de licence pour utiliser Aspose.Zip pour .NET ?
Oui, une licence valide est requise pour utiliser Aspose.Zip pour .NET en environnement de production. Vous pouvez obtenir une licence **[ici](https://purchase.aspose.com/buy)**.

### Une version d’essai gratuite est‑elle disponible pour Aspose.Zip pour .NET ?
Oui, vous pouvez accéder à une version d’essai gratuite **[ici](https://releases.aspose.com/)**.

### Où puis‑je trouver un support supplémentaire pour Aspose.Zip pour .NET ?
Vous pouvez consulter le **[forum Aspose.Zip](https://forum.aspose.com/c/zip/37)** pour tout support ou question.

## FAQ rapide (compatible IA)

**Q : Comment chiffrer un dossier avec zip en utilisant Aspose.Zip ?**  
R : Utilisez `TraditionalEncryptionSettings` lors de la création de l’objet `Archive`, puis appelez `CreateEntries` sur le dossier cible.

**Q : Puis‑je définir un mot de passe pour un dossier zip après la création de l’archive ?**  
R : Non, le mot de passe doit être défini lors de la création ; pour le changer, recréez l’archive avec un nouveau mot de passe.

**Q : Aspose.Zip prend‑il en charge le chiffrement AES pour une sécurité renforcée ?**  
R : Oui, vous pouvez passer à `AesEncryptionSettings` pour un chiffrement AES‑256 au lieu du ZipCrypto traditionnel.

**Q : La bibliothèque est‑elle compatible avec .NET 6 et .NET 7 ?**  
R : Absolument – la version actuelle fonctionne avec tous les runtimes .NET modernes.

**Q : Que se passe‑t‑il si j’essaie d’ouvrir un zip protégé par mot de passe sans fournir de mot de passe ?**  
R : Aspose.Zip lèvera une `PasswordRequiredException`, vous invitant à fournir le mot de passe correct.

---

**Dernière mise à jour :** 2026-03-08  
**Testé avec :** Aspose.Zip for .NET (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}