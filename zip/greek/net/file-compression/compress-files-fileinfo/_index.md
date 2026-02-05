---
date: 2026-02-05
description: Μάθετε πώς να συμπιέζετε πολλαπλά αρχεία C# και να δημιουργείτε αρχείο
  zip .NET χρησιμοποιώντας το Aspose.Zip. Αυτός ο οδηγός βήμα‑βήμα δείχνει τη συμπίεση
  αρχείων με το FileInfo σε έργα ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να συμπιέσετε πολλά αρχεία σε C# χρησιμοποιώντας το Aspose.Zip για .NET
url: /el/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να zip multiple files c# χρησιμοποιώντας Aspose.Zip για .NET

## Εισαγωγή

Αν χρειάζεστε να **zip multiple files c#** προγραμματιστικά, το Aspose.Zip για .NET σας παρέχει ένα καθαρό, υψηλής απόδοσης API που λειτουργεί σε οποιαδήποτε εφαρμογή .NET (συμπεριλαμβανομένου του ASP.NET). Σε αυτό το tutorial θα περάσουμε από τη συμπίεση αρχείων με την κλάση `FileInfo`, θα σας δείξουμε πώς να **add files to zip**, και θα εξηγήσουμε γιατί αυτή η προσέγγιση είναι ιδανική για σύγχρονα έργα .NET. Ας ξεκινήσουμε!

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο πιο εύκολος τρόπος για να δημιουργήσετε ένα zip αρχείο;** Χρησιμοποιήστε την κλάση `Archive` του Aspose.Zip μαζί με αντικείμενα `FileInfo`.  
- **Μπορώ να προσθέσω πολλά αρχεία ταυτόχρονα;** Ναι – απλώς δημιουργήστε ένα `FileInfo` για κάθε αρχείο και καλέστε `CreateEntry`.  
- **Χρειάζομαι ειδική άδεια για ASP.NET;** Απαιτείται εμπορική άδεια Aspose.Zip για παραγωγή· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Το API είναι thread‑safe;** Ναι, εφόσον κάθε νήμα εργάζεται με το δικό του αντικείμενο `Archive`.  
- **Πώς να zip files c# χωρίς να τα φορτώνετε στη μνήμη;** Χρησιμοποιήστε αντικείμενα `FileInfo` – μεταδίδουν τα δεδομένα απευθείας.  

## Πώς να zip multiple files c#
Ένα zip αρχείο ενώνει ένα ή περισσότερα αρχεία σε ένα συμπιεσμένο κοντέινερ. Αυτό μειώνει το χώρο αποθήκευσης, επιταχύνει τις μεταφορές δικτύου και απλοποιεί τη διανομή. Είτε παραδίδετε αρχεία καταγραφής, εξάγετε αναφορές, είτε πακετάρετε πόρους για έναν πελάτη, η γνώση του **how to zip files c#** προγραμματιστικά είναι πολύτιμη δεξιότητα για κάθε προγραμματιστή .NET.

## Γιατί να χρησιμοποιήσετε Aspose.Zip για να προσθέσετε αρχεία σε zip;
- **Zero external dependencies** – καθαρή υλοποίηση .NET.  
- **Full control over compression level and encoding** (ASCII, UTF‑8, κ.λπ.).  
- **Supports large files** (> 4 GB) και προστασία με κωδικό.  
- **Consistent API across .NET Framework, .NET Core, and .NET 5+**.  

## Προαπαιτούμενα

Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε:

1. **Aspose.Zip for .NET** εγκατεστημένο. Κατεβάστε το τελευταίο πακέτο από τη [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Έναν φάκελο στον υπολογιστή σας που περιέχει τα αρχεία που θέλετε να συμπιέσετε (π.χ., `alice29.txt` και `fields.c`).  

## Εισαγωγή Namespaces

Σε οποιοδήποτε αρχείο C# όπου θα δουλεύετε με zip αρχεία, προσθέστε τις παρακάτω δηλώσεις `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Αυτοί οι χώροι ονομάτων σας δίνουν πρόσβαση στην κλάση `Archive`, στις επιλογές αποθήκευσης και στα τυπικά εργαλεία I/O.

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων σας

Πρώτα, ορίστε το φάκελο που περιέχει τα πηγαία αρχεία. Αντικαταστήστε το placeholder με την απόλυτη ή σχετική διαδρομή στο σύστημά σας:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Χρησιμοποιήστε `Path.Combine` για να δημιουργήσετε διαδρομές με τρόπο δια-πλατφορμικό.

### Βήμα 2: Ανοίξτε ένα αρχείο Zip για εγγραφή

Δημιουργήστε ένα `FileStream` που δείχνει στο αρχείο zip εξόδου. Η ροή ανοίγεται σε λειτουργία **Create**, η οποία αντικαθιστά τυχόν υπάρχον αρχείο με το ίδιο όνομα:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Βήμα 3: Προετοιμάστε αντικείμενα `FileInfo` για κάθε αρχείο πηγής

`FileInfo` παρέχει στο Aspose.Zip άμεση πρόσβαση στα φυσικά αρχεία στο δίσκο. Δημιουργήστε μία παρουσία ανά αρχείο που θέλετε να συμπιέσετε:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** Αποφεύγει τη φόρτωση ολόκληρου του αρχείου στη μνήμη, κάτι που είναι ιδιαίτερα χρήσιμο για μεγάλα αρχεία.

### Βήμα 4: Δημιουργήστε το Archive και προσθέστε καταχωρήσεις

Δημιουργήστε ένα αντικείμενο `Archive`, στη συνέχεια καλέστε `CreateEntry` για κάθε `FileInfo`. Το πρώτο όρισμα είναι το όνομα που θα έχει το αρχείο μέσα στο zip, το δεύτερο είναι το πηγαίο `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Βήμα 5: Αποθηκεύστε το Zip Archive με την επιθυμητή κωδικοποίηση

Τέλος, αποθηκεύστε το αρχείο στο `FileStream` που ανοίξατε νωρίτερα. Εδώ χρησιμοποιούμε κωδικοποίηση ASCII για τα ονόματα των καταχωρήσεων, αλλά μπορείτε να μεταβείτε σε UTF‑8 εάν τα ονόματα των αρχείων περιέχουν μη‑ASCII χαρακτήρες:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Όταν τα μπλοκ `using` τερματιστούν, οι ροές κλείνουν αυτόματα και το zip αρχείο είναι έτοιμο για χρήση.

## Συχνά Προβλήματα & Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Empty zip file** | `FileInfo` δείχνει σε μη‑υπάρχουσα διαδρομή | Επαληθεύστε το `dataDir` και τα ονόματα αρχείων· χρησιμοποιήστε `File.Exists` για έλεγχο πριν δημιουργήσετε καταχωρήσεις. |
| **Incorrect filename encoding** | Χρήση της προεπιλεγμένης κωδικοποίησης με ονόματα μη‑ASCII | Ορίστε `Encoding = Encoding.UTF8` στο `ArchiveSaveOptions`. |
| **OutOfMemoryException on large files** | Φόρτωση ολόκληρου του αρχείου στη μνήμη | Το `FileInfo` μεταδίδει το αρχείο· βεβαιωθείτε ότι δεν διαβάζετε το αρχείο σε byte array αλλού. |
| **Permission denied** | Η εφαρμογή δεν έχει δικαίωμα εγγραφής στον φάκελο εξόδου | Εκτελέστε την εφαρμογή με τα κατάλληλα δικαιώματα ή επιλέξτε έναν εγγράψιμο φάκελο. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσθέσω προστασία με κωδικό στο zip αρχείο;**  
A: Ναι. Μετά τη δημιουργία του `Archive`, ορίστε `archive.Password = "yourPassword"` πριν καλέσετε `Save`.

**Q: Είναι δυνατόν να ενημερώσω ένα υπάρχον zip αρχείο;**  
A: Το Aspose.Zip υποστηρίζει το άνοιγμα υπάρχοντος αρχείου με `Archive.Open` και στη συνέχεια την προσθήκη νέων καταχωρήσεων.

**Q: Πώς συμπιέζω αρχεία σε έναν ASP.NET MVC controller;**  
A: Ο ίδιος κώδικας λειτουργεί· απλώς βεβαιωθείτε ότι η ροή εξόδου επιστρέφεται ως `FileResult` στον πελάτη.

**Q: Το Aspose.Zip υποστηρίζει αλγορίθμους κρυπτογράφησης;**  
A: Υποστηρίζει το τυπικό ZipCrypto και την κρυπτογράφηση AES‑256.

**Q: Τι κάνω αν χρειάζεται να συμπιέσω έναν φάκελο αναδρομικά;**  
A: Κάντε βρόχο μέσω `Directory.GetFiles` (και υπο‑φακέλων) και δημιουργήστε ένα `FileInfo` για κάθε αρχείο, στη συνέχεια προσθέστε τα στο archive.

## Υπάρχουσα Ενότητα FAQ (διατηρείται αμετάβλητη)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Συμπέρασμα

Τώρα γνωρίζετε **how to zip multiple files c#** χρησιμοποιώντας Aspose.Zip για .NET, πώς να **add files to zip**, και γιατί αυτή η μέθοδος είναι ιδανική για ASP.NET και άλλες εφαρμογές .NET. Πειραματιστείτε με διαφορετικά επίπεδα συμπίεσης, κωδικοποιήσεις και επιλογές κρυπτογράφησης για να προσαρμόσετε το αρχείο στις ακριβείς ανάγκες σας. Καλή συμπίεση!

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}