---
date: 2026-08-02
description: Πώς να συμπιέσετε φάκελο σε .NET χρησιμοποιώντας το Aspose.Zip – μάθετε
  πώς να συμπιέσετε έναν κατάλογο σε zip και να εξάγετε το zip σε κατάλογο με βήμα‑βήμα
  κώδικα και βέλτιστες πρακτικές.
keywords:
- compress directory to zip
- zip folder programmatically
- extract zip to directory
- extract zip archive .net
- how to zip folder
lastmod: 2026-08-02
linktitle: Αποσυμπίεση Φακέλου
og_description: Πώς να συμπιέσετε φάκελο σε .NET χρησιμοποιώντας το Aspose.Zip. Αυτός
  ο οδηγός σας δείχνει πώς να συμπιέσετε έναν κατάλογο σε zip και να εξάγετε το zip
  σε κατάλογο αποδοτικά.
og_image_alt: Guide showing how to zip folder and unzip archive with Aspose.Zip in
  .NET
og_title: Πώς να Συμπιέσετε Φάκελο – Συμπίεση Καταλόγου με το Aspose.Zip για .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: How to zip folder in .NET using Aspose.Zip – learn to compress directory
    to zip and extract zip to directory with step‑by‑step code and best practices.
  headline: How to Zip Folder – Compress Directory with Aspose.Zip for .NET
  type: TechArticle
- description: How to zip folder in .NET using Aspose.Zip – learn to compress directory
    to zip and extract zip to directory with step‑by‑step code and best practices.
  name: How to Zip Folder – Compress Directory with Aspose.Zip for .NET
  steps:
  - name: Zip folder programmatically
    text: 'The `CompressDirectory` class provides a static `Run` method that creates
      a zip archive from a folder. We’ll create a zip file from the directory you
      plan to decompress later. The `CompressDirectory.Run()` helper does the heavy
      lifting. > **Pro tip:** The `CompressDirectory` sample packs every file '
  - name: extract zip to directory – How to unzip folder in .NET
    text: '#### Step 2.1: Open the Zip File Open the generated archive with a `FileStream`.
      This prepares the file for reading.'
  - name: '2: Create Archive Instance'
    text: Instantiate the `Archive` object, which represents the zip container.
  - name: '3: extract zip archive .net'
    text: Finally, extract the contents to a new folder. This is the **extract zip
      to directory** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip supports all file types—text, binary, images, PDFs, and
      more—because it treats files as byte streams without format restrictions.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Absolutely. It processes multi‑gigabyte archives using less than 10 MB
      of RAM and can compress at speeds exceeding 150 MB/s on a typical server CPU.
    question: Is Aspose.Zip suitable for large‑scale applications?
  - answer: Explore the detailed docs [here](https://reference.aspose.com/zip/net/).
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/).
    question: Can I try Aspose.Zip before purchasing?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community
      help and official assistance.
    question: How can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip folder
- Aspose.Zip
- .NET compression
- file archiving
title: Πώς να Συμπιέσετε Φάκελο – Συμπίεση Καταλόγου με το Aspose.Zip για .NET
url: /el/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Συμπιέσετε Φάκελο – Συμπίεση Καταλόγου με Aspose.Zip για .NET

Αν ψάχνετε για μια σαφή, **compress directory to zip** λύση σε μια εφαρμογή .NET, βρίσκεστε στο σωστό σημείο. Σε αυτό το tutorial θα περάσουμε από όλη τη ροή εργασίας—πρώτα θα **compress directory to zip**, μετά θα σας δείξουμε τα ακριβή βήματα για **extract zip to directory** (δηλαδή πώς να αποσυμπιέσετε φάκελο). Στο τέλος θα έχετε ένα επαναχρησιμοποιήσιμο, προγραμματιστικό μοτίβο για λειτουργίες zip φακέλου που λειτουργεί σε .NET Framework, .NET Core και .NET 5/6+.

## Γρήγορες Απαντήσεις
Η μέθοδος `Archive.ExtractToDirectory` εξάγει όλες τις καταχωρήσεις από ένα zip αρχείο σε έναν καθορισμένο φάκελο.

- **What does “compress directory to zip” mean?** Σημαίνει τη μετατροπή των περιεχομένων ενός φακέλου σε ένα ενιαίο αρχείο .zip.  
- **How do I extract zip to directory?** Χρησιμοποιήστε τη μέθοδο `Archive.ExtractToDirectory` όπως φαίνεται στον οδηγό.  
- **Which .NET versions are supported?** Όλες οι σύγχρονες εκδόσεις .NET Framework, .NET Core και .NET 5/6+.  
- **Is a license required for production?** Ναι, απαιτείται εμπορική άδεια Aspose.Zip για χρήση εκτός δοκιμής.  
- **Can I automate this in CI/CD pipelines?** Απόλυτα—απλώς προσθέστε τον ίδιο κώδικα στα scripts κατασκευής.

## Τι είναι το “how to zip folder”;
**How to zip folder** είναι η διαδικασία λήψης κάθε αρχείου και υποφακέλου μέσα σε έναν κατάλογο και συσκευασίας τους σε ένα ενιαίο συμπιεσμένο .zip αρχείο. Αυτή η λειτουργία μειώνει το μέγεθος αποθήκευσης, επιταχύνει τις μεταφορές δικτύου και δημιουργεί ένα φορητό πακέτο που μπορεί να μετακινηθεί ή να ελεγχθεί εκδοτικά ως μία ενιαία οντότητα.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για .NET;
Το Aspose.Zip παρέχει ένα **pure‑managed** API που δεν απαιτεί εγγενή DLLs, υποστηρίζει **50+** μορφές εισόδου και εξόδου, και μπορεί να διαχειριστεί αρχεία μεγαλύτερα από 2 GB χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Προσφέρει επίσης ενσωματωμένη προστασία με κωδικό πρόσβασης, διαχείριση ονομάτων αρχείων Unicode, και ροή δεδομένων που διατηρεί τη χρήση μνήμης κάτω από 10 MB ακόμη και για αρχεία πολλαπλών gigabyte, καθιστώντας το ιδανικό για σενάρια υψηλής απόδοσης στο διακομιστή.

## Προαπαιτούμενα
- Η βιβλιοθήκη **Aspose.Zip for .NET** εγκατεστημένη (κατεβάστε την [εδώ](https://releases.aspose.com/zip/net/)).  
- Ένας φάκελος στο δίσκο που θέλετε να αρχειοθετήσετε – ορίστε τη διαδρομή του στη μεταβλητή `dataDir`.  
- Περιβάλλον ανάπτυξης .NET (Visual Studio, VS Code ή οποιοδήποτε IDE προτιμάτε).

## Εισαγωγή Ονομάτων Χώρων
Πρώτα, φέρτε τα απαιτούμενα ονόματα χώρων (namespaces) στο πεδίο ορατότητας:

```csharp
using Aspose.Zip;
using System.IO;
```

## compress directory to zip – Οδηγός βήμα‑βήμα

### Βήμα 1: Συμπίεση φακέλου προγραμματιστικά
Η κλάση `CompressDirectory` παρέχει μια στατική μέθοδο `Run` που δημιουργεί ένα zip αρχείο από έναν φάκελο.

Θα δημιουργήσουμε ένα zip αρχείο από τον κατάλογο που σκοπεύετε να αποσυμπιέσετε αργότερα. Η βοηθητική μέθοδος `CompressDirectory.Run()` εκτελεί το βαριά έργο.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** Το παράδειγμα `CompressDirectory` πακετάρει κάθε αρχείο στο `dataDir` στο `CompressDirectory_out.zip`. Μπορείτε να μετονομάσετε το αρχείο εξόδου ώστε να ταιριάζει με τις συμβάσεις ονοματοδότησής σας.

### Βήμα 2: extract zip to directory – Πώς να αποσυμπιέσετε φάκελο σε .NET

#### Βήμα 2.1: Άνοιγμα του Zip Αρχείου
Ανοίξτε το παραγόμενο αρχείο με ένα `FileStream`. Αυτό προετοιμάζει το αρχείο για ανάγνωση.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Βήμα 2.2: Δημιουργία Αντικειμένου Archive
Δημιουργήστε ένα αντικείμενο `Archive`, το οποίο αντιπροσωπεύει το zip κοντέινερ.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Βήμα 2.3: extract zip archive .net
Τέλος, εξάγετε τα περιεχόμενα σε έναν νέο φάκελο. Αυτό είναι το βήμα **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Γιατί Αυτό Είναι Σημαντικό
- **Consistency:** Η χρήση της ίδιας βιβλιοθήκης για τη συμπίεση και την εξαγωγή εγγυάται συμβατές μορφές αρχείων.  
- **Performance:** Το Aspose.Zip ρέει τα δεδομένα αποδοτικά, έτσι ακόμη και αρχεία πολλαπλών gigabyte διαχειρίζονται με χαμηλό φορτίο μνήμης.  
- **Security:** Η ενσωματωμένη υποστήριξη προστασίας με κωδικό σημαίνει ότι μπορείτε να ασφαλίσετε το zip αρχείο χωρίς επιπλέον κώδικα.

## Συνηθισμένες Περιπτώσεις Χρήσης
- **Automated backups** – συμπιέστε έναν φάκελο καταγραφών (logs) κάθε νύχτα και αποθηκεύστε τον σε αποθήκευση cloud.  
- **Deployment packages** – ομαδοποιήστε στατικά web assets πριν τη δημοσίευση σε διακομιστή.  
- **Data exchange** – στείλτε μια συλλογή αρχείων μεταξύ υπηρεσιών ως ένα ενιαίο αρχείο.

## Συνηθισμένα Προβλήματα & Λύσεις
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `UnauthorizedAccessException` when extracting | Ο φάκελος προορισμού είναι μόνο για ανάγνωση ή σε χρήση | Βεβαιωθείτε ότι η διαδρομή προορισμού είναι εγγράψιμη και δεν είναι κλειδωμένη |
| Empty output folder after extraction | Λάθος διαδρομή zip αρχείου προέλευσης | Ελέγξτε ξανά ότι το `dataDir + "CompressDirectory_out.zip"` δείχνει στο σωστό αρχείο |
| Large files cause OutOfMemoryException | Χρήση προεπιλεγμένου μεγέθους buffer σε πολύ μεγάλα αρχεία | Χρησιμοποιήστε `ArchiveOptions` για αύξηση του μεγέθους buffer ή ροή αρχείων σε τμήματα |

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Zip για .NET με οποιοδήποτε τύπο αρχείου;**  
A: Ναι, το Aspose.Zip υποστηρίζει όλους τους τύπους αρχείων—κείμενο, δυαδικά, εικόνες, PDF και άλλα—επειδή αντιμετωπίζει τα αρχεία ως ροές byte χωρίς περιορισμούς μορφής.

**Q: Είναι το Aspose.Zip κατάλληλο για εφαρμογές μεγάλης κλίμακας;**  
A: Απόλυτα. Επεξεργάζεται αρχεία πολλαπλών gigabyte χρησιμοποιώντας λιγότερο από 10 MB RAM και μπορεί να συμπιέσει με ταχύτητες άνω των 150 MB/s σε τυπική CPU διακομιστή.

**Q: Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.Zip για .NET;**  
A: Εξερευνήστε τα λεπτομερή έγγραφα [εδώ](https://reference.aspose.com/zip/net/).

**Q: Μπορώ να δοκιμάσω το Aspose.Zip πριν την αγορά;**  
A: Ναι, μια δωρεάν δοκιμή είναι διαθέσιμη στη [σελίδα λήψης Aspose.Zip](https://releases.aspose.com/).

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Zip για .NET;**  
A: Επισκεφθείτε το [φόρουμ Aspose.Zip](https://forum.aspose.com/c/zip/37) για βοήθεια από την κοινότητα και επίσημη υποστήριξη.

**Τελευταία Ενημέρωση:** 2026-08-02  
**Δοκιμή Με:** Aspose.Zip 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Προσθέσετε Φάκελο σε Zip Χρησιμοποιώντας το Aspose.Zip για .NET – Συμπίεση Αρχείων με FileInfo](/zip/net/file-compression/compress-files-fileinfo/)
- [zip πολλαπλά αρχεία c# – Απλή Συμπίεση με το Aspose.Zip για .NET](/zip/net/file-compression/compress-multiple-files/)
- [Πώς να εξάγετε zip σε φάκελο με το Aspose.Zip για .NET](/zip/net/file-decompression/decompress-compressed-folder-directory/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}