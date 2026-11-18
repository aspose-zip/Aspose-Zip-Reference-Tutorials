---
date: 2026-11-18
description: Μάθετε πώς να προσθέτετε αρχεία σε tar και να συμπιέζετε αρχεία σε αρχείο
  tarxz .NET χρησιμοποιώντας το Aspose.Zip. Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα
  για αποδοτική αποθήκευση και μετάδοση.
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: Συμπίεση σε TarXz
og_description: Προσθήκη αρχείων σε tar και δημιουργία αρχείου tarxz με το Aspose.Zip.
  Μάθετε πώς να συμπιέζετε αρχεία σε TarXz σε .NET γρήγορα, με υψηλή αποδοτικότητα
  συμπίεσης και διασυστημική συμβατότητα.
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: Προσθήκη αρχείων σε tar και δημιουργία αρχείου tarxz με το Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: Προσθήκη αρχείων σε tar και δημιουργία αρχείου tarxz με το Aspose.Zip
url: /el/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη αρχείων σε tar και δημιουργία αρχείου tarxz με Aspose.Zip

## Εισαγωγή

Αν χρειάζεστε **προσθήκη αρχείων σε tar** και στη συνέχεια **δημιουργία αρχείου tarxz .net**, το Aspose.Zip για .NET κάνει τη διαδικασία απλή και αξιόπιστη. Είτε συσκευάζετε αρχεία καταγραφής, αρχεία ρυθμίσεων ή οποιαδήποτε άλλα στοιχεία για αποθήκευση ή μετάδοση, η συμπίεση σε μορφή TarXz σας προσφέρει υψηλό λόγο συμπίεσης διατηρώντας τη γνωστή δομή tar. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα τις ακριβείς ενέργειες — με πλήρη αποσπάσματα κώδικα — ώστε να μπορείτε να ενσωματώσετε τη δημιουργία tarxz στις .NET εφαρμογές σας με σιγουριά. Στο τέλος θα καταλάβετε γιατί η “προσθήκη αρχείων σε tar” είναι το πρώτο βήμα προς ένα συμπαγές, διαπλατφορμικό πακέτο.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση;** `TarArchive` from `Aspose.Zip.Tar`
- **Πώς συμπιέζω σε tarxz;** Call `SaveXzCompressed` after adding entries
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
- **Χρειάζομαι άδεια;** Yes, a valid Aspose.Zip license is required for production use
- **Χρόνος υλοποίησης;** Roughly 5‑10 minutes for a basic archive

## Τι είναι ένα αρχείο TarXz;

Ένα αρχείο TarXz συνδυάζει το παραδοσιακό Unix `tar` container με τη συμπίεση XZ. Το τμήμα tar ομαδοποιεί πολλά αρχεία σε μία ροή, ενώ το XZ παρέχει ισχυρή, χωρίς απώλειες συμπίεση. Αυτή η μορφή είναι δημοφιλής για τη διανομή κώδικα πηγής, αντιγράφων ασφαλείας και μεγάλων συνόλων δεδομένων, επειδή διατηρεί τις δομές καταλόγων και επιτυγχάνει μικρότερα μεγέθη αρχείων σε σύγκριση με απλό tar ή zip.

## Γιατί να δημιουργήσετε αρχείο tarxz .net με Aspose.Zip;

Η δημιουργία ενός αρχείου TarXz με το Aspose.Zip προσφέρει μια γρήγορη, μονοβήμα λύση χωρίς εξωτερικά εργαλεία. Τα αρχεία είναι 30‑50 % μικρότερα από το gzip και μπορείτε να διαχειριστείτε πάνω από 20 μορφές αρχείων απευθείας στο .NET. Η βιβλιοθήκη επεξεργάζεται μεγάλα αρχεία χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, καθιστώντας την ιδανική για υπηρεσίες cloud και CI pipelines. Υποστηρίζει επίσης περισσότερα από 50 μορφές εισόδου και εξόδου.

## Προαπαιτούμενα

- **Aspose.Zip for .NET** εγκατεστημένο (κατεβάστε από την επίσημη [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Ένας φάκελος που περιέχει τα αρχεία που θέλετε να αρχειοθετήσετε. Στα παραδείγματα παρακάτω, αυτός ο φάκελος αναφέρεται από τη μεταβλητή `dataDir`.  
- Μια έγκυρη άδεια Aspose.Zip (προαιρετική για αξιολόγηση, απαιτείται για παραγωγή).

## Εισαγωγή ονομάτων χώρων

Χρειάζεται μόνο να εισάγετε τα namespaces που εκθέτουν τη λειτουργικότητα TarXz. Δεν απαιτούνται πρόσθετα πακέτα πέρα από τη βασική βιβλιοθήκη Aspose.Zip.

## Πώς να προσθέσετε αρχεία σε tar χρησιμοποιώντας το Aspose.Zip

`TarArchive` είναι η κλάση που αντιπροσωπεύει ένα tar container στο Aspose.Zip. Προσθέτετε αρχεία σε ένα tar αρχείο δημιουργώντας μια παρουσία `TarArchive`, στη συνέχεια καλώντας τη μέθοδο `AddEntry` για κάθε αρχείο που θέλετε να συμπεριλάβετε, καθορίζοντας τη διαδρομή προέλευσης και προαιρετικό όνομα καταχώρησης. Το αρχείο δημιουργεί το tar container στη μνήμη, έτοιμο για επόμενη συμπίεση XZ.

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Συμβουλή:** Η δήλωση `using` εξασφαλίζει ότι το αρχείο διαχειρίζεται σωστά, απελευθερώνοντας τυχόν μη διαχειριζόμενους πόρους.

### Βήμα 1: αρχικοποίηση ενός `TarArchive`

Δημιουργήστε το αντικείμενο `TarArchive` μέσα σε ένα μπλοκ `using` ώστε όλοι οι μη διαχειριζόμενοι πόροι να απελευθερώνονται αυτόματα όταν ολοκληρωθεί η λειτουργία.

```csharp
using (TarArchive archive = new TarArchive())
{
```

### Βήμα 2: προσθήκη αρχείων στο αρχείο

Προσθέστε κάθε αρχείο που θέλετε να συμπεριλάβετε. Σε αυτό το παράδειγμα προσθέτουμε δύο αρχεία κειμένου, αλλά μπορείτε να προσθέσετε όσες καταχωρήσεις χρειάζεστε. Η μέθοδος `AddEntry` δέχεται τη πλήρη διαδρομή του αρχείου και ένα προαιρετικό όνομα καταχώρησης που θα εμφανιστεί μέσα στο tar.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Γιατί είναι σημαντικό:** Η προσθήκη καταχωρήσεων πριν τη συμπίεση επιτρέπει στο Aspose.Zip να δημιουργήσει πρώτα το tar container, έπειτα να εφαρμόσει τη συμπίεση XZ σε ένα βήμα.

### Βήμα 3: αποθήκευση του αρχείου με συμπίεση XZ

Η μέθοδος `SaveXzCompressed` γράφει το tar αρχείο σε ένα αρχείο ενώ εφαρμόζει τη συμπίεση XZ σε ένα βήμα, παράγοντας ένα αρχείο `.tar.xz` που είναι έτοιμο για διανομή.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Αποτέλεσμα:** Τώρα έχετε ένα πλήρως‑συμπιεσμένο αρχείο `archive.tar.xz` που μπορεί να μεταφερθεί, αποθηκευτεί ή αποσυμπιεστεί σε οποιαδήποτε πλατφόρμα που υποστηρίζει TarXz.

## Πώς να συμπιέσετε αρχεία tarxz με το Aspose.Zip

Η συμπίεση σε tarxz με το Aspose.Zip είναι μια διαδικασία δύο βημάτων ενσωματωμένη σε μία κλήση μεθόδου: πρώτα **προσθέσετε αρχεία σε tar**, στη συνέχεια καλείτε το `SaveXzCompressed`. Αυτό εξαλείφει την ανάγκη για εξωτερικά εργαλεία γραμμής εντολών και διατηρεί όλη τη ροή εργασίας μέσα στον κώδικα .NET.

## Κοινά προβλήματα & λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **“File not found” exception** | Λανθασμένη διαδρομή `dataDir` | Επαληθεύστε ότι η διαδρομή του φακέλου τελειώνει με ανάστροφη κάθετο (`\`) ή χρησιμοποιήστε `Path.Combine`. |
| **Large memory usage** | Πολύ μεγάλα αρχεία που συμπιέζονται στη μνήμη | Χρησιμοποιήστε το `TarArchive` σε λειτουργία streaming (`SaveXzCompressed` υπερφόρτωση που δέχεται `Stream`). |
| **License not applied** | Απουσία αρχείου άδειας | Φορτώστε την άδεια κατά την εκκίνηση της εφαρμογής: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Συχνές ερωτήσεις

**Q: Είναι το Aspose.Zip συμβατό με όλα τα περιβάλλοντα .NET;**  
A: Ναι, το Aspose.Zip λειτουργεί με .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10. Δείτε την [documentation](https://reference.aspose.com/zip/net/) για λεπτομέρειες.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Zip;**  
A: Μπορείτε να ζητήσετε προσωρινή άδεια από τη [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**Q: Υπάρχουν επιπλέον παραδείγματα για άλλες μορφές αρχείων;**  
A: Σίγουρα—εξερευνήστε το πλήρες σύνολο παραδειγμάτων στην [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: Πού μπορώ να λάβω βοήθεια ή να συζητήσω προβλήματα;**  
A: Συμμετέχετε στη συζήτηση στο [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) για υποστήριξη από την κοινότητα και επίσημες απαντήσεις.

**Q: Μπορώ να δοκιμάσω το Aspose.Zip δωρεάν πριν το αγοράσω;**  
A: Ναι, μια δωρεάν δοκιμή είναι διαθέσιμη στη [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## Συμπέρασμα

Ακολουθώντας τα παραπάνω βήματα, τώρα γνωρίζετε **πώς να προσθέσετε αρχεία σε tar** και **πώς να συμπιέσετε αρχεία tarxz**, και πιο σημαντικό, **πώς να δημιουργήσετε αρχείο tarxz .net** χρησιμοποιώντας το Aspose.Zip. Αυτή η προσέγγιση σας παρέχει ένα συμπαγές, φορητό πακέτο που μπορεί να ενσωματωθεί απρόσκοπτα σε οποιαδήποτε ροή εργασίας .NET — είτε δημιουργείτε μια επιτραπέζια εφαρμογή, μια υπηρεσία web ή μια αυτοματοποιημένη CI/CD pipeline.

---

**Τελευταία ενημέρωση:** 2026-11-18  
**Δοκιμή με:** Aspose.Zip for .NET 24.11  
**Συγγραφέας:** Aspose  

## Σχετικά μαθήματα

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [How to compress tar and create TarBz2 with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [How to compress multiple files tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}