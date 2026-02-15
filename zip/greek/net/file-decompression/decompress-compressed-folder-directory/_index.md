---
date: 2026-02-15
description: Μάθετε πώς να εξάγετε ένα αρχείο zip σε φάκελο χρησιμοποιώντας το Aspose.Zip
  για .NET, συμπεριλαμβανομένων των αρχείων με προστασία κωδικού πρόσβασης και της
  κρυπτογραφημένης εξαγωγής zip.
linktitle: extract zip to folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να εξάγετε zip σε φάκελο με το Aspose.Zip για .NET
url: /el/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να εξάγετε zip σε φάκελο με Aspose.Zip για .NET

## Introduction

Αν χρειάζεστε να **εξάγετε zip σε φάκελο** γρήγορα και αξιόπιστα σε μια εφαρμογή .NET, το Aspose.Zip για .NET σας παρέχει ένα καθαρό, διαπλατφορμικό API που διαχειρίζεται τόσο απλά όσο και κρυπτογραφημένα αρχεία. Σε αυτό το tutorial θα καλύψουμε όλα όσα χρειάζεστε—από τη ρύθμιση της βιβλιοθήκης μέχρι την εξαγωγή ενός αρχείου ZIP με κωδικό πρόσβασης—ώστε να εστιάσετε στη λογική της επιχείρησής σας αντί για τη χαμηλού επιπέδου διαχείριση αρχείων.

## Quick Answers
- **Ποιος είναι ο κύριος σκοπός του Aspose.Zip;** Να δημιουργεί, να διαβάζει και να **εξάγει zip σε φάκελο** σε εφαρμογές .NET.  
- **Πώς εξάγω zip με κωδικό πρόσβασης;** Περνάτε τον κωδικό μέσω του `ArchiveLoadOptions.DecryptionPassword`.  
- **Μπορώ να αποσυμπιέσω κρυπτογραφημένο αρχείο χωρίς κωδικό;** Όχι—το Aspose.Zip απαιτεί τον σωστό κωδικό για να ανοίξει κρυπτογραφημένα αρχεία.  
- **Ποιες εκδόσεις του .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Απαιτείται άδεια για παραγωγή;** Ναι, απαιτείται έγκυρη άδεια Aspose.Zip για εμπορική χρήση.

## What is **extract zip to folder**?

Η εξαγωγή ενός αρχείου ZIP σημαίνει ανάγνωση των συμπιεσμένων δεδομένων και εγγραφή των αρχικών αρχείων σε έναν προορισμένο φάκελο στο δίσκο. Το Aspose.Zip αφαιρεί τις λεπτομέρειες χαμηλού επιπέδου, επιτρέποντάς σας να καλέσετε μία μόνο μέθοδο για να εκτελέσετε ολόκληρη τη διαδικασία.

## Why use Aspose.Zip for **how to unzip zip** tasks?

- **Απλό API** – ελάχιστος κώδικας για άνοιγμα, αποκρυπτογράφηση και εξαγωγή αρχείων.  
- **Υποστηρίζει κρυπτογραφημένα αρχεία** – ιδανικό για ασφαλή ανταλλαγή δεδομένων.  
- **Διαπλατφορμικό** – λειτουργεί σε Windows, Linux και macOS με .NET Core/.NET 5+.  
- **Χωρίς εξωτερικές εξαρτήσεις** – δεν χρειάζεται εγκατάσταση εγγενών εργαλείων zip.  

## Prerequisites

- Βιβλιοθήκη Aspose.Zip για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από την [τεκμηρίωση Aspose.Zip για .NET](https://reference.aspose.com/zip/net/).
- Περιβάλλον ανάπτυξης .NET (Visual Studio, VS Code ή οποιοδήποτε IDE προτιμάτε).
- (Προαιρετικά) Ένα αρχείο ZIP με κωδικό πρόσβασης αν θέλετε να δοκιμάσετε **εξαγωγή zip με κωδικό**.

## Import Namespaces

Στο .NET project σας, εισάγετε τα απαραίτητα namespaces για να αξιοποιήσετε τις λειτουργίες του Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Now let’s break down the extraction process step‑by‑step.

## How to **extract zip to folder** – Step‑by‑Step Guide

### Step 1: Open the ZIP file (or encrypted archive)

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

Ανοίγουμε το αρχείο ZIP με ένα `FileStream`. Προσαρμόστε τη διαδρομή ώστε να δείχνει στο δικό σας αρχείο. Αν το αρχείο δεν είναι κρυπτογραφημένο, ο ίδιος κώδικας λειτουργεί για μια κανονική περίπτωση **αποσυμπίεσης φακέλου zip**.

### Step 2: Create an `Archive` instance (provide password when needed)

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

Ο κατασκευαστής `Archive` λαμβάνει το stream και ένα αντικείμενο `ArchiveLoadOptions`. Η παροχή του `DecryptionPassword` είναι ο τρόπος για να **εξάγετε zip με κωδικό** και να διαχειριστείτε περιπτώσεις **αποσυμπίεσης κρυπτογραφημένου αρχείου**.

### Step 3: Extract the contents to a destination folder

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

Καλώντας το `ExtractToDirectory` γράφει κάθε καταχώρηση του αρχείου στον καθορισμένο φάκελο, ολοκληρώνοντας τη λειτουργία **εξαγωγής zip σε φάκελο**. Η μέθοδος θα δημιουργήσει αυτόματα τον προορισμό αν δεν υπάρχει.

> **Συμβουλή:** Αν χρειάζεστε μόνο ένα υποσύνολο αρχείων, χρησιμοποιήστε την υπερφόρτωση που δέχεται ένα φίλτρο delegate αντί να εξάγετε τα πάντα.

## Common Issues & Troubleshooting

- **Λάθος κωδικός πρόσβασης** – το Aspose.Zip ρίχνει εξαίρεση αυθεντικοποίησης. Επαληθεύστε τη συμβολοσειρά κωδικού ή ανακτήστε την με ασφάλεια από πηγή ρυθμίσεων.  
- **Η διαδρομή προορισμού δεν βρέθηκε** – Βεβαιωθείτε ότι η διαδρομή του φακέλου προορισμού είναι έγκυρη· το `ExtractToDirectory` θα δημιουργήσει τους ελλιπείς φακέλους, αλλά η γονική διαδρομή πρέπει να είναι προσβάσιμη.  
- **Μεγάλα αρχεία** – Για πολύ μεγάλα αρχεία ZIP, σκεφτείτε την εξαγωγή καταχώρησης‑κατά‑καταχώρηση χρησιμοποιώντας το streaming API για να μειώσετε τη χρήση μνήμης.  

## Frequently Asked Questions

**Ε: Υποστηρίζει το Aspose.Zip άλλες μορφές συμπίεσης όπως GZIP;**  
Α: Ναι, το Aspose.Zip για .NET υποστηρίζει ZIP, GZIP και αρκετές άλλες κοινές μορφές.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Zip σε εμπορικά και μη εμπορικά έργα;**  
Α: Απόλυτα. Απαιτείται έγκυρη άδεια για παραγωγή, αλλά μπορείτε να χρησιμοποιήσετε τη δωρεάν δοκιμή για αξιολόγηση.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;**  
Α: Μπορείτε να αποκτήσετε προσωρινή άδεια από [εδώ](https://purchase.aspose.com/temporary-license/) για σκοπούς δοκιμής.

**Ε: Από πού μπορώ να κατεβάσω δωρεάν δοκιμή του Aspose.Zip;**  
Α: Επισκεφθείτε τη σελίδα δοκιμής του Aspose.Zip [εδώ](https://releases.aspose.com/) για να κατεβάσετε την τελευταία έκδοση.

**Ε: Πού μπορώ να ζητήσω βοήθεια αν αντιμετωπίσω προβλήματα;**  
Α: Το φόρουμ κοινότητας του Aspose.Zip είναι ένας εξαιρετικός τόπος για βοήθεια: [forum υποστήριξης](https://forum.aspose.com/c/zip/37).

---

**Τελευταία ενημέρωση:** 2026-02-15  
**Δοκιμάστηκε με:** Aspose.Zip for .NET (latest release)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}