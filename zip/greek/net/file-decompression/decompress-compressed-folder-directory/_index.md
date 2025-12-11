---
date: 2025-12-10
description: Αποκτήστε το πλήρες δυναμικό του Aspose.Zip για .NET! Μάθετε πώς να αποσυμπιέζετε
  φακέλους χωρίς κόπο με αυτόν τον βήμα‑βήμα οδηγό. Βυθιστείτε στον κόσμο της αδιάλειπτης
  συμπίεσης και εξαγωγής.
linktitle: Decompress Compressed Folder to Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Αποσυμπίεση Συμπιεσμένου Φακέλου σε Κατάλογο στο Aspose.Zip για .NET
url: /el/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να εξάγετε αρχεία ZIP με το Aspose.Zip για .NET

## Εισαγωγή

Καλώς ήρθατε στον κόσμο του Aspose.Zip για .NET, μιας ισχυρής βιβλιοθήκης που δίνει τη δυνατότητα στους προγραμματιστές να διαχειρίζονται συμπιεσμένους φακέλους με ευκολία. Αν αναρωτιέστε **how to extract zip** αρχεία σε .NET, αυτός ο οδηγός σας καλύπτει. Σε αυτό το tutorial, θα εμβαθύνουμε στη διαδικασία αποσυμπίεσης ενός συμπιεσμένου φακέλου σε έναν κατάλογο χρησιμοποιώντας το Aspose.Zip για .NET. Δέστε τη ζώνη ασφαλείας καθώς σας καθοδηγούμε βήμα-βήμα, αποσαφηνίζοντας τις λεπτομέρειες αυτού του ισχυρού εργαλείου.

## Γρήγορες Απαντήσεις
- **What is the primary purpose of Aspose.Zip?** Για τη δημιουργία, ανάγνωση και εξαγωγή αρχείων ZIP σε εφαρμογές .NET.  
- **How to extract zip** με κωδικό πρόσβασης; Χρησιμοποιήστε το `ArchiveLoadOptions` με την ιδιότητα `DecryptionPassword`.  
- **Can I unzip encrypted archive** χωρίς κωδικό πρόσβασης; Όχι – πρέπει να παρέχετε τον σωστό κωδικό.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is a license required for production?** Ναι, απαιτείται έγκυρη άδεια Aspose.Zip για εμπορική χρήση.

## Τι είναι **how to extract zip**;
Η εξαγωγή ενός αρχείου ZIP σημαίνει ανάγνωση των συμπιεσμένων δεδομένων και εγγραφή των αρχικών αρχείων σε έναν προορισμό. Το Aspose.Zip αφαιρεί τις λεπτομέρειες χαμηλού επιπέδου, επιτρέποντάς σας να εστιάσετε στη λογική της επιχείρησης αντί στη διαχείριση των αρχείων.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για εργασίες **how to unzip folder**;
- **Straightforward API** – ελάχιστος κώδικας για άνοιγμα, αποκρυπτογράφηση και εξαγωγή αρχείων.  
- **Supports encrypted archives** – ιδανικό για ασφαλή ανταλλαγή δεδομένων.  
- **Cross‑platform** – λειτουργεί σε Windows, Linux και macOS με .NET Core/.NET 5+.  
- **No external dependencies** – δεν απαιτείται εγκατάσταση εξωτερικών εργαλείων zip.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

- Aspose.Zip for .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από την [Aspose.Zip for .NET documentation](https://reference.aspose.com/zip/net/).

## Εισαγωγή Namespaces

Στο .NET project σας, εισάγετε τα απαραίτητα namespaces για να αξιοποιήσετε τις λειτουργίες του Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Τώρα, ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλαπλά βήματα για μια ολοκληρωμένη κατανόηση.

## Πώς να **unzip folder** – Οδηγός βήμα‑βήμα

### Βήμα 1: Άνοιγμα του Συμπιεσμένου Φακέλου

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

Ξεκινήστε ανοίγοντας το συμπιεσμένο φάκελο χρησιμοποιώντας ένα `FileStream`. Προσαρμόστε τη διαδρομή του αρχείου σύμφωνα με τη δομή του project σας.

### Βήμα 2: Δημιουργία ενός αντικειμένου Archive (Αποκρυπτογράφηση του ZIP)

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

Δημιουργήστε ένα αντικείμενο `Archive`, περνώντας το ρεύμα `zipFile` και παρέχοντας προαιρετικές επιλογές φόρτωσης, όπως ο κωδικός αποκρυπτογράφησης σε αυτήν την περίπτωση. Αυτό είναι το βασικό βήμα όταν χρειάζεται να **unzip encrypted archive** αρχεία.

### Βήμα 3: Εξαγωγή σε Κατάλογο

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

Τέλος, χρησιμοποιήστε τη μέθοδο `ExtractToDirectory` για να αποσυμπιέσετε και να εξάγετε τα περιεχόμενα του συμπιεσμένου φακέλου στον καθορισμένο κατάλογο. Αυτό ολοκληρώνει τη διαδικασία **how to decompress zip**.

Επαναλάβετε αυτά τα βήματα για άλλους συμπιεσμένους φακέλους, εξασφαλίζοντας αδιάλειπτη ενσωμάτωση με το Aspose.Zip για .NET.

## Κοινά Προβλήματα & Επίλυση
- **Incorrect password** – Εάν ο κωδικός αποκρυπτογράφησης είναι λανθασμένος, το Aspose.Zip θα ρίξει εξαίρεση αυθεντικοποίησης. Ελέγξτε ξανά τη συμβολοσειρά κωδικού.  
- **Path not found** – Βεβαιωθείτε ότι ο προορισμός υπάρχει ή αφήστε τη `ExtractToDirectory` να το δημιουργήσει αυτόματα.  
- **Large archives** – Για πολύ μεγάλα αρχεία ZIP, σκεφτείτε την εξαγωγή σε τμήματα ή τη χρήση streaming APIs για μείωση της πίεσης μνήμης.

## Συχνές Ερωτήσεις

**Q: Is Aspose.Zip for .NET compatible with various compression formats?**  
A: Ναι, το Aspose.Zip για .NET υποστηρίζει δημοφιλείς μορφές συμπίεσης όπως ZIP, GZIP και άλλα.

**Q: Can I use Aspose.Zip for .NET in both commercial and non‑commercial projects?**  
A: Απόλυτα, μπορείτε να χρησιμοποιήσετε το Aspose.Zip για .NET τόσο σε εμπορικά όσο και σε μη εμπορικά έργα.

**Q: Is there a free trial available for Aspose.Zip for .NET?**  
A: Ναι, μπορείτε να δοκιμάσετε τις δυνατότητες με δωρεάν δοκιμή επισκεπτόμενοι το [here](https://releases.aspose.com/).

**Q: How can I get support for Aspose.Zip for .NET?**  
A: Ζητήστε βοήθεια από την κοινότητα Aspose.Zip στο [support forum](https://forum.aspose.com/c/zip/37).

**Q: Do I need a temporary license for testing Aspose.Zip for .NET?**  
A: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια από το [here](https://purchase.aspose.com/temporary-license/) για σκοπούς δοκιμής.

---

**Τελευταία ενημέρωση:** 2025-12-10  
**Δοκιμάστηκε με:** Aspose.Zip for .NET (τελευταία έκδοση)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}