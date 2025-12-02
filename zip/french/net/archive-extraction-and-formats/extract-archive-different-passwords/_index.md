---
date: 2025-12-01
description: Apprenez à extraire des fichiers zip protégés par mot de passe à l'aide
  d'Aspose.Zip pour .NET, en gérant efficacement plusieurs entrées protégées.
language: fr
linktitle: Extracting Archive Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Comment extraire un zip protégé par mot de passe avec Aspise.Zip pour .NET
url: /net/archive-extraction-and-formats/extract-archive-different-passwords/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment extraire un Zip avec mot de passe en utilisant Aspose.Zip pour .NET

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.Zip for .NET.
- **Puis‑je extraire des entrées qui ont des mots de passe différents ?** Oui—chaque entrée peut être ouverte avec son propre mot de passe.
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit est disponible.
- **Plateformes prises en charge ?** .NET Framework, .NET Core, .NET 5/6+.
- **Temps d’implémentation typique ?** Environ 10 minutes pour un scénario de base.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Aspose.Zip for .NET** installé dans votre projet. Vous pouvez trouver la documentation officielle [ici](https://reference.aspose.com/zip/net/).
- Un environnement de développement .NET (Visual Studio, Rider ou VS Code) ciblant .NET 5 ou supérieur.
- Un fichier ZIP contenant des entrées chiffrées avec **différents mots de passe** (l’exemple utilisé ici est `different_password.zip`).

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis pour travailler avec les archives :

```csharp
using Aspose.Zip;
using System.IO;
```

Ces deux instructions `using` vous donnent accès à la classe `Archive` et aux utilitaires d’E/S standard.

## Étape 1 : Définir le répertoire de travail

Définissez le dossier où se trouve le fichier ZIP et où les fichiers extraits seront écrits :

```csharp
string dataDir = "Your Document Directory";
```

> **Astuce :** Utilisez `Path.Combine` pour construire des chemins multiplateformes si vous devez prendre en charge Linux/macOS.

## Étape 2 : Extraire les entrées d’archive avec des mots de passe différents

Ci‑dessous, nous parcourons les étapes exactes pour ouvrir l’archive et extraire chaque entrée en utilisant son propre mot de passe.

### Étape 2.1 : Ouvrir le fichier Zip

```csharp
using (FileStream zipFile = File.Open(dataDir + "\\different_password.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
        // Continue to the next steps...
    }
}
```

L’objet `Archive` représente le conteneur ZIP. Conserver le `FileStream` et l’`Archive` à l’intérieur de blocs `using` garantit que toutes les ressources sont libérées rapidement.

### Étape 2.2 : Extraire la première entrée (Mot de passe = « first_pass »)

```csharp
archive.Entries[0].Extract(dataDir + "alice29_extracted_pass_out.txt", "first_pass");
```

Ici, nous **extrayons plusieurs entrées zip** en les accédant via la collection `Entries`. La première entrée est déchiffrée avec le mot de passe "first_pass".

### Étape 2.3 : Extraire la deuxième entrée (Mot de passe = « second_pass »)

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_pass_out.txt", "second_pass");
```

La deuxième entrée utilise un mot de passe différent, démontrant l’**extraction de zip protégée par mot de passe** pour chaque fichier individuel.

## Pourquoi cette approche est importante

- **Sécurité granulaire :** Chaque fichier peut avoir son propre mot de passe, réduisant le risque en cas de compromission d’un seul mot de passe.
- **Flexibilité :** Vous pouvez décider programmétiquement quel mot de passe appliquer en fonction de la logique métier (par ex., rôles d’utilisateur).
- **Performance :** Aspose.Zip traite les entrées en mémoire, évitant la nécessité de décompresser l’ensemble de l’archive au préalable.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| *« Invalid password » exception* | Mot de passe incorrect fourni ou l’entrée n’est pas réellement chiffrée. | Vérifiez la chaîne du mot de passe et assurez‑vous que l’entrée est protégée par mot de passe. |
| *Fichier non trouvé* | Le chemin `dataDir` est incorrect. | Utilisez `Path.Combine(dataDir, "different_password.zip")` et revérifiez le dossier. |
| *Les grandes archives entraînent une forte utilisation de mémoire* | Toutes les entrées sont chargées en mémoire par défaut. | Diffusez chaque entrée individuellement ou utilisez `Archive.ExtractToDirectory` avec un rappel de mot de passe (si supporté). |

## Questions fréquentes

**Q1 : Puis‑je utiliser Aspose.Zip à la fois dans des projets .NET Core et .NET Framework ?**  
R1 : Oui, Aspose.Zip prend en charge .NET Framework, .NET Core et .NET 5/6+, vous offrant une flexibilité sur toutes les plateformes.

**Q2 : Où puis‑je trouver un support supplémentaire ou des discussions communautaires liées à Aspose.Zip ?**  
R2 : Consultez le [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) pour interagir avec la communauté, poser des questions et partager des expériences.

**Q3 : Une version d’essai gratuite est‑elle disponible pour Aspose.Zip ?**  
R3 : Oui, vous pouvez accéder à l’essai gratuit d’Aspose.Zip [ici](https://releases.aspose.com/).

**Q4 : Comment obtenir une licence temporaire pour Aspose.Zip ?**  
R4 : Pour une licence temporaire, visitez [ce lien](https://purchase.aspose.com/temporary-license/).

**Q5 : Où puis‑je acheter Aspose.Zip ?**  
R5 : Pour acheter Aspose.Zip, consultez la [page d’achat](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-01  
**Testé avec :** Aspose.Zip for .NET 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

---