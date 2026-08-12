---
date: 2026-06-04
description: Μάθετε πώς να εξάγετε zip σε φάκελο χρησιμοποιώντας το Aspose.Zip για
  .NET, συμπεριλαμβανομένων των αρχείων με προστασία κωδικού πρόσβασης και της κρυπτογραφημένης
  εξαγωγής zip.
keywords:
- extract zip to folder
- how to unzip zip
- extract zip with password
- unzip files in c#
- read zip archive c#
linktitle: εξαγωγή zip σε φάκελο
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  headline: How to extract zip to folder with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  name: How to extract zip to folder with Aspose.Zip for .NET
  steps:
  - name: Open the ZIP file (or encrypted archive)
    text: The `FileStream` class provides a read‑only stream to the physical ZIP file
      on disk. Using a stream lets Aspose.Zip work with files located on network shares
      or embedded resources without first copying them to a temporary location.
  - name: Create an `Archive` instance (provide password when needed)
    text: The `Archive` class is the core object that represents a ZIP archive in
      memory. `ArchiveLoadOptions` defines settings used when loading an archive,
      such as the decryption password. Passing an `ArchiveLoadOptions` object with
      the `DecryptionPassword` property enables decryption of AES‑encrypted entri
  - name: Extract the contents to a destination folder
    text: '`ExtractToDirectory` iterates over every entry in the archive and writes
      it to the target path, preserving the original folder hierarchy. The method
      creates missing directories automatically and can also filter entries if you
      only need a subset. > **Pro tip:** If you only need to extract a subset of'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET supports ZIP, GZIP, and several other common
      formats.
    question: Does Aspose.Zip support other compression formats like GZIP?
  - answer: Absolutely. A valid license is required for production, but you can use
      the free trial for evaluation.
    question: Can I use Aspose.Zip in both commercial and non‑commercial projects?
  - answer: You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: How do I get a temporary license for testing?
  - answer: Visit the Aspose.Zip trial page [here](https://releases.aspose.com/) to
      download the latest version.
    question: Where can I download a free trial of Aspose.Zip?
  - answer: 'The Aspose.Zip community forum is a great place to get assistance: [support
      forum](https://forum.aspose.com/c/zip/37).'
    question: Where can I ask for help if I run into issues?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να εξάγετε zip σε φάκελο με το Aspose.Zip για .NET
url: /el/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να εξάγετε zip σε φάκελο με το Aspose.Zip για .NET

## Εισαγωγή

Αν χρειάζεστε **εξαγωγή zip σε φάκελο** γρήγορα και αξιόπιστα σε μια εφαρμογή .NET, το Aspose.Zip για .NET σας προσφέρει ένα καθαρό, cross‑platform API που διαχειρίζεται τόσο απλά όσο και κρυπτογραφημένα αρχεία. Σε αυτό το μάθημα θα καλύψουμε όλα όσα χρειάζεστε—από τη ρύθμιση της βιβλιοθήκης μέχρι την εξαγωγή ενός zip αρχείου με κωδικό πρόσβασης—ώστε να εστιάσετε στη λογική της επιχείρησής σας αντί για τη χαμηλού επιπέδου διαχείριση αρχείων.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος σκοπός του Aspose.Zip;** Να δημιουργεί, να διαβάζει και να **εξάγει zip σε φάκελο** σε εφαρμογές .NET.  
- **Πώς εξάγω zip με κωδικό πρόσβασης;** Περνάτε τον κωδικό μέσω του `ArchiveLoadOptions.DecryptionPassword`.  
- **Μπορώ να αποσυμπιέσω κρυπτογραφημένο αρχείο χωρίς κωδικό πρόσβασης;** Όχι—το Aspose.Zip απαιτεί τον σωστό κωδικό πρόσβασης για το άνοιγμα κρυπτογραφημένων αρχείων.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10.  
- **Απαιτείται άδεια για παραγωγή;** Ναι, απαιτείται έγκυρη άδεια Aspose.Zip για εμπορική χρήση.

## Τι είναι η **εξαγωγή zip σε φάκελο**;

Η εξαγωγή ενός αρχείου ZIP σημαίνει ανάγνωση των συμπιεσμένων δεδομένων και εγγραφή των αρχικών αρχείων σε έναν προορισμένο φάκελο στο δίσκο. Το Aspose.Zip αφαιρεί τις λεπτομέρειες χαμηλού επιπέδου, επιτρέποντάς σας να καλέσετε μια ενιαία μέθοδο για να εκτελέσετε ολόκληρη τη διαδικασία, ενώ υποστηρίζει **30+ μορφές αρχείων** και διαχειρίζεται αρχεία έως **2 GB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για εργασίες **πώς να αποσυμπιέσετε zip**;

Το Aspose.Zip παρέχει ένα απλό API που σας επιτρέπει να αποσυμπιέζετε αρχεία με λίγες μόνο γραμμές κώδικα, υποστηρίζει αρχεία με κωδικό πρόσβασης και κρυπτογραφημένα με AES, και λειτουργεί σε Windows, Linux και macOS. Επεξεργάζεται **αρχείο ZIP 500 σελίδων σε λιγότερο από 2 δευτερόλεπτα** σε έναν τυπικό διακομιστή, εξαλείφοντας την ανάγκη για εγγενή εργαλεία zip και μειώνοντας την πολυπλοκότητα της ανάπτυξης.

## Προαπαιτούμενα

- Βιβλιοθήκη Aspose.Zip για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από την [τεκμηρίωση Aspose.Zip για .NET](https://reference.aspose.com/zip/net/).
- Ένα περιβάλλον ανάπτυξης .NET (Visual Studio, VS Code ή οποιοδήποτε IDE προτιμάτε).
- (Προαιρετικό) Ένα αρχείο ZIP με κωδικό πρόσβασης αν θέλετε να δοκιμάσετε **εξαγωγή zip με κωδικό πρόσβασης**.

## Εισαγωγή Namespaces

Στο .NET έργο σας, εισάγετε τα απαραίτητα namespaces για να αξιοποιήσετε τις λειτουργίες του Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Τώρα ας αναλύσουμε τη διαδικασία εξαγωγής βήμα προς βήμα.

## Πώς να **εξάγετε zip σε φάκελο** – Οδηγός βήμα προς βήμα

Φορτώστε το αρχείο ZIP, προαιρετικά παρέχετε έναν κωδικό αποσυμπίεσης, και καλέστε το `ExtractToDirectory` – αυτή είναι η πλήρης ροή εργασίας εξαγωγής σε τρία σύντομα βήματα. Το API δημιουργεί αυτόματα το φάκελο προορισμού αν δεν υπάρχει και μεταφέρει τα αρχεία στο δίσκο ώστε η χρήση μνήμης να παραμένει χαμηλή, ακόμη και για αρχεία πολλαπλών gigabyte.

### Βήμα 1: Άνοιγμα του αρχείου ZIP (ή κρυπτογραφημένου αρχείου)

Η κλάση `FileStream` παρέχει μια ροή μόνο για ανάγνωση στο φυσικό αρχείο ZIP στο δίσκο. Η χρήση ροής επιτρέπει στο Aspose.Zip να εργάζεται με αρχεία που βρίσκονται σε δικτυακές κοινόχρηστες ή ενσωματωμένους πόρους χωρίς να τα αντιγράψετε πρώτα σε προσωρινή τοποθεσία.

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

### Βήμα 2: Δημιουργία ενός αντικειμένου `Archive` (παρέχετε κωδικό πρόσβασης όταν χρειάζεται)

Η κλάση `Archive` είναι το βασικό αντικείμενο που αντιπροσωπεύει ένα αρχείο ZIP στη μνήμη. Το `ArchiveLoadOptions` ορίζει τις ρυθμίσεις που χρησιμοποιούνται κατά τη φόρτωση ενός αρχείου, όπως ο κωδικός αποσυμπίεσης. Η μεταβίβαση ενός αντικειμένου `ArchiveLoadOptions` με την ιδιότητα `DecryptionPassword` ενεργοποιεί την αποσυμπίεση των κρυπτογραφημένων με AES καταχωρίσεων.

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

### Βήμα 3: Εξαγωγή των περιεχομένων σε φάκελο προορισμού

Το `ExtractToDirectory` διασχίζει κάθε καταχώρηση στο αρχείο και την γράφει στην προορισμένη διαδρομή, διατηρώντας την αρχική ιεραρχία φακέλων. Η μέθοδος δημιουργεί αυτόματα τους ελλιπείς φακέλους και μπορεί επίσης να φιλτράρει τις καταχωρήσεις αν χρειάζεστε μόνο ένα υποσύνολο.

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

> **Συμβουλή:** Αν χρειάζεστε μόνο ένα υποσύνολο αρχείων, χρησιμοποιήστε την υπερφόρτωση που δέχεται έναν delegate φίλτρου αντί να εξάγετε τα πάντα.

## Συνηθισμένα Προβλήματα & Επίλυση

- **Λάθος κωδικός πρόσβασης** – Το Aspose.Zip ρίχνει μια εξαίρεση αυθεντικοποίησης. Ελέγξτε ξανά τη συμβολοσειρά κωδικού ή ανακτήστε την με ασφαλή τρόπο από πηγή ρυθμίσεων.  
- **Διαδρομή προορισμού δεν βρέθηκε** – Βεβαιωθείτε ότι η διαδρομή του φακέλου προορισμού είναι έγκυρη· το `ExtractToDirectory` θα δημιουργήσει τους ελλιπείς φακέλους, αλλά η γονική διαδρομή πρέπει να είναι προσβάσιμη.  
- **Μεγάλα αρχεία** – Για πολύ μεγάλα αρχεία ZIP, εξετάστε την εξαγωγή καταχώρησης-κατά-καταχώρηση χρησιμοποιώντας το streaming API για να διατηρήσετε τη χρήση μνήμης χαμηλή.  

## Συχνές Ερωτήσεις

**Ε: Υποστηρίζει το Aspose.Zip άλλες μορφές συμπίεσης όπως GZIP;**  
Α: Ναι, το Aspose.Zip για .NET υποστηρίζει ZIP, GZIP και αρκετές άλλες κοινές μορφές.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Zip σε εμπορικά και μη εμπορικά έργα;**  
Α: Απόλυτα. Απαιτείται έγκυρη άδεια για παραγωγή, αλλά μπορείτε να χρησιμοποιήσετε τη δωρεάν δοκιμή για αξιολόγηση.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμή;**  
Α: Μπορείτε να αποκτήσετε προσωρινή άδεια από [εδώ](https://purchase.aspose.com/temporary-license/) για σκοπούς δοκιμής.

**Ε: Από πού μπορώ να κατεβάσω δωρεάν δοκιμή του Aspose.Zip;**  
Α: Επισκεφθείτε τη σελίδα δοκιμής Aspose.Zip [εδώ](https://releases.aspose.com/) για να κατεβάσετε την τελευταία έκδοση.

**Ε: Πού μπορώ να ζητήσω βοήθεια αν αντιμετωπίσω προβλήματα;**  
Α: Το φόρουμ κοινότητας Aspose.Zip είναι ένας εξαιρετικός τόπος για βοήθεια: [forum υποστήριξης](https://forum.aspose.com/c/zip/37).

---

**Τελευταία ενημέρωση:** 2026-06-04  
**Δοκιμάστηκε με:** Aspose.Zip για .NET (τελευταία έκδοση)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να εξάγετε Zip με κωδικό πρόσβασης χρησιμοποιώντας Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [Πώς να εξάγετε WIM σε φάκελο χρησιμοποιώντας Aspose.Zip για .NET](/zip/net/file-decompression/decompress-wim-folder/)
- [Πώς να αποσυμπιέσετε αρχεία με Aspose.Zip για .NET](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}