---
date: 2026-06-29
description: Μάθετε πώς να συμπιέσετε φάκελο σε 7z με Aspose.Zip for .NET, καλύπτοντας
  μεθόδους συμπίεσης Seven Zip όπως LZMA2, BZip2 και Store. Ιδανικό για τη δημιουργία
  αρχείων 7z προγραμματιστικά.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip με Διάφορες Μεθόδους Συμπίεσης
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να Συμπιέσετε Φάκελο σε 7z – Aspose.Zip for .NET Οδηγός
url: /el/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Συμπιέσετε Φάκελο σε 7z – Aspose.Zip for .NET Tutorial

## Εισαγωγή

Αν χρειάζεστε να **συμπιέσετε φάκελο σε 7z** αρχεία προγραμματιστικά σε μια εφαρμογή .NET, βρίσκεστε στο σωστό μέρος. Το Aspose.Zip for .NET καθιστά εύκολο να δημιουργήσετε αρχεία Seven Zip με οποιονδήποτε από τους υποστηριζόμενους αλγόριθμους συμπίεσης, είτε θέλετε να συσκευάσετε ολόκληρο κατάλογο για διανομή είτε απλώς χρειάζεστε μια αξιόπιστη **seven zip archive .net** λύση. Σε αυτόν τον οδηγό θα περάσουμε από τρεις δημοφιλείς μεθόδους συμπίεσης — LZMA2, BZip2 και Store (χωρίς συμπίεση) — και θα σας δείξουμε ακριβώς πώς να παραγάγετε ένα αρχείο 7z με λίγες γραμμές κώδικα C#.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Aspose.Zip for .NET παρέχει το πιο πλήρες σύνολο λειτουργιών Seven Zip.  
- **Ποια μέθοδος συμπίεσης δίνει το καλύτερο λόγο συμπίεσης;** Η LZMA2 συνήθως προσφέρει τη μεγαλύτερη συμπίεση για μικτά δεδομένα.  
- **Μπορώ να δημιουργήσω ένα 7z χωρίς καμία συμπίεση;** Ναι — χρησιμοποιήστε τη μέθοδο Store (χωρίς συμπίεση).  
- **Χρειάζομαι άδεια για ανάπτυξη;** Διατίθεται δωρεάν δοκιμή· απαιτείται άδεια για χρήση σε παραγωγή.  
- **Είναι συμβατό με .NET 6/7;** Απόλυτα — Aspose.Zip υποστηρίζει .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 και .NET 5–10.

## Ποιες είναι οι Μέθοδοι Συμπίεσης Seven Zip;

Seven Zip υποστηρίζει αρκετούς αλγόριθμους, καθένας βελτιστοποιημένος για διαφορετικά σενάρια. **LZMA2** προσφέρει το υψηλότερο λόγο συμπίεσης (συχνά 30‑40 % μικρότερο από το BZip2), **BZip2** παρέχει σταθερή συμπίεση με ευρύτερη υποστήριξη παλαιών εργαλείων, και **Store** απλώς αρχειοθετεί τα αρχεία χωρίς να τα μειώνει, διατηρώντας τέλεια τις αρχικές χρονικές σήμανσεις.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις C# και Visual Studio.  
- Τη βιβλιοθήκη Aspose.Zip for .NET εγκατεστημένη. Κατεβάστε την από την επίσημη σελίδα λήψης **[εδώ](https://releases.aspose.com/zip/net/)**.  
- Έναν φάκελο (`dataDir`) που περιέχει τα αρχεία που θέλετε να αρχειοθετήσετε.

## Εισαγωγή Ονομάτων Χώρων

Πρώτα, προσθέστε τα απαιτούμενα ονόματα χώρων στο αρχείο C#:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Αυτές οι κλάσεις σας δίνουν πρόσβαση στις ρυθμίσεις συμπίεσης και στη διαχείριση του αρχείου.

## Συμπίεση LZMA2 – Πώς να Δημιουργήσετε ένα 7z με Μέγιστο Λόγο Συμπίεσης

Η κλάση `Archive` αντιπροσωπεύει ένα αρχείο 7z που μπορεί να περιέχει πολλαπλά αρχεία.  
Ο αλγόριθμος LZMA2 παρέχει το υψηλότερο λόγο συμπίεσης μεταξύ των υποστηριζόμενων μεθόδων. Λειτουργεί διαιρώντας την είσοδο σε μπλοκ και εφαρμόζοντας μια εξελιγμένη συμπίεση λεξικού. Στο Aspose.Zip ορίζετε το `CompressionMethod` σε `CompressionMethod.Lzma2` στο αντικείμενο `Archive` πριν προσθέσετε αρχεία.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Συμβουλή:** Η LZMA2 λειτουργεί καλύτερα όταν τα αρχεία προέλευσης είναι μεγαλύτερα από 1 MB. Για πολλά μικρά αρχεία, το BZip2 μπορεί να είναι ταχύτερο.

## Συμπίεση BZip2 – Μια Ισορροπημένη Επιλογή

Η κλάση `Archive` αντιπροσωπεύει ένα αρχείο 7z που μπορεί να περιέχει πολλαπλά αρχεία.  
Το BZip2 προσφέρει σταθερή συμπίεση με καλή συμβατότητα για παλαιότερα εργαλεία. Χρησιμοποιεί τη μεταστροφή Burrows‑Wheeler και την κωδικοποίηση Huffman για μείωση του μεγέθους. Στο Aspose.Zip επιλέγετε `CompressionMethod.BZip2` όταν διαμορφώνετε το αντικείμενο `Archive`, εξισορροπώντας την ταχύτητα και το λόγο συμπίεσης για τα περισσότερα κείμενα και δυαδικά αρχεία.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

Το BZip2 προσφέρει σταθερή συμπίεση διατηρώντας λογική ταχύτητα, καθιστώντας το καλή εναλλακτική όταν η LZMA2 δεν υποστηρίζεται από το περιβάλλον στόχο.

## Store (Χωρίς Συμπίεση) – Όταν το Μέγεθος δεν Μετράει

Η κλάση `Archive` αντιπροσωπεύει ένα αρχείο 7z που μπορεί να περιέχει πολλαπλά αρχεία.  
Η μέθοδος Store δημιουργεί ένα αρχείο χωρίς να συμπιέζει τα δεδομένα. Απλώς αντιγράφει τα αρχικά αρχεία στο κοντέινερ 7z, διατηρώντας χρονικές σήμανσεις και δομή καταλόγου. Για να τη χρησιμοποιήσετε στο Aspose.Zip, ορίστε `CompressionMethod.Store` στο `Archive` πριν προσθέσετε τα αρχεία που θέλετε να συσσωρεύσετε.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Χρησιμοποιήστε τη μέθοδο Store εάν χρειάζεστε απλώς να συσσωρεύσετε αρχεία μαζί χωρίς να αλλάξετε το μέγεθός τους — ιδανική για διατήρηση των αρχικών χρονικών σήμανσεων ή όταν το αρχείο θα αποσυμπιεστεί άμεσα.

## Πώς να προσθέσω αρχεία σε 7z;

Προσθέστε αρχεία σε ένα αρχείο 7z δημιουργώντας μια παρουσία της κλάσης `Archive`, ορίζοντας τη ζητούμενη `CompressionMethod` και καλώντας `AddAllFiles(dataDir)`. Η μέθοδος σαρώει τον καθορισμένο φάκελο αναδρομικά, διατηρώντας την ιεραρχία καταλόγου μέσα στο αρχείο. Αυτή η προσέγγιση σας επιτρέπει να **compress folder to 7z** με μία μόνο γραμμή κώδικα μετά τη αρχική ρύθμιση.

## Συνηθισμένες Περιπτώσεις Χρήσης

| Σενάριο | Συνιστώμενη Μέθοδος |
|----------|--------------------|
| Διανομή μεγάλων εγκαταστάσεων | LZMA2 |
| Κοινοποίηση αρχείων καταγραφής με παλαιά εργαλεία | BZip2 |
| Συσκευασία αρχείων για γρήγορη εξαγωγή | Store (χωρίς συμπίεση) |
| Απαιτείται **compress folder to 7z** σε πραγματικό χρόνο σε μια υπηρεσία web | LZMA2 (για το καλύτερο λόγο) |

## Επίλυση Προβλημάτων & Συμβουλές

- **Λείπουν αρχεία στο αρχείο;** Ελέγξτε ότι το `dataDir` δείχνει στον σωστό κατάλογο και ότι η διαδικασία έχει δικαιώματα ανάγνωσης.  
- **Το αρχείο δεν ανοίγει σε παλαιότερες εκδόσεις 7‑Zip;** Παραμείνετε στο BZip2 ή Store, καθώς η LZMA2 μπορεί να απαιτεί νεότερες βιβλιοθήκες αποσυμπίεσης.  
- **Σημείο συμφόρησης στην απόδοση;** Για τεράστιες συλλογές δεδομένων, σκεφτείτε τη ροή του αρχείου αντί να φορτώνετε όλες τις καταχωρήσεις στη μνήμη.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Zip for .NET με οποιοδήποτε τύπο αρχείου;**  
Α: Ναι, το Aspose.Zip υποστηρίζει ένα ευρύ φάσμα μορφών αρχείων, επιτρέποντάς σας να συμπιέζετε και να αποσυμπιέζετε σχεδόν οποιονδήποτε τύπο αρχείου.

**Ε: Διατίθεται δωρεάν δοκιμή για το Aspose.Zip for .NET;**  
Α: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή **[εδώ](https://releases.aspose.com/)**.

**Ε: Πού μπορώ να βρω τεκμηρίωση για το Aspose.Zip for .NET;**  
Α: Η πλήρης αναφορά API είναι διαθέσιμη **[εδώ](https://reference.aspose.com/zip/net/)**.

**Ε: Πώς μπορώ να αποκτήσω προσωρινές άδειες για το Aspose.Zip for .NET;**  
Α: Προσωρινές άδειες μπορούν να ληφθούν **[εδώ](https://purchase.aspose.com/temporary-license/)**.

**Ε: Πού μπορώ να βρω υποστήριξη για το Aspose.Zip for .NET;**  
Α: Μπορείτε να ζητήσετε υποστήριξη στο **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**Last Updated:** 2026-06-29  
**Tested With:** Aspose.Zip for .NET 24.12  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [συμπίεση αρχείων c# – Δημιουργία αρχείου 7z με Aspose.Zip for .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Πώς να Συμπιέσετε Φάκελο Χρησιμοποιώντας Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Πώς να Συμπιέσετε LZMA στο Aspose.Zip for .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}