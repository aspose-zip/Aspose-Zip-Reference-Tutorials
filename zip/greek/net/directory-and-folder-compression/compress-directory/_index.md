---
date: 2026-05-30
description: Μάθετε πώς να συμπιέσετε φάκελο με Aspose.Zip για .NET, δημιουργήστε
  αρχείο zip αποδοτικά και μειώστε τον χώρο αποθήκευσης στις εφαρμογές .NET σας.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Πώς να συμπιέσετε έναν φάκελο
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να συμπιέσετε φάκελο χρησιμοποιώντας Aspose.Zip για .NET
url: /el/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Συμπιέσετε Φάκελο Χρησιμοποιώντας το Aspose.Zip για .NET

Σε αυτό το tutorial θα ανακαλύψετε **πώς να συμπιέσετε φάκελο** γρήγορα και αξιόπιστα με το Aspose.Zip για .NET. Είτε δημιουργείτε μια επιτραπέζια εφαρμογή, μια υπηρεσία βασισμένη στο cloud, είτε ένα αυτοματοποιημένο script backup, η συμπίεση ενός φακέλου σε αρχείο ZIP μπορεί να μειώσει δραστικά τις απαιτήσεις αποθήκευσης και να επιταχύνει τις μεταφορές δικτύου. Θα περάσουμε βήμα-βήμα, θα εξηγήσουμε γιατί κάθε γραμμή είναι σημαντική και θα επισημάνουμε κοινά προβλήματα ώστε να εφαρμόσετε την τεχνική με αυτοπεποίθηση.

## Γρήγορες Απαντήσεις
- **Τι κάνει το Aspose.Zip;** Παρέχει ένα απλό .NET API για δημιουργία και εξαγωγή αρχείων ZIP χωρίς εξωτερικές εξαρτήσεις.  
- **Πόσο χρόνο απαιτεί η υλοποίηση;** Συνήθως λιγότερο από 10 λεπτά για μια βασική συμπίεση φακέλου.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1, και .NET 5‑10.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται εμπορική άδεια για χρήση σε παραγωγή.  
- **Μπορώ να συμπιέσω πολλαπλούς φακέλους ταυτόχρονα;** Απόλυτα—χρησιμοποιήστε τη μέθοδο `CreateEntries` σε οποιαδήποτε συλλογή `DirectoryInfo` για **συμπίεση πολλαπλών φακέλων** σε μία εκτέλεση.  

`CreateEntries` προσθέτει όλα τα αρχεία από έναν κατάλογο στο αρχείο.

## Τι είναι το «πώς να συμπιέσετε φάκελο»;

Η συμπίεση ενός φακέλου σημαίνει ότι παίρνουμε κάθε αρχείο και υπο‑φάκελο μέσα σε έναν δεδομένο κατάλογο και τα συσκευάζουμε σε ένα ενιαίο αρχείο ZIP. Αυτό μειώνει το συνολικό μέγεθος, διατηρεί την αρχική ιεραρχία και καθιστά πιο εύκολη τη μεταφορά ή την αποθήκευση των δεδομένων. Το προκύπτον ZIP μπορεί να ανοιχθεί σε οποιαδήποτε πλατφόρμα χωρίς ειδικό λογισμικό, και διατηρεί τη δομή του φακέλου ώστε όταν εξαχθεί η αρχική διάταξη να αποκατασταθεί ακριβώς όπως ήταν.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για αυτήν την εργασία;

Το Aspose.Zip σας επιτρέπει να **δημιουργήσετε αρχείο zip** απευθείας από κώδικα .NET με ένα συνεπές API σε όλα τα υποστηριζόμενα runtime. Φορτώστε την κλάση `Archive`, προσθέστε καταχωρήσεις, ορίστε `CompressionLevel`, προαιρετικά ορίστε κωδικό πρόσβασης, και καλέστε `Save`. Η βιβλιοθήκη επεξεργάζεται φακέλους με χιλιάδες αρχεία σε λιγότερο από ένα δευτερόλεπτο σε τυπικό υλικό, και υποστηρίζει πάνω από 50 διαφορετικές μορφές συμπίεσης και αλγορίθμους κρυπτογράφησης.

## Προαπαιτούμενα

- **Aspose.Zip for .NET** – κατεβάστε το [εδώ](https://releases.aspose.com/zip/net/) ή [εδώ](https://releases.aspose.com/zip/net).  
- **Development Environment** – Visual Studio, Rider, ή οποιοδήποτε IDE που υποστηρίζει C#.  
- **Document Directory** – αντικαταστήστε το `"Your Document Directory"` στον κώδικα με τη διαδρομή του φακέλου που θέλετε να συμπιέσετε.  
- **Reference Documentation** – συμβουλευτείτε τα επίσημα έγγραφα [εδώ](https://reference.aspose.com/zip/net/).

## Εισαγωγή Namespaces

Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων. Αυτοί σας δίνουν πρόσβαση στις βασικές κλάσεις συμπίεσης.

```csharp
using Aspose.Zip;
using System.IO;
```

## Πώς να Συμπιέσετε Φάκελο με το Aspose.Zip

Παρακάτω υπάρχει ένα απλό παράδειγμα που δείχνει **πώς να συμπιέσετε φάκελο**. Το ίδιο μοτίβο μπορεί να επεκταθεί για **συμπίεση πολλαπλών αρχείων .net** ή για δημιουργία προσαρμοσμένων δομών αρχείων.

### Βήμα 1: Αρχικοποίηση του Καταλόγου Εγγράφων σας

Ορίστε τη μεταβλητή `dataDir` στη διαδρομή του καταλόγου που θέλετε να συμπιέσετε.

```csharp
string dataDir = "Your Document Directory";
```

### Βήμα 2: Δημιουργία Αρχείων ZIP Εξόδου

Ανοίξτε δύο αντικείμενα `FileStream` για τα αρχεία ZIP εξόδου. Αυτό δείχνει πώς μπορείτε να δημιουργήσετε περισσότερα από ένα αρχεία από την ίδια πηγή—χρήσιμο για εκδόσεις backup.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Βήμα 3: Συμπίεση του Καταλόγου

Η κλάση `Archive` αντιπροσωπεύει ένα αρχείο ZIP και παρέχει μεθόδους για προσθήκη καταχωρήσεων και αποθήκευση του αρχείου. Χρησιμοποιήστε την για να προσθέσετε κάθε καταχώρηση από τον στόχο φάκελο. Το παράδειγμα χρησιμοποιεί έναν δείγμα φάκελο με όνομα **CanterburyCorpus**, αλλά μπορείτε να τον δείξετε σε οποιονδήποτε κατάλογο.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Συμβουλή:** Αν χρειάζεστε **να δημιουργήσετε αρχείο zip .net** με συγκεκριμένο επίπεδο συμπίεσης, ορίστε `archive.CompressionLevel` πριν καλέσετε `Save`.

## Συχνά Προβλήματα και Λύσεις

| Σύμπτωμα | Πιθανή Αιτία | Διόρθωση |
|----------|--------------|----------|
| Κενό αρχείο ZIP | `dataDir` δείχνει σε λάθος φάκελο ή λείπει η τελική κάθετος | Επαληθεύστε τη διαδρομή και βεβαιωθείτε ότι ο φάκελος περιέχει αρχεία |
| `UnauthorizedAccessException` | Η εφαρμογή δεν διαθέτει δικαιώματα συστήματος αρχείων | Εκτελέστε το Visual Studio ως διαχειριστής ή χορηγήστε δικαιώματα ανάγνωσης/εγγραφής |
| Μεγάλη χρήση μνήμης για τεράστιους καταλόγους | Φόρτωση όλων των καταχωρήσεων στη μνήμη ταυτόχρονα | Χρησιμοποιήστε `Archive.CreateEntryFromFile` σε βρόχο για να μεταφέρετε τα αρχεία ατομικά |

## Συχνές Ερωτήσεις (Πρόσθετες)

**Q: Μπορώ να προσθέσω κωδικό πρόσβασης στο αρχείο ZIP;**  
A: Ναι. Ορίστε `archive.Password = "yourPassword";` πριν καλέσετε `Save`.

**Q: Πώς μπορώ να συμπεριλάβω μόνο ορισμένους τύπους αρχείων;**  
A: Φιλτράρετε τη συλλογή `DirectoryInfo` με `GetFiles("*.txt")` ή παρόμοιο πριν καλέσετε `CreateEntries`.

**Q: Υπάρχει τρόπος να ενημερώσω ένα υπάρχον ZIP χωρίς να το δημιουργήσω ξανά;**  
A: Το Aspose.Zip υποστηρίζει σταδιακές ενημερώσεις μέσω `Archive.UpdateEntry`.

## Συχνές Ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Zip για .NET τόσο σε εμπορικά όσο και σε προσωπικά έργα;

A1: Ναι, το Aspose.Zip για .NET αδειοδοτείται για εμπορική και προσωπική χρήση.

### Ε2: Υπάρχει διαθέσιμη δωρεάν δοκιμή;

A2: Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή [εδώ](https://releases.aspose.com/zip/net).

### Ε3: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Zip για .NET;

A3: Επισκεφθείτε το [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) για υποστήριξη της κοινότητας ή σκεφτείτε την αγορά μιας [temporary license](https://purchase.aspose.com/temporary-license/) για εξειδικευμένη βοήθεια.

### Ε4: Υπάρχουν άλλα παραδείγματα και tutorials διαθέσιμα;

A4: Ναι, η [documentation](https://reference.aspose.com/zip/net/) περιέχει ολοκληρωμένα παραδείγματα και tutorials.

### Ε5: Μπορώ να αγοράσω το Aspose.Zip για .NET;

A5: Φυσικά, μπορείτε να κάνετε αγορά [εδώ](https://purchase.aspose.com/buy).

## Συμπέρασμα

Τώρα έχετε ένα πλήρες, έτοιμο για παραγωγή μοτίβο για **πώς να συμπιέσετε φάκελο** χρησιμοποιώντας το Aspose.Zip για .NET. Εκμεταλλευόμενοι την κλάση `Archive` της βιβλιοθήκης, μπορείτε να **δημιουργήσετε αρχείο zip**, να ορίσετε προσαρμοσμένο `CompressionLevel`, να προσθέσετε προστασία με κωδικό πρόσβασης, και ακόμη να **συμπιέσετε πολλαπλούς φακέλους** σε μία εκτέλεση—κάτι ιδανικό για αυτοματοποίηση εργασιών backup φακέλων. Πειραματιστείτε με το API για να προσθέσετε κρυπτογράφηση, διαχωρισμό αρχείων ή άμεση ροή σε αποθήκευση cloud, και θα έχετε μια ισχυρή λύση για κάθε ανάγκη συμπίεσης .NET.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
