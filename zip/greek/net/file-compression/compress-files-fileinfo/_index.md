---
date: 2026-07-18
description: Μάθετε πώς να προσθέσετε φάκελο σε zip και να προσθέσετε αρχεία σε zip
  χρησιμοποιώντας το Aspose.Zip για .NET. Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να
  συμπιέσετε αρχεία με FileInfo σε έργα ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Συμπίεση αρχείων με χρήση FileInfo
og_description: Προσθήκη φακέλου σε zip χρησιμοποιώντας το Aspose.Zip για .NET. Μάθετε
  πώς να δημιουργήσετε αρχείο zip, να προσθέσετε αρχεία σε zip και να συμπιέσετε φακέλους
  αποδοτικά σε ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Προσθήκη φακέλου σε Zip – Συμπίεση αρχείων με Aspose.Zip για .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Προσθήκη φακέλου σε αρχείο Zip χρησιμοποιώντας το Aspose.Zip για .NET – Συμπίεση
  αρχείων με FileInfo
url: /el/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Φακέλου σε Zip Χρησιμοποιώντας το Aspose.Zip για .NET

## Εισαγωγή

Αν χρειάζεστε να **add folder to zip** προγραμματιστικά, το Aspose.Zip for .NET προσφέρει ένα καθαρό, υψηλής απόδοσης API που λειτουργεί σε οποιαδήποτε .NET (συμπεριλαμβανομένου του ASP.NET) εφαρμογή. Σε αυτό το tutorial θα περάσουμε από τη συμπίεση αρχείων με την κλάση `FileInfo`, θα σας δείξουμε πώς να **add files to zip**, και θα εξηγήσουμε γιατί αυτή η προσέγγιση είναι ιδανική για σύγχρονα .NET έργα. Θα καλύψουμε επίσης τα ακριβή βήματα για **add folder to zip** ώστε να μπορείτε να συσσωρεύετε ολόκληρους καταλόγους σε μία ενέργεια. Ας ξεκινήσουμε!

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο πιο εύκολος τρόπος για τη δημιουργία ενός zip αρχείου;** Χρησιμοποιήστε την κλάση `Archive` του Aspose.Zip μαζί με αντικείμενα `FileInfo`.  
- **Μπορώ να προσθέσω πολλά αρχεία ταυτόχρονα;** Ναι – απλώς δημιουργήστε ένα `FileInfo` για κάθε αρχείο και καλέστε το `CreateEntry`.  
- **Χρειάζομαι ειδική άδεια για το ASP.NET;** Απαιτείται εμπορική άδεια Aspose.Zip για παραγωγή· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.  
- **Ποιες εκδόσεις του .NET υποστηρίζονται;** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 και .NET 5–10.  
- **Είναι το API thread‑safe;** Ναι, εφόσον κάθε νήμα εργάζεται με τη δική του παρουσία `Archive`.

## Τι είναι ένα Zip Αρχείο και γιατί να δημιουργηθεί;
Ένα zip αρχείο συγκεντρώνει ένα ή περισσότερα αρχεία σε ένα ενιαίο, συμπιεσμένο κοντέινερ. Αυτό μειώνει το χώρο αποθήκευσης, επιταχύνει τις μεταφορές δικτύου και απλοποιεί τη διανομή. Είτε παραδίδετε αρχεία καταγραφής, εξάγετε αναφορές, είτε πακετάρετε πόρους για έναν πελάτη, η γνώση του **how to create zip archive** προγραμματιστικά είναι μια πολύτιμη δεξιότητα για κάθε .NET προγραμματιστή.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για την προσθήκη αρχείων σε Zip;
Το Aspose.Zip παρέχει μια καθαρή λύση .NET που εξαλείφει εξωτερικές εξαρτήσεις, ενώ δίνει στους προγραμματιστές λεπτομερή έλεγχο πάνω στη συμπίεση, την κωδικοποίηση και την ασφάλεια. Υποστηρίζει μεγάλα αρχεία, προστασία με κωδικό πρόσβασης και λειτουργεί σταθερά σε όλες τις υποστηριζόμενες εκδόσεις .NET, καθιστώντας το αξιόπιστη επιλογή τόσο για παλαιές όσο και για σύγχρονες εφαρμογές.  

- **Zero external dependencies** – καθαρή υλοποίηση .NET.  
- **Full control over compression level and encoding** (ASCII, UTF‑8, κ.λπ.).  
- **Supports files larger than 4 GB** και προστασία με κωδικό.  
- **Consistent API across 50+ .NET versions** – από .NET Framework 2.0 έως .NET 10.  

## Προαπαιτούμενα

Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε:

1. Εγκατεστημένο **Aspose.Zip for .NET**. Κατεβάστε το τελευταίο πακέτο από τη [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Έναν φάκελο στον υπολογιστή σας που περιέχει τα αρχεία που θέλετε να συμπιέσετε (π.χ., `alice29.txt` και `fields.c`).  

## Εισαγωγή Namespaces

Σε οποιοδήποτε αρχείο C# όπου θα δουλέψετε με zip αρχεία, προσθέστε τις παρακάτω δηλώσεις `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Αυτά τα namespaces σας δίνουν πρόσβαση στην κλάση `Archive`, τις επιλογές αποθήκευσης και τις τυπικές βοηθητικές λειτουργίες I/O.

## Οδηγός Βήμα‑βήμα

### Βήμα 1: Ρύθμιση του Καταλόγου Εγγράφων

Πρώτα, ορίστε το φάκελο που περιέχει τα αρχεία προέλευσης. Αντικαταστήστε το placeholder με την απόλυτη ή σχετική διαδρομή στο σύστημά σας:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Χρησιμοποιήστε το `Path.Combine` για να δημιουργήσετε διαδρομές με δια‑πλατφορμικό τρόπο.

### Βήμα 2: Άνοιγμα Αρχείου Zip για Εγγραφή

Δημιουργήστε ένα `FileStream` που δείχνει στο αρχείο zip εξόδου. Η ροή ανοίγεται σε λειτουργία **Create**, η οποία αντικαθιστά οποιοδήποτε υπάρχον αρχείο με το ίδιο όνομα:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Βήμα 3: Προετοιμασία Αντικειμένων `FileInfo` για Κάθε Αρχείο Πηγής

`FileInfo` παρέχει στο Aspose.Zip άμεση πρόσβαση στα φυσικά αρχεία στο δίσκο. Δημιουργήστε μία παρουσία ανά αρχείο που θέλετε να συμπιέσετε:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** Αποφεύγει τη φόρτωση ολόκληρου του αρχείου στη μνήμη, κάτι που είναι ιδιαίτερα χρήσιμο για μεγάλα αρχεία.

### Βήμα 4: Δημιουργία του Archive και Προσθήκη Εγγραφών

Η κλάση `Archive` είναι το κεντρικό αντικείμενο του Aspose.Zip που αντιπροσωπεύει ένα zip κοντέινερ στη μνήμη. Δημιουργήστε ένα αντικείμενο `Archive`, στη συνέχεια καλέστε το `CreateEntry` για κάθε `FileInfo`. Το πρώτο όρισμα είναι το όνομα που θα έχει το αρχείο μέσα στο zip, το δεύτερο όρισμα είναι το πηγαίο `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

Η μέθοδος `CreateEntry` προσθέτει μια νέα εγγραφή αρχείου στο archive, συνδέοντας το όνομα της εγγραφής με το πηγαίο `FileInfo`, ώστε τα δεδομένα να ρέουν απευθείας από το δίσκο όταν το archive αποθηκευτεί.

### Βήμα 5: Αποθήκευση του Zip Archive με την Επιθυμητή Κωδικοποίηση

Τέλος, αποθηκεύστε το archive στο `FileStream` που ανοίξατε νωρίτερα. Εδώ χρησιμοποιούμε κωδικοποίηση ASCII για τα ονόματα των εγγραφών, αλλά μπορείτε να μεταβείτε σε UTF‑8 εάν τα ονόματα αρχείων σας περιέχουν μη‑ASCII χαρακτήρες:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Όταν τα μπλοκ `using` ολοκληρωθούν, οι ροές κλείνουν αυτόματα και το αρχείο zip είναι έτοιμο για χρήση.

## Πώς να Προσθέσετε Φάκελο σε Zip Χρησιμοποιώντας το Aspose.Zip;

Φορτώστε τον στόχο κατάλογο, απαριθμήστε κάθε αρχείο και προσθέστε το καθένα με μια σχετική διαδρομή που περιλαμβάνει το όνομα του φακέλου. Αυτή η προσέγγιση σας επιτρέπει να **add folder to zip** χωρίς να απαριθμήσετε χειροκίνητα κάθε αρχείο. Διατηρώντας την ιεραρχία φακέλων στα ονόματα των εγγραφών, το τελικό archive μπορεί να αποσυμπιεστεί με τη διατήρηση της αρχικής δομής καταλόγου, κάτι που είναι ουσιώδες για πολλές περιπτώσεις ανάπτυξης.

1. Χρησιμοποιήστε το `DirectoryInfo` για να δείξετε στον φάκελο που θέλετε να συμπιέσετε.  
2. Καλέστε το `GetFiles("*", SearchOption.AllDirectories)` για να ανακτήσετε όλα τα αρχεία αναδρομικά.  
3. Για κάθε αρχείο, δημιουργήστε ένα `FileInfo` και καλέστε το `CreateEntry` με μια διαδρομή όπως `"MyFolder/Report.pdf"`.

## Συχνά Προβλήματα & Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Κενό αρχείο zip** | `FileInfo` δείχνει σε μη‑υπάρχουσα διαδρομή | Επαληθεύστε το `dataDir` και τα ονόματα αρχείων· χρησιμοποιήστε το `File.Exists` για έλεγχο πριν τη δημιουργία εγγραφών. |
| **Λανθασμένη κωδικοποίηση ονόματος αρχείου** | Χρήση της προεπιλεγμένης κωδικοποίησης με μη‑ASCII ονόματα | Ορίστε `Encoding = Encoding.UTF8` στο `ArchiveSaveOptions`. |
| **OutOfMemoryException σε μεγάλα αρχεία** | Φόρτωση ολόκληρου του αρχείου στη μνήμη | `FileInfo` ρέει το αρχείο· βεβαιωθείτε ότι δεν διαβάζετε το αρχείο σε πίνακα byte αλλού. |
| **Άρνηση πρόσβασης** | Η εφαρμογή δεν έχει δικαίωμα εγγραφής στον φάκελο εξόδου | Εκτελέστε την εφαρμογή με τα κατάλληλα δικαιώματα ή επιλέξτε έναν φάκελο με δυνατότητα εγγραφής. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσθέσω ολόκληρο φάκελο σε ένα zip αρχείο με μία κλήση;**  
A: Δεν υπάρχει μέθοδος μονής κλήσης, αλλά η απαρίθμηση αρχείων με `DirectoryInfo` και η προσθήκη καθενός μέσω `CreateEntry` επιτυγχάνει το ίδιο αποτέλεσμα αποδοτικά.

**Q: Υποστηρίζει το Aspose.Zip προστασία με κωδικό;**  
A: Ναι, μπορείτε να ορίσετε κωδικό πρόσβασης στο αντικείμενο `Archive` πριν την αποθήκευση για κρυπτογράφηση ολόκληρου του archive.

**Q: Πόσο μεγάλο zip αρχείο μπορεί να διαχειριστεί το Aspose.Zip;**  
A: Η βιβλιοθήκη επεξεργάζεται αρχεία μεγαλύτερα από 4 GB και μπορεί να δημιουργήσει αρχεία archive που υπερβαίνουν τα 10 GB χωρίς να φορτώνει ολόκληρο το archive στη μνήμη.

**Q: Είναι το API συμβατό με .NET 6 και .NET 8;**  
A: Απόλυτα. Το Aspose.Zip υποστηρίζει .NET 5 έως .NET 10, καλύπτοντας όλες τις τρέχουσες εκδόσεις LTS.

**Q: Ποια επίπεδα συμπίεσης είναι διαθέσιμα;**  
A: Μπορείτε να επιλέξετε `CompressionLevel.NoCompression`, `Fast`, `Normal` ή `Maximum` για να ισορροπήσετε την ταχύτητα και το μέγεθος.

## Περαιτέρω Πόροι

- Κατεβάστε το τελευταίο πακέτο Aspose.Zip: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Αγοράστε άδεια για παραγωγική χρήση: [purchase page](https://purchase.aspose.com/buy)  
- Λάβετε βοήθεια από την κοινότητα: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Δοκιμάστε το Aspose.Zip δωρεάν: [free trial here](https://releases.aspose.com/)  
- Λάβετε προσωρινή άδεια για αξιολόγηση: [this link](https://purchase.aspose.com/temporary-license/)

## Συμπέρασμα

Τώρα γνωρίζετε **how to add folder to zip** και **how to create zip archive** αρχεία χρησιμοποιώντας το Aspose.Zip for .NET, πώς να **add files to zip**, και γιατί αυτή η μέθοδος είναι ιδανική για ASP.NET και άλλες .NET εφαρμογές. Πειραματιστείτε με διαφορετικά επίπεδα συμπίεσης, κωδικοποιήσεις και επιλογές κρυπτογράφησης για να προσαρμόσετε το archive στις ακριβείς ανάγκες σας. Καλή συμπίεση!

---

**Τελευταία Ενημέρωση:** 2026-07-18  
**Δοκιμάστηκε Με:** Aspose.Zip for .NET 24.12 (latest)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικές Εκπαιδεύσεις

- [Πώς να Συμπιέσετε Φάκελο Χρησιμοποιώντας το Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Συμπίεση πολλαπλών αρχείων c# – Απρόσκοπτη Συμπίεση με Aspose.Zip for .NET](/zip/net/file-compression/compress-multiple-files/)
- [Δημιουργία Zip Archive .NET – Συμπίεση Αρχείων με Aspose.Zip](/zip/net/file-compression/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}