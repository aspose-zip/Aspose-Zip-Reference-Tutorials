---
date: 2026-06-24
description: Μάθετε πώς να συμπιέσετε LZMA στο Aspose.Zip για .NET, βελτιστοποιώντας
  την αποθήκευση και την αποδοτικότητα της μεταφοράς δεδομένων.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Συμπίεση σε Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να συμπιέσετε LZMA στο Aspose.Zip για .NET
url: /el/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Συμπιέσετε LZMA στο Aspose.Zip για .NET

## Εισαγωγή

Σε αυτό το μάθημα, θα μάθετε **πώς να συμπιέζετε LZMA** στο Aspose.Zip για .NET, μια κρίσιμη δεξιότητα για τη βελτιστοποίηση του χώρου αποθήκευσης και τη βελτίωση της αποδοτικότητας της μεταφοράς δεδομένων. Το LZMA (αλγόριθμος Lempel‑Ziv‑Markov chain) προσφέρει αρχεία έως και 70 % μικρότερα σε σύγκριση με το παραδοσιακό ZIP, διατηρώντας ταχύτητα αποσυμπίεσης, καθιστώντας το ιδανικό για σενάρια με περιορισμένο εύρος ζώνης.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Zip for .NET  
- **Ποιος αλγόριθμος καλύπτεται σε αυτόν τον οδηγό;** LZMA compression  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια είναι επαρκής για δοκιμές· πλήρης άδεια απαιτείται για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Συνήθως λιγότερο από 10 λεπτά για ένα βασικό αρχείο.

## Τι είναι η συμπίεση LZMA;

Το LZMA είναι ένας αλγόριθμος συμπίεσης χωρίς απώλειες υψηλής αναλογίας που χρησιμοποιεί συμπίεση λεξικού και κωδικοποίηση εύρους. Μπορεί να μειώσει τα κείμενα κατά 30‑70 % διατηρώντας την ταχύτητα αποσυμπίεσης συγκρίσιμη με το ZIP. Για μεγάλα σύνολα δεδομένων, το LZMA μειώνει το κόστος αποθήκευσης και επιταχύνει τις μεταφορές δικτύου χωρίς να θυσιάζει την ακεραιότητα των δεδομένων.

## Γιατί να χρησιμοποιήσετε Aspose.Zip για LZMA;

Aspose.Zip υποστηρίζει **5 αλγορίθμους συμπίεσης** (ZIP, Deflate, BZIP2, LZMA, και ZSTD) και μπορεί να διαχειριστεί αρχεία έως **4 GB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Η βιβλιοθήκη επεξεργάζεται έγγραφα εκατοντάδων σελίδων σε λιγότερο από **2 δευτερόλεπτα** σε τυπικό διακομιστή, προσφέροντας τόσο απόδοση όσο και κλιμακωσιμότητα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

- Aspose.Zip for .NET: Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Zip είναι εγκατεστημένη. Μπορείτε να βρείτε την τεκμηρίωση [εδώ](https://reference.aspose.com/zip/net/).
- Document Directory: Επιλέξτε ή δημιουργήστε έναν φάκελο που περιέχει τα αρχεία που θέλετε να συμπιέσετε.

## Εισαγωγή Namespaces

Προσθέστε τα απαιτούμενα namespaces στην κορυφή του αρχείου C# ώστε να έχετε πρόσβαση στη λειτουργικότητα LZMA του Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Πώς ορίζω τον φάκελο προέλευσης για τη συμπίεση;

Καθορίστε το φάκελο που περιέχει τα αρχεία που προτίθεστε να αρχειοθετήσετε. Η παροχή ενός αφιερωμένου φακέλου προέλευσης εξασφαλίζει ότι θα επεξεργαστούν μόνο τα επιθυμητά αρχεία, μειώνει τον κίνδυνο συμπερίληψης ανεπιθύμητων δεδομένων και απλοποιεί τη διαχείριση διαδρομών όταν εργάζεστε με πολλαπλές εργασίες συμπίεσης στο ίδιο έργο.

```csharp
string dataDir = "Your Document Directory";
```

## Πώς συμπιέζω ένα αρχείο χρησιμοποιώντας LZMA;

`LzmaArchive` είναι η κλάση του Aspose.Zip για δημιουργία και διαχείριση LZMA αρχείων.

Δημιουργήστε μια παρουσία `LzmaArchive`, ορίστε την ως πηγή το αρχείο και καλέστε `Save` για να δημιουργήσετε το αρχείο `.lzma`. Αυτό το μοτίβο δύο γραμμών εκτελεί ολόκληρη τη ροή εργασίας της συμπίεσης, διαχειρίζεται εσωτερικά τα streams και παράγει ένα συμπαγές αρχείο έτοιμο για διανομή ή αποθήκευση.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Πώς μπορώ να επιβεβαιώσω ότι η συμπίεση ήταν επιτυχής;

`Console.WriteLine` γράφει μια γραμμή κειμένου στην τυπική έξοδο της κονσόλας.

Αφού αποθηκευτεί το αρχείο, εμφανίστε ένα σύντομο μήνυμα επιβεβαίωσης χρησιμοποιώντας `Console.WriteLine`. Αυτή η άμεση ανάδραση βοηθά τους προγραμματιστές να επαληθεύσουν ότι το βήμα της συμπίεσης ολοκληρώθηκε χωρίς σφάλματα, απλοποιεί τον εντοπισμό σφαλμάτων κατά τις αυτοματοποιημένες κατασκευές και παρέχει σαφείς πληροφορίες κατάστασης όταν η διαδικασία ενσωματώνεται σε μεγαλύτερες εφαρμογές ή σενάρια.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Συχνά Προβλήματα και Λύσεις

- **File not found** – Επαληθεύστε ότι η συμβολοσειρά διαδρομής χρησιμοποιεί διπλές ανάστροφες κάθετες (`\\`) ή μια ακριβή συμβολοσειρά (`@"C:\Path"`).  
- **Insufficient memory** – Το Aspose.Zip κάνει streaming των δεδομένων, αλλά εξαιρετικά μεγάλα αρχεία μπορεί να απαιτούν αύξηση του ορίου μνήμης της διεργασίας.  
- **License not applied** – Βεβαιωθείτε ότι καλείτε `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` πριν από οποιαδήποτε λειτουργία του Aspose.Zip.

## Συχνές Ερωτήσεις

**Q: Μπορώ να συμπιέσω πολλά αρχεία σε ένα ενιαίο αρχείο LZMA;**  
A: Ναι. Καλέστε `archive.AddFile()` για κάθε αρχείο πριν εκτελέσετε `archive.Save()`.

**Q: Υπάρχει τρόπος να ορίσω επίπεδο συμπίεσης για το LZMA;**  
A: Η κλάση `LzmaArchive` χρησιμοποιεί το προεπιλεγμένο επίπεδο συμπίεσης, το οποίο προσφέρει καλή ισορροπία μεταξύ ταχύτητας και μεγέθους. Προηγμένες ρυθμίσεις είναι διαθέσιμες μέσω του `LzmaEncoder` εάν χρειάζεστε πιο ακριβή έλεγχο.

**Q: Θα λειτουργεί το παραγόμενο αρχείο .lzma σε πλατφόρμες εκτός των Windows;**  
A: Απόλυτα. Η μορφή LZMA είναι πλατφόρμα‑ανεξάρτητη, έτσι το αρχείο μπορεί να αποσυμπιεστεί σε οποιοδήποτε λειτουργικό σύστημα με εργαλείο συμβατό με LZMA.

**Q: Πώς αποσυμπιέζω ένα αρχείο LZMA χρησιμοποιώντας Aspose.Zip;**  
A: Χρησιμοποιήστε τον κατασκευαστή `LzmaArchive` με τη διαδρομή του αρχείου, στη συνέχεια καλέστε `ExtractToDirectory()` για να εξαγάγετε τα περιεχόμενά του.

**Q: Υποστηρίζει το Aspose.Zip streaming συμπίεση για να αποφευχθεί η φόρτωση ολόκληρων αρχείων στη μνήμη;**  
A: Ναι. Μπορείτε να εργαστείτε με streams περνώντας αντικείμενα `Stream` στις μεθόδους `SetSource()` και `Save()`.

---

**Τελευταία ενημέρωση:** 2026-06-24  
**Δοκιμή με:** Aspose.Zip for .NET (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Συμπιέσετε Αρχεία με Aspose.Zip για .NET](/zip/net/file-compression/compress-file/)
- [Πώς να Ανοίξετε Αρχείο GZip και Άλλες Τεχνικές Συμπίεσης με Aspose.Zip για .NET](/zip/net/other-compression-techniques/)
- [compress files c# – Δημιουργία αρχείου 7z με Aspose.Zip για .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}