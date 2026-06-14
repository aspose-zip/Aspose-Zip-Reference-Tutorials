---
date: 2026-06-14
description: Μάθετε πώς να εξάγετε zip σε φάκελο χρησιμοποιώντας Aspose.Zip for .NET
  – step‑by‑step guide covering extract password zip, decompress multiple zips, and
  more.
keywords:
- extract zip to folder
- extract password zip
- decompress multiple zips
- extract multiple zip entries
- asp.net zip archive
linktitle: Αποσυμπίεση πολλαπλών αρχείων
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET – step‑by‑step
    guide covering extract password zip, decompress multiple zips, and more.
  headline: How to Extract ZIP Files – extract zip to folder
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET – step‑by‑step
    guide covering extract password zip, decompress multiple zips, and more.
  name: How to Extract ZIP Files – extract zip to folder
  steps:
  - name: '1: Opening the Compressed File'
    text: Open the archive by passing the file path to the `Archive` constructor.
      **`Archive` represents a ZIP archive and provides access to its entries.** This
      call validates the ZIP structure and prepares an enumerable collection of entries.
  - name: '2: Listing Entries and Tracking Progress (Extract Multiple ZIP Entries)'
    text: Iterate through `archive.Entries` to list each file name. Use the `Progress`
      event to report extraction status, which is especially useful for large batches.
      **`Progress` event reports the extraction progress as a percentage.**
  - name: '3: Extracting the First Entry (Extract Specific File Zip)'
    text: To pull a single file, locate the desired entry by name and call `ExtractToFile`.
      **`ExtractToFile` extracts a single entry to a specified file path.** This method
      writes the entry directly to the specified path without extracting the whole
      archive.
  - name: '4: Extracting the Second Entry (Extract ZIP to Folder)'
    text: For full‑folder extraction, invoke `ExtractToDirectory` on the archive object.
      This extracts **all entries** to the target folder while preserving the original
      directory hierarchy inside the ZIP. And there you have it! You've successfully
      **extracted multiple zip entries** using Aspose.Zip for .NET,
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET
    question: What library is best for .NET zip extraction?
  - answer: Yes, iterate over the `Archive` entries collection.
    question: Can I extract multiple zip entries at once?
  - answer: A valid Aspose.Zip license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
    question: Which .NET versions are supported?
  - answer: Absolutely – download it from the Aspose website.
    question: Is there a free trial?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να εξάγετε αρχεία ZIP – extract zip to folder
url: /el/net/file-decompression/decompress-multiple-files/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Εξάγετε Αρχεία ZIP – εξαγωγή zip σε φάκελο

Σε αυτό το ολοκληρωμένο σεμινάριο θα μάθετε **πώς να εξάγετε zip σε φάκελο** χρησιμοποιώντας το Aspose.Zip για .NET. Είτε χρειάζεστε να εξάγετε ένα μόνο αρχείο από ένα αρχείο, είτε να αποσυμπιέσετε δεκάδες ZIP σε παρτίδα, είτε να εργαστείτε με πακέτα προστατευμένα με κωδικό, θα σας καθοδηγήσουμε βήμα προς βήμα—από την εγκατάσταση της βιβλιοθήκης μέχρι τη διαχείριση των ενημερώσεων προόδου—ώστε να διαχειρίζεστε με σιγουριά τα αρχεία ZIP σε οποιαδήποτε εφαρμογή .NET.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη είναι η καλύτερη για εξαγωγή zip σε .NET;** Aspose.Zip for .NET  
- **Μπορώ να εξάγω πολλαπλές καταχωρήσεις zip ταυτόχρονα;** Ναι, επαναλάβετε τη συλλογή καταχωρήσεων `Archive`.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται έγκυρη άδεια Aspose.Zip για χρήση εκτός δοκιμής.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10  
- **Υπάρχει δωρεάν δοκιμή;** Απόλυτα – κατεβάστε την από την ιστοσελίδα της Aspose.

## Πώς να εξάγετε zip σε φάκελο με το Aspose.Zip

Φορτώστε το αρχείο ZIP, επιλέξτε τον φάκελο προορισμού και καλέστε `ExtractToDirectory`. **`ExtractToDirectory` εξάγει όλες τις καταχωρήσεις του αρχείου σε έναν καθορισμένο φάκελο, διατηρώντας τη δομή των εσωτερικών καταλόγων.** Αυτή η εντολή μιας γραμμής εξάγει **όλες τις καταχωρήσεις** διατηρώντας την αρχική ιεραρχία φακέλων, και λειτουργεί για αρχεία έως **5 GB** με κατανάλωση μνήμης μικρότερη από **100 MB**.

Η εξαγωγή ενός αρχείου ZIP σημαίνει το άνοιγμα του συμπιεσμένου πακέτου, ο εντοπισμός κάθε καταχώρησης και η εγγραφή των αποσυμπιεσμένων δεδομένων σε έναν προορισμό (φάκελο ή ροή). Το Fluent API του Aspose.Zip αφαιρεί τις λεπτομέρειες χαμηλού επιπέδου, επιτρέποντάς σας να εστιάσετε στη λογική της επιχείρησης ενώ διατηρείτε τον έλεγχο σε λειτουργίες όπως **εξαγωγή zip με κωδικό** ή η εξαγωγή ενός **συγκεκριμένου αρχείου zip**.

## Γιατί να Χρησιμοποιήσετε το Aspose.Zip για .NET;

Το Aspose.Zip προσφέρει **αξιόπιστη απόδοση**—μπορεί να επεξεργαστεί αρχεία που περιέχουν **πάνω από 10.000 καταχωρήσεις** σε λιγότερο από ένα δευτερόλεπτο σε έναν τυπικό διακομιστή, και μεταδίδει δεδομένα ώστε η χρήση μνήμης να παραμένει κάτω από **150 MB** ακόμη και για αρχεία πολλαπλών gigabyte. Η πλήρης υποστήριξη .NET καλύπτει **.NET Framework 2.0–4.8.1**, **.NET Core 2.0–3.1**, και **.NET 5–10**. Προηγμένα χαρακτηριστικά περιλαμβάνουν παρακολούθηση προόδου, προστασία με κωδικό, και εξαγωγή επιπέδου καταχώρησης, όλα χωρίς εξωτερικά native DLLs.

## Προαπαιτούμενα

- **Aspose.Zip for .NET** – κατεβάστε τη βιβλιοθήκη από [εδώ](https://releases.aspose.com/zip/net/) **ή** από [εδώ](https://releases.aspose.com/zip/net).  
- **Document Directory** – δημιουργήστε έναν φάκελο στο δίσκο που θα λειτουργεί ως βασική διαδρομή για τα αρχεία ZIP προέλευσης και την εξαγόμενη έξοδο.  

Τώρα που το περιβάλλον είναι έτοιμο, ας βουτήξουμε στον κώδικα.

## Εισαγωγή Χώρων Ονομάτων

Οι τύποι `Archive` και σχετιζόμενοι ζουν στο χώρο ονομάτων `Aspose.Zip`. Εισάγετέ το στην αρχή του αρχείου σας ώστε να μπορείτε να αναφέρετε τις κλάσεις χωρίς πλήρη ονομασία.

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Βήμα 1: Δημιουργία Αρχείου ZIP Στυλ .NET (Προαιρετικό)

Αν έχετε ήδη ένα αρχείο ZIP, μπορείτε να παραλείψετε αυτό το βήμα. Διαφορετικά, η δημιουργία ενός αρχείου zip .net είναι απλή και βοηθά στην επίδειξη της πλήρους ροής εξαγωγής.

```csharp
string dataDir = "Your Document Directory";

// Run the compression method
CompressMultipleFiles.Run();
```

## Βήμα 2: Αποσυμπίεση Αρχείων (Πώς να Εξάγετε ZIP)

### Βήμα 2.1: Άνοιγμα του Συμπιεσμένου Αρχείου

Ανοίξτε το αρχείο περνώντας τη διαδρομή του αρχείου στον κατασκευαστή `Archive`. **`Archive` αντιπροσωπεύει ένα αρχείο ZIP και παρέχει πρόσβαση στις καταχωρήσεις του.** Αυτή η κλήση επικυρώνει τη δομή του ZIP και προετοιμάζει μια συλλογή καταχωρήσεων που μπορεί να διαβαστεί.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### Βήμα 2.2: Καταγραφή Καταχωρήσεων και Παρακολούθηση Προόδου (Εξαγωγή Πολλών Καταχωρήσεων ZIP)

Επαναλάβετε μέσω `archive.Entries` για να καταγράψετε κάθε όνομα αρχείου. Χρησιμοποιήστε το γεγονός `Progress` για να αναφέρετε την κατάσταση εξαγωγής, κάτι που είναι ιδιαίτερα χρήσιμο για μεγάλες παρτίδες. **Το γεγονός `Progress` αναφέρει την πρόοδο της εξαγωγής ως ποσοστό.**

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### Βήμα 2.3: Εξαγωγή Πρώτης Καταχώρησης (Εξαγωγή Συγκεκριμένου Αρχείου Zip)

Για να εξάγετε ένα μόνο αρχείο, εντοπίστε την επιθυμητή καταχώρηση με το όνομα και καλέστε `ExtractToFile`. **`ExtractToFile` εξάγει μια μοναδική καταχώρηση σε καθορισμένη διαδρομή αρχείου.** Αυτή η μέθοδος γράφει την καταχώρηση απευθείας στη συγκεκριμένη διαδρομή χωρίς να εξάγει ολόκληρο το αρχείο.

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Read and write data from decompressed stream to the extracting file.
    }
}
```

### Βήμα 2.4: Εξαγωγή Δεύτερης Καταχώρησης (Εξαγωγή ZIP σε Φάκελο)

Για πλήρη εξαγωγή σε φάκελο, καλέστε `ExtractToDirectory` στο αντικείμενο archive. Αυτό εξάγει **όλες τις καταχωρήσεις** στον φάκελο προορισμού διατηρώντας την αρχική ιεραρχία καταλόγου μέσα στο ZIP.

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

Και το έχετε! Έχετε εξάγει με επιτυχία **πολλές καταχωρήσεις zip** χρησιμοποιώντας το Aspose.Zip για .NET, και τώρα ξέρετε πώς να **εξάγετε zip σε φάκελο**, **εξάγετε συγκεκριμένο αρχείο zip**, και ακόμη να διαχειριστείτε **εξαγωγή zip με κωδικό** (παρέχοντας κωδικό στο `ArchiveLoadOptions`).

## Συνηθισμένα Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Δεν δημιουργήθηκαν αρχεία εξόδου** | Λάθος διαδρομή `dataDir` ή έλλειψη δικαιωμάτων εγγραφής | Επαληθεύστε ότι ο φάκελος υπάρχει και η εφαρμογή έχει δικαίωμα εγγραφής. |
| **Η πρόοδος εμφανίζει 0%** | Το μέγεθος της καταχώρησης αναφέρεται ως 0 (κενό αρχείο) | Βεβαιωθείτε ότι το αρχείο ZIP προέλευσης περιέχει δεδομένα· δημιουργήστε ξανά το αρχείο αν χρειάζεται. |
| **Εξαίρεση σε μεγάλα αρχεία** | Ανεπαρκής μνήμη | Χρησιμοποιήστε `ArchiveLoadOptions` με `ReadOnly = true` για να μεταφέρετε τις καταχωρήσεις αντί να τις φορτώνετε όλες ταυτόχρονα. |
| **Αποτυχία ZIP με κωδικό** | Δεν έχει δοθεί κωδικός | Παρέχετε τον κωδικό μέσω `ArchiveLoadOptions.Password = "yourPassword"` για να ενεργοποιήσετε την **εξαγωγή zip με κωδικό**. |

## Συχνές Ερωτήσεις

**Q:** Μπορώ να χρησιμοποιήσω το Aspose.Zip για .NET σε εμπορικά και προσωπικά έργα;  
**A:** Ναι, το Aspose.Zip για .NET μπορεί να χρησιμοποιηθεί σε εμπορικά και προσωπικά έργα. Για λεπτομέρειες άδειας, ανατρέξτε στην [πληροφορία αδειών της Aspose](https://purchase.aspose.com/buy).

**Q:** Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Zip για .NET;  
**A:** Ναι, μπορείτε να δοκιμάσετε δωρεάν το Aspose.Zip για .NET [εδώ](https://releases.aspose.com/zip/net).

**Q:** Πού μπορώ να βρω πρόσθετη υποστήριξη για το Aspose.Zip για .NET;  
**A:** Επισκεφθείτε το [φόρουμ Aspose.Zip](https://forum.aspose.com/c/zip/37) για υποστήριξη κοινότητας και συζητήσεις.

**Q:** Πώς μπορώ να αγοράσω προσωρινή άδεια για το Aspose.Zip για .NET;  
**A:** Αποκτήστε μια προσωρινή άδεια για το Aspose.Zip για .NET [εδώ](https://purchase.aspose.com/temporary-license/).

**Q:** Υπάρχουν συγκεκριμένες απαιτήσεις συστήματος για τη χρήση του Aspose.Zip για .NET;  
**A:** Ανατρέξτε στην [τεκμηρίωση](https://reference.aspose.com/zip/net/) για λεπτομερείς απαιτήσεις συστήματος.

## Συμπέρασμα

Σε αυτό το σεμινάριο καλύψαμε **πώς να εξάγετε zip** αρχεία, δείξαμε την εξαγωγή πολλαπλών καταχωρήσεων zip, και αναδείξαμε τις βέλτιστες πρακτικές για τη χρήση του ισχυρού API του Aspose.Zip. Ακολουθώντας αυτά τα βήματα μπορείτε να διαχειρίζεστε αποτελεσματικά αρχεία ZIP σε οποιαδήποτε εφαρμογή .NET—είτε δημιουργείτε ένα εργαλείο επιφάνειας εργασίας, μια υπηρεσία web, ή έναν αυτοματοποιημένο επεξεργαστή παρτίδας που χρειάζεται να **αποσυμπιέσει πολλαπλά αρχεία zip** ή **εξάγει zip με κωδικό**.

---

**Τελευταία Ενημέρωση:** 2026-06-14  
**Δοκιμή Με:** Aspose.Zip 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Σεμινάρια

- [Πώς να Αποσυμπιέσετε Αρχεία με το Aspose.Zip για .NET](/zip/net/file-decompression/)
- [Πώς να Εξάγετε Zip με Κωδικό Χρησιμοποιώντας το Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [zip πολλαπλά αρχεία c# – Απρόσκοπτη Συμπίεση με το Aspose.Zip για .NET](/zip/net/file-compression/compress-multiple-files/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}