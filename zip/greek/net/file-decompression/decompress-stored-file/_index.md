---
date: 2026-06-14
description: Μάθετε πώς να δημιουργήσετε zip χωρίς συμπίεση και να εξάγετε πολλαπλά
  zip αρχεία χρησιμοποιώντας το Aspose.Zip για .NET. Αυτός ο οδηγός καλύπτει πώς να
  ανοίξετε zip, να διαβάσετε την καταχώρηση zip και τα βήματα εξαγωγής zip σε C#.
keywords:
- create zip without compression
- extract multiple zip files
- c# extract zip
- aspose zip extract
- zip archive store method
linktitle: Αποσυμπίεση αποθηκευμένου αρχείου
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  headline: Create Zip Without Compression & Decompress Files – Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression and extract multiple zip
    files using Aspose.Zip for .NET. This guide covers how to open zip, read zip entry,
    and C# extract zip steps.
  name: Create Zip Without Compression & Decompress Files – Aspose.Zip
  steps:
  - name: '1: Opening the Zip File'
    text: The `Archive` object represents the opened ZIP and gives you access to each
      entry via the `Entries` collection.
  - name: '2: Creating Extracted Files'
    text: Here we **read zip entry** 0, copy its bytes to a new file, and close the
      streams automatically thanks to the `using` statements.
  - name: '3: Repeating the Process for Another File'
    text: By iterating over `archive.Entries`, you can **extract multiple zip files**
      (or multiple entries) with just a few lines of code.
  type: HowTo
- questions:
  - answer: It stores files in a ZIP using the *store* method, leaving the data unchanged.
    question: What does “create zip without compression” mean?
  - answer: Aspose.Zip for .NET provides a clean API for the *store* method and extraction.
    question: Which library supports this in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license to run the sample?
  - answer: Yes – the tutorial demonstrates how to **extract multiple zip files**
      in a loop.
    question: Can I extract several files at once?
  - answer: .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Δημιουργία Zip χωρίς συμπίεση & αποσυμπίεση αρχείων – Aspose.Zip
url: /el/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποσυμπίεση ενός Αποθηκευμένου Αρχείου χρησιμοποιώντας το Aspose.Zip για .NET

## Εισαγωγή

Σε σύγχρονες εφαρμογές .NET, η **create zip without compression** είναι μια χρήσιμη τεχνική όταν χρειάζεστε ταχύτατη αρχειοθέτηση και δεν σας ενδιαφέρει το μέγεθος του αρχείου. Το Aspose.Zip για .NET σας επιτρέπει να δημιουργήσετε τέτοια αρχεία με τη μέθοδο “store‑method” και αργότερα να **extract multiple zip files** με λίγες μόνο γραμμές κώδικα C#. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα από το άνοιγμα ενός ZIP, την ανάγνωση μιας καταχώρησης zip, και την εκτέλεση μιας **C# extract zip** λειτουργίας.

## Γρήγορες Απαντήσεις
- **What does “create zip without compression” mean?** Αποθηκεύει αρχεία σε ένα ZIP χρησιμοποιώντας τη μέθοδο *store*, αφήνοντας τα δεδομένα αμετάβλητα.  
- **Which library supports this in .NET?** Το Aspose.Zip για .NET παρέχει ένα καθαρό API για τη μέθοδο *store* και την εξαγωγή.  
- **Do I need a license to run the sample?** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Can I extract several files at once?** Ναι – το tutorial δείχνει πώς να **extract multiple zip files** σε βρόχο.  
- **What .NET versions are supported?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10.

## Τι είναι το “create zip without compression”

Η μέθοδος συμπίεσης `store` λέει στη μορφή ZIP να παραλείψει οποιοδήποτε βήμα μείωσης δεδομένων. **create zip without compression** επομένως παράγει ένα μεγαλύτερο αρχείο, αλλά η λειτουργία είναι σχεδόν άμεση και τα αρχικά bytes παραμένουν αμετάβλητα – ιδανικό για ήδη συμπιεσμένα μέσα (JPEG, MP3) ή όταν χρειάζεστε καθοριστικό περιεχόμενο αρχείων.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για .NET;

Το Aspose.Zip δίνει στους προγραμματιστές ακριβή έλεγχο της συμπίεσης, ένα ευέλικτο API για ανάγνωση και εγγραφή καταχωρήσεων, και συμβατότητα πολλαπλών πλατφορμών σε όλες τις εκδόσεις .NET. Διαχειρίζεται μεγάλα αρχεία αποδοτικά, διατηρεί τη χρήση μνήμης χαμηλή, και υποστηρίζει πάνω από 50 μορφές, καθιστώντας το ιδανικό για απλές και σύνθετες εργασίες αρχειοθέτησης.

- **Full control** στο επίπεδο συμπίεσης – επιλέξτε *store* ή *deflate* ανά καταχώρηση.  
- **Simple, fluent API** για ανάγνωση καταχωρήσεων, άνοιγμα αρχείων zip και εξαγωγή δεδομένων.  
- **Cross‑platform** υποστήριξη για .NET Framework, .NET Core, και .NET 5+.  
- **Handles large archives** έως 2 GB χωρίς να φορτώνεται ολόκληρο το αρχείο στη μνήμη.  
- **Quantified claim:** Το Aspose.Zip υποστηρίζει **50+ μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί **αρχεία πολλαπλών εκατοντάδων σελίδων** διατηρώντας τη χρήση μνήμης κάτω από 100 MB.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

- **Aspose.Zip for .NET** – κατεβάστε το από την επίσημη ιστοσελίδα **[here](https://releases.aspose.com/zip/net/)**.  
- Έναν λειτουργικό **document directory** στον υπολογιστή σας όπου τα δείγματα αρχείων θα διαβαστούν και θα γραφτούν.

## Εισαγωγή Namespaces

Πρώτα, εισάγετε τους χώρους ονομάτων που περιέχουν τις βασικές κλάσεις που θα χρησιμοποιήσουμε:

```csharp
using Aspose.Zip;
using System.IO;
```

## Πώς δημιουργώ ένα αρχείο zip χωρίς συμπίεση σε C#;

`Archive` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο ZIP στο Aspose.Zip.

Για να δημιουργήσετε ένα αποθηκευμένο (stored) αρχείο, φορτώστε κάθε αρχείο προέλευσης, δημιουργήστε ένα `Archive`, και προσθέστε κάθε αρχείο με `CompressionMethod.Store`. Δεν απαιτούνται επιπλέον παράμετροι συμπίεσης, και η βιβλιοθήκη γράφει τα ακατέργαστα bytes απευθείας, με αποτέλεσμα μια σχεδόν άμεση λειτουργία ενώ διατηρεί τα αρχικά δεδομένα αμετάβλητα.

## Πώς να δημιουργήσετε Zip χωρίς Συμπίεση

Πρώτα χρειαζόμαστε ένα αρχείο ZIP που χρησιμοποιεί τη μέθοδο **store** (δηλαδή χωρίς συμπίεση). Ο παρακάτω κώδικας δείγματος δημιουργεί ένα τέτοιο αρχείο και παρέχεται από το Aspose.Zip ως βοηθητική μέθοδος. Η εκτέλεσή του θα δημιουργήσει το `StoreMultipleFilesWithoutCompression_out.zip` στον φάκελο εγγράφων σας.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** Η βοηθητική μέθοδος ορίζει εσωτερικά `CompressionMethod.Store` για κάθε καταχώρηση, διασφαλίζοντας ότι το αρχείο δημιουργείται χωρίς καμία συμπίεση δεδομένων.

## Πώς μπορώ να ανοίξω ένα αρχείο zip και να εξάγω πολλαπλές καταχωρήσεις χρησιμοποιώντας το Aspose.Zip;

`Archive` αντιπροσωπεύει ένα ανοιχτό αρχείο ZIP και παρέχει πρόσβαση στις καταχωρήσεις του μέσω της συλλογής `Entries`.

Ανοίξτε το αρχείο περνώντας τη διαδρομή του αρχείου στον κατασκευαστή `Archive`, στη συνέχεια επαναλάβετε μέσω `archive.Entries`. Για κάθε καταχώρηση, ανοίξτε το ρεύμα της με `entry.Open()`, αντιγράψτε τα δεδομένα σε ένα αρχείο προορισμού χρησιμοποιώντας ένα buffered stream, και κλείστε αυτόματα τα ρεύματα με `using`. Αυτή η προσέγγιση εξάγει αποδοτικά όλες τις καταχωρήσεις χωρίς να φορτώνεται ολόκληρο το αρχείο στη μνήμη.

## Πώς να ανοίξετε Zip και να εξάγετε πολλαπλά αρχεία

Τώρα που έχουμε ένα αποθηκευμένο ZIP, ας δούμε **how to open zip** και να εξάγουμε τα αρχεία.

### Βήμα 2.1: Άνοιγμα του αρχείου Zip

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

Το αντικείμενο `Archive` αντιπροσωπεύει το ανοιχτό ZIP και σας δίνει πρόσβαση σε κάθε καταχώρηση μέσω της συλλογής `Entries`.

### Βήμα 2.2: Δημιουργία Εξαγόμενων Αρχείων

```csharp
        using (var extracted = File.Create(dataDir + "alice_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[0].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
```

Εδώ **read zip entry** 0, αντιγράφουμε τα bytes του σε ένα νέο αρχείο, και κλείνουμε τα ρεύματα αυτόματα χάρη στις δηλώσεις `using`.

### Βήμα 2.3: Επανάληψη της διαδικασίας για άλλο αρχείο

```csharp
        using (var extracted = File.Create(dataDir + "asyoulik_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[1].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
    }
}
```

Με την επανάληψη μέσω `archive.Entries`, μπορείτε να **extract multiple zip files** (ή πολλαπλές καταχωρήσεις) με λίγες μόνο γραμμές κώδικα.

## Συχνά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| `FileNotFoundException` κατά το άνοιγμα του ZIP | Λάθος διαδρομή `dataDir` | Επαληθεύστε ότι το `dataDir` τελειώνει με κάθετο ή χρησιμοποιήστε `Path.Combine`. |
| Το εξαγόμενο αρχείο είναι κενό | Το buffer δεν εκκενώθηκε | Το μπλοκ `using` εκκαθαρίζει αυτόματα· βεβαιωθείτε ότι διαβάζετε το ρεύμα μέχρι το `bytesRead` να είναι 0 (όπως φαίνεται). |
| Αδυναμία άδειας | Εκτέλεση χωρίς έγκυρη άδεια | Εφαρμόστε δοκιμαστική ή μόνιμη άδεια πριν από την ανάπτυξη. |

## Συχνές Ερωτήσεις

### Q1: Είναι το Aspose.Zip για .NET συμβατό με όλα τα .NET frameworks;

**A:** Ναι, το Aspose.Zip για .NET λειτουργεί με .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10, παρέχοντάς σας ευελιξία σε όλες τις πλατφόρμες.

### Q2: Μπορώ να χρησιμοποιήσω το Aspose.Zip για .NET σε εμπορικά και μη‑εμπορικά έργα;

**A:** Ναι, μπορείτε να το χρησιμοποιήσετε σε οποιοδήποτε τύπο έργου. Δείτε τις λεπτομέρειες αδειοδότησης στη **[purchase page](https://purchase.aspose.com/buy)** για περισσότερες πληροφορίες.

### Q3: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Zip για .NET;

**A:** Επισκεφθείτε το **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** όπου η κοινότητα και οι μηχανικοί της Aspose απαντούν σε ερωτήσεις.

### Q4: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Zip για .NET;

**A:** Απόλυτα – μπορείτε να κατεβάσετε μια δοκιμαστική έκδοση **[here](https://releases.aspose.com/)** και να αξιολογήσετε όλες τις δυνατότητες χωρίς κόστος.

### Q5: Μπορώ να αποκτήσω προσωρινή άδεια για δοκιμαστικούς σκοπούς;

**A:** Ναι, μια προσωρινή άδεια είναι διαθέσιμη μέσω **[this link](https://purchase.aspose.com/temporary-license/)** για βραχυπρόθεσμη αξιολόγηση.

### Q6: Πώς διαβάζω μια καταχώρηση zip χωρίς να εξάγω ολόκληρο το αρχείο;

**A:** Χρησιμοποιήστε `archive.Entries[index].Open()` για να αποκτήσετε ένα ρεύμα για μια συγκεκριμένη καταχώρηση, στη συνέχεια διαβάστε μόνο τα bytes που χρειάζεστε – ακριβώς όπως φαίνεται στα αποσπάσματα κώδικα.

### Q7: Ποιος είναι ο καλύτερος τρόπος για **extract multiple zip files** σε βρόχο;

**A:** Επαναλάβετε μέσω `archive.Entries` με έναν βρόχο `foreach`, ανοίξτε το ρεύμα κάθε καταχώρησης και γράψτε το στην τοποθεσία προορισμού. Αυτή η προσέγγιση αντικατοπτρίζει το μοτίβο που παρουσιάζεται στα Βήματα 2.2 και 2.3.

## Συμπέρασμα

Η κατανόηση του **create zip without compression** και της επακόλουθης διαδικασίας εξαγωγής είναι ουσιώδης για εφαρμογές .NET υψηλής απόδοσης. Το Aspose.Zip για .NET σας παρέχει ένα καθαρό, διαισθητικό API για **how to open zip**, την ανάγνωση κάθε **zip entry**, και την εκτέλεση μιας **C# extract zip** λειτουργίας με ελάχιστο κώδικα. Ακολουθώντας αυτόν τον οδηγό, έχετε μάθει πώς να δημιουργήσετε ένα αποθηκευμένο αρχείο, να το ανοίξετε και να εξάγετε τα περιεχόμενά του αποδοτικά.

---

**Τελευταία Ενημέρωση:** 2026-06-14  
**Δοκιμή Με:** Aspose.Zip for .NET 24.12  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Aspose.Zip for .NET - Προστασία κωδικού σε αρχείο Zip & Αποθήκευση πολλαπλών αρχείων χωρίς συμπίεση](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Δημιουργία αρχείου Zip .NET – Συμπίεση αρχείων με Aspose.Zip](/zip/net/file-compression/)
- [Πώς να αποσυμπιέσετε αρχεία με Aspose.Zip για .NET](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}