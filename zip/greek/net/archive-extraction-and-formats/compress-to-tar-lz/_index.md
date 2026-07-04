---
date: 2026-07-04
description: Μάθετε πώς να συμπιέσετε πολλαπλά αρχεία tar χρησιμοποιώντας Aspose.Zip
  για .NET και να δημιουργήσετε αρχεία tar.lz αποδοτικά.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Συμπίεση σε TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να συμπιέσετε πολλαπλά αρχεία tar με Aspose.Zip για .NET
url: /el/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να συμπιέσετε πολλαπλά αρχεία tar με το Aspose.Zip για .NET

Στη σύγχρονη ανάπτυξη .NET, η αποδοτική συσκευασία αρχείων μπορεί να βελτιώσει δραματικά το μέγεθος της ανάπτυξης και τους χρόνους μεταφοράς δικτύου. **Compress multiple files tar** είναι συχνή απαίτηση όταν χρειάζεστε ένα ελαφρύ, LZ‑συμπιεσμένο αρχείο TAR για αντίγραφα ασφαλείας, διανομή ή μεταφορτώσεις στο cloud. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα ένα σαφές **παράδειγμα συμπίεσης tar.lz** χρησιμοποιώντας τη βιβλιοθήκη Aspose.Zip, ώστε να μπορείτε γρήγορα να δημιουργήσετε ένα **αρχείο tar.lz** στις δικές σας εφαρμογές.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Aspose.Zip for .NET.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 5‑10 λεπτά για ένα βασικό παράδειγμα.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Μπορώ να συμπιέσω πολλαπλά αρχεία ταυτόχρονα;** Ναι – απλώς προσθέστε περισσότερες καταχωρήσεις πριν από την αποθήκευση.

## Πώς να συμπιέσω πολλαπλά αρχεία tar με το Aspose.Zip για .NET;
Φορτώστε τα πηγαία αρχεία σας, δημιουργήστε ένα αντικείμενο `TarArchive`, προσθέστε κάθε αρχείο με `CreateEntry` και ολοκληρώστε καλώντας το `SaveLzipped`. Η βιβλιοθήκη διαχειρίζεται τη δομή TAR και τη συμπίεση LZ εσωτερικά, έτσι καταλήγετε με ένα μόνο αρχείο `*.tar.lz` σε λίγες γραμμές κώδικα. Αυτή η προσέγγιση λειτουργεί σε Windows, Linux και macOS χωρίς εξαρτήσεις native.

## Τι είναι η συμπίεση tar.lz;
`tar.lz` είναι ένα αρχείο TAR που έχει συμπιεστεί χρησιμοποιώντας τον αλγόριθμο LZMA (συχνά αναφέρεται απλώς ως **LZ**). Συνδυάζει την απλότητα της ομαδοποίησης αρχείων του TAR με το υψηλό λόγο συμπίεσης του LZ, καθιστώντας το ιδανικό για αρχεία αντιγράφων ασφαλείας, διανομή πακέτων ή οποιοδήποτε σενάριο όπου η εύρος ζώνης είναι σημαντικό.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για .NET;
Το Aspose.Zip παρέχει μια καθαρά διαχειριζόμενη,跨平台 λύση που δημιουργεί αρχεία TAR, ZIP και LZ‑βασισμένα αρχεία χωρίς εξωτερικά εργαλεία, υποστηρίζει πάνω από 30 μορφές αρχείων και προσφέρει έως και 30 % καλύτερη συμπίεση σε μεγάλα αρχεία, ενώ παρέχει λεπτομερείς εξαιρέσεις για αξιόπιστο χειρισμό σφαλμάτων. Επίσης ενσωματώνεται άψογα με τα πλαίσια καταγραφής του .NET και παρέχει λεπτομερή γεγονότα προόδου.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- **Aspose.Zip for .NET** βιβλιοθήκη – κατεβάστε την από [εδώ](https://releases.aspose.com/zip/net/).  
- Ένας φάκελος που περιέχει τα αρχεία που θέλετε να αρχειοθετήσετε. Η διαδρομή σε αυτόν τον φάκελο θα αποθηκευτεί στη μεταβλητή `dataDir` (θα τη ρυθμίσετε στο Βήμα 3).

## Εισαγωγή Namespaces
Προσθέστε τα απαιτούμενα namespaces ώστε ο μεταγλωττιστής να γνωρίζει πού βρίσκονται οι κλάσεις που θα χρησιμοποιήσουμε.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Πώς να δημιουργήσετε αρχείο tar.lz – Οδηγός βήμα‑βήμα

### Βήμα 1: Συμπίεση ενός μόνο αρχείου
Το πρώτο παράδειγμα δείχνει το πιο βασικό σενάριο – προσθήκη ενός αρχείου σε ένα αρχείο TAR και στη συνέχεια αποθήκευση ως αρχείο **tar.lz**.

Η κλάση `TarArchive` αντιπροσωπεύει ένα κοντέινερ TAR που μπορεί να περιέχει πολλαπλά αρχεία σε ένα ενιαίο αρχείο.  

**Εξήγηση**

- `new TarArchive()` δημιουργεί ένα κενό κοντέινερ TAR.  
- `CreateEntry` προσθέτει το αρχείο `alice29.txt` από το `dataDir` σας.  
- `SaveLzipped` γράφει το αρχείο στο δίσκο και εφαρμόζει συμπίεση LZ, παράγοντας το `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Βήμα 2: Συμπίεση πολλαπλών αρχείων σε ένα αρχείο
Συχνά θα χρειαστεί να ομαδοποιήσετε πολλά αρχεία μαζί. Απλώς καλέστε το `CreateEntry` για κάθε αρχείο πριν την αποθήκευση. Αυτό δείχνει **add files to tar lz** και αποτελεσματικά **compress multiple files tar**.

**Εξήγηση**

- Ο κώδικας ακολουθεί το ίδιο μοτίβο με το Βήμα 1, αλλά προσθέτει μια δεύτερη καταχώρηση (`lcet10.txt`).  
- Μπορείτε να επαναλάβετε το `CreateEntry` όσες φορές χρειάζεται· η βιβλιοθήκη διαχειρίζεται αυτόματα τη εσωτερική δομή TAR.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Βήμα 3: Καθορίστε τον φάκελο εγγράφων σας
Αντικαταστήστε το placeholder με την πραγματική διαδρομή όπου βρίσκονται τα πηγαία αρχεία σας. Αυτή η διαδρομή χρησιμοποιείται από τα παραπάνω παραδείγματα.

**Εξήγηση**

- Ορίστε το `dataDir` σε μια πλήρη διαδρομή φακέλου, π.χ., `@"C:\\MyFiles\\"`.  
- Η διατήρηση του φακέλου σε μια μεταβλητή κάνει τον κώδικα επαναχρησιμοποιήσιμο και πιο εύκολο στη συντήρηση.

```csharp
string dataDir = "Your Document Directory";
```

## Συνηθισμένα προβλήματα & αντιμετώπιση
| Σύμπτωμα | Πιθανή αιτία | Διόρθωση |
|---------|--------------|-----|
| `FileNotFoundException` κατά την εκτέλεση του δείγματος | `dataDir` δείχνει σε έναν ανύπαρκτο φάκελο ή το όνομα αρχείου είναι λανθασμένο | Επαληθεύστε τη διαδρομή και τα ονόματα αρχείων· χρησιμοποιήστε `Path.Combine` για ασφάλεια. |
| Το αρχείο εξόδου είναι **0 KB** | `archive.SaveLzipped` κλήθηκε πριν προστεθούν καταχωρήσεις | Βεβαιωθείτε ότι τουλάχιστον μία κλήση `CreateEntry` προηγείται του `SaveLzipped`. |
| Η συμπίεση φαίνεται αργή | Μεγάλα αρχεία με προεπιλεγμένο μέγεθος buffer | Σκεφτείτε την επεξεργασία αρχείων σε τμήματα ή τη χρήση ασύγχρονης I/O αν η απόδοση είναι κρίσιμη. |

## Συμπέρασμα
Τώρα ξέρετε **πώς να συμπιέσετε αρχεία tar.lz** χρησιμοποιώντας το Aspose.Zip για .NET, είτε εργάζεστε με ένα μόνο έγγραφο είτε με μια συλλογή αρχείων. Αυτό το **παράδειγμα συμπίεσης tar.lz** δείχνει έναν καθαρό, έτοιμο για παραγωγή τρόπο να **δημιουργήσετε αρχείο tar lz** που μπορεί να μεταφερθεί ή να αποθηκευτεί εύκολα. Μπορείτε να συμπιέσετε αρχεία σε tar.lz χρησιμοποιώντας το ίδιο API καλώντας το `SaveLzipped` μετά την προσθήκη όλων των επιθυμητών καταχωρήσεων.

## Συχνές Ερωτήσεις

**Q:** Μπορώ να συμπιέσω αρχεία οποιουδήποτε μεγέθους χρησιμοποιώντας το Aspose.Zip για .NET;  
**A:** Ναι, η βιβλιοθήκη διαχειρίζεται τόσο μικρά όσο και πολύ μεγάλα αρχεία· απλώς βεβαιωθείτε ότι έχετε επαρκή μνήμη και χώρο δίσκου για τη προσωρινή δομή TAR.

**Q:** Είναι ο κώδικας συμβατός με την τελευταία έκδοση του Aspose.Zip;  
**A:** Το παράδειγμα στοχεύει στην τρέχουσα έκδοση· διατηρείτε πάντα το πακέτο NuGet ενημερωμένο για διορθώσεις σφαλμάτων και νέες λειτουργίες.

**Q:** Υπάρχουν ζητήματα αδειοδότησης;  
**A:** Απαιτείται εμπορική άδεια για χρήση σε παραγωγή. Δείτε τις λεπτομέρειες αδειοδότησης στην [ιστοσελίδα Aspose](https://purchase.aspose.com/buy).

**Q:** Μπορώ να το χρησιμοποιήσω σε εμπορικό έργο;  
**A:** Απόλυτα – μόλις έχετε έγκυρη άδεια, μπορείτε να ενσωματώσετε τη βιβλιοθήκη σε οποιαδήποτε εμπορική εφαρμογή.

**Q:** Πού μπορώ να λάβω βοήθεια αν αντιμετωπίσω προβλήματα;  
**A:** Επισκεφθείτε το [φόρουμ Aspose.Zip](https://forum.aspose.com/c/zip/37) για υποστήριξη από την κοινότητα και επίσημη βοήθεια.

---

**Last Updated:** 2026-07-04  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Δημιουργία αρχείου tar και προσθήκη αρχείων σε tar με το Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Πώς να συμπιέσετε tar και να δημιουργήσετε TarBz2 με το Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Προσθήκη αρχείων σε tar και δημιουργία αρχείου tarxz με το Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}