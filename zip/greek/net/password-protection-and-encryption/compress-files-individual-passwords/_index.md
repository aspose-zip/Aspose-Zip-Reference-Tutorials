---
date: 2026-05-15
description: Μάθετε πώς να δημιουργείτε zip αρχεία με προστασία κωδικού και να συμπιέζετε
  αρχεία με κωδικούς χρησιμοποιώντας το Aspose.Zip για .NET σε λίγα απλά βήματα.
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: Συμπίεση αρχείων με ξεχωριστούς κωδικούς
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Δημιουργία ZIP με προστασία κωδικού σε .NET με Aspose.Zip
url: /el/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Αρχειοθήκης ZIP με Προστασία Κωδικού σε .NET με Aspose.Zip

## Εισαγωγή

Σε αυτό το μάθημα θα μάθετε πώς να **δημιουργήσετε αρχεία zip με προστασία κωδικού** σε μια εφαρμογή .NET χρησιμοποιώντας το Aspose.Zip. Η ασφαλής συμπίεση είναι απαραίτητη όταν χρειάζεται να μεταφέρετε εμπιστευτικά δεδομένα ή να αποθηκεύετε ευαίσθητα έγγραφα χωρίς να τα εκθέτετε σε μη εξουσιοδοτημένη πρόσβαση.

**Aspose.Zip** είναι μια βιβλιοθήκη .NET που επιτρέπει τη δημιουργία, ανάγνωση και κρυπτογράφηση αρχείων ZIP προγραμματιστικά. Υποστηρίζει κρυπτογράφηση AES‑256 και σας επιτρέπει να εκχωρήσετε έναν μοναδικό κωδικό σε κάθε καταχώρηση μέσα στο αρχείο.

## Γρήγορες Απαντήσεις
- **Τι κάνει το Aspose.Zip;** Δημιουργεί και διαχειρίζεται αρχεία ZIP, συμπεριλαμβανομένης της προστασίας κωδικού ανά αρχείο.  
- **Πόσους κωδικούς μπορώ να εκχωρήσω;** Ένας ξεχωριστός κωδικός ανά αρχείο· απεριόριστες καταχωρήσεις.  
- **Ποιος αλγόριθμος κρυπτογράφησης χρησιμοποιείται;** AES‑256, παρέχοντας ασφάλεια 256‑bit.  
- **Χρειάζομαι άδεια για δοκιμή;** Διατίθεται δωρεάν δοκιμή· απαιτείται άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Προαπαιτούμενα

Πριν ξεκινήσετε το μάθημα, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

- Aspose.Zip για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Zip στο .NET έργο σας. Μπορείτε να βρείτε την απαραίτητη τεκμηρίωση [εδώ](https://reference.aspose.com/zip/net/).

- Λήψη: Εάν δεν το έχετε κάνει ήδη, κατεβάστε τη βιβλιοθήκη Aspose.Zip για .NET από [αυτόν τον σύνδεσμο](https://releases.aspose.com/zip/net/).

- Κατάλογος Εγγράφων: Προετοιμάστε έναν φάκελο που περιέχει τα αρχεία που θέλετε να συμπιέσετε.

## Εισαγωγή Χώρων Ονομάτων

Στο .NET έργο σας, βεβαιωθείτε ότι έχετε εισάγει τους απαραίτητους χώρους ονομάτων:

`ZipFile` είναι η κύρια κλάση του Aspose.Zip για δημιουργία αρχείων ZIP και εκχώρηση ατομικών κωδικών σε κάθε καταχώρηση.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Πώς να δημιουργήσετε αρχεία zip με προστασία κωδικού σε .NET;

Φορτώστε το φάκελο προορισμού, δημιουργήστε ένα αντικείμενο `ZipFile`, προσθέστε κάθε αρχείο με τον δικό του κωδικό και, τέλος, καλέστε `Save` για να γράψετε το αρχείο. Ολόκληρη αυτή η διαδικασία απαιτεί μόνο λίγες γραμμές κώδικα και εγγυάται ότι κάθε καταχώρηση κρυπτογραφείται με τον κωδικό που καθορίζετε.

### Βήμα 1: Ορισμός Διαδρομής Καταλόγου Πόρων

Ορίστε τη διαδρομή του καταλόγου πόρων όπου βρίσκονται τα αρχεία σας.

```csharp
string dataDir = "Your Document Directory";
```

### Βήμα 2: Συμπίεση Αρχείων με Ατομικούς Κωδικούς

Τώρα, ας συμπιέσουμε αρχεία με ατομικούς κωδικούς. Θα χρησιμοποιήσουμε τρία δείγμα αρχεία (`alice29.txt`, `asyoulik.txt` και `fields.c`) με διαφορετικούς κωδικούς για το καθένα.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

## Γιατί να χρησιμοποιήσετε προστασία κωδικού για αρχεία ZIP;

Το Aspose.Zip υποστηρίζει **πάνω από 30 αλγόριθμους συμπίεσης** και μπορεί να κρυπτογραφήσει αρχεία με AES‑256, παρέχοντας έως **256‑bit ασφάλεια**. Μπορεί να επεξεργαστεί αρχεία πολλαπλών εκατοντάδων megabytes χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, καθιστώντας το ιδανικό για σενάρια υψηλής απόδοσης στο διακομιστή. Επιπλέον, η προστασία κωδικού βοηθά στην τήρηση κανονιστικών απαιτήσεων όπως GDPR και HIPAA, διασφαλίζοντας ότι τα ευαίσθητα δεδομένα παραμένουν κρυπτογραφημένα τόσο σε ηρεμία όσο και κατά τη μετάδοση.

## Συμπέρασμα

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να **δημιουργήσετε αρχεία zip με προστασία κωδικού** και **συμπιέσετε αρχεία με κωδικούς** χρησιμοποιώντας το Aspose.Zip για .NET. Αυτή η δυνατότητα προσθέτει ένα επιπλέον επίπεδο ασφαλείας στα συμπιεσμένα αρχεία σας, διασφαλίζοντας την εμπιστευτικότητα και τη συμμόρφωση με τις πολιτικές προστασίας δεδομένων.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω διαφορετικές μεθόδους κρυπτογράφησης για κάθε αρχείο;**  
Α: Ναι, το Aspose.Zip σας επιτρέπει να επιλέξετε τον αλγόριθμο κρυπτογράφησης (π.χ., AES‑256) για κάθε καταχώρηση όταν την προσθέτετε στο αρχείο.

**Ε: Υπάρχει διαθέσιμη έκδοση δοκιμής;**  
Α: Ναι, μπορείτε να αποκτήσετε πρόσβαση στη δωρεάν δοκιμή του Aspose.Zip για .NET [εδώ](https://releases.aspose.com/).

**Ε: Πώς μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα;**  
Α: Επισκεφθείτε το [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) για βοήθεια από την κοινότητα και την υποστήριξη της Aspose.

**Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Zip για .NET;**  
Α: Η τεκμηρίωση είναι διαθέσιμη [εδώ](https://reference.aspose.com/zip/net/).

**Ε: Μπορώ να αγοράσω προσωρινή άδεια για δοκιμαστικούς σκοπούς;**  
Α: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Τελευταία Ενημέρωση:** 2026-05-15  
**Δοκιμή με:** Aspose.Zip 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία Αρχειοθήκης ZIP με Προστασία Κωδικού με Aspose.Zip για .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Προστασία ZIP Αρχείων με Κρυπτογράφηση AES χρησιμοποιώντας Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Συμπίεση Πολλαπλών Αρχείων με Κρυπτογράφηση στο Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}