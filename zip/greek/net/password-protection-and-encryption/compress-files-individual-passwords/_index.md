---
title: Ασφαλής συμπίεση αρχείων σε .NET με Aspose.Zip
linktitle: Συμπίεση αρχείων με μεμονωμένους κωδικούς πρόσβασης
second_title: Aspose.Zip .NET API για συμπίεση και αρχειοθέτηση αρχείων
description: Μάθετε πώς να βελτιώσετε την ασφάλεια αρχείων σε εφαρμογές .NET! Ακολουθήστε τον βήμα προς βήμα οδηγό μας για τη συμπίεση αρχείων με μεμονωμένους κωδικούς πρόσβασης χρησιμοποιώντας το Aspose.Zip για .NET.
type: docs
weight: 16
url: /el/net/password-protection-and-encryption/compress-files-individual-passwords/
---

## Εισαγωγή

Στον κόσμο της ανάπτυξης .NET, η αποτελεσματική διαχείριση και συμπίεση αρχείων είναι ένα κρίσιμο έργο. Το Aspose.Zip for .NET παρέχει μια ισχυρή λύση για τη συμπίεση αρχείων, προσφέροντας διάφορες δυνατότητες για τη βελτίωση των εφαρμογών σας. Ένα αξιοσημείωτο χαρακτηριστικό είναι η δυνατότητα συμπίεσης αρχείων με μεμονωμένους κωδικούς πρόσβασης, παρέχοντας ένα πρόσθετο επίπεδο ασφάλειας. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία συμπίεσης αρχείων με μεμονωμένους κωδικούς πρόσβασης χρησιμοποιώντας το Aspose.Zip για .NET.

## Προαπαιτούμενα

Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Aspose.Zip για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Zip στο έργο σας .NET. Μπορείτε να βρείτε την απαραίτητη τεκμηρίωση[εδώ](https://reference.aspose.com/zip/net/).

-  Λήψη: Εάν δεν το έχετε κάνει ήδη, κάντε λήψη της βιβλιοθήκης Aspose.Zip για .NET από[αυτός ο σύνδεσμος](https://releases.aspose.com/zip/net/).

- Κατάλογος εγγράφων: Προετοιμάστε έναν κατάλογο που περιέχει τα αρχεία που θέλετε να συμπιέσετε.

## Εισαγωγή χώρων ονομάτων

Στο έργο σας .NET, φροντίστε να εισαγάγετε τους απαραίτητους χώρους ονομάτων:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Βήμα 1: Ορίστε τη διαδρομή καταλόγου πόρων

Καθορίστε τη διαδρομή προς τον κατάλογο πόρων όπου βρίσκονται τα αρχεία σας.

```csharp
string dataDir = "Your Document Directory";
```

## Βήμα 2: Συμπίεση αρχείων με μεμονωμένους κωδικούς πρόσβασης

Τώρα, ας συμπιέσουμε αρχεία με μεμονωμένους κωδικούς πρόσβασης. Θα χρησιμοποιήσουμε τρία δείγματα αρχείων (`alice29.txt`, `asyoulik.txt` , και`fields.c`) με διακριτούς κωδικούς πρόσβασης για το καθένα.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Συμπιέστε κάθε αρχείο με έναν ξεχωριστό κωδικό πρόσβασης
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Αποθηκεύστε τα συμπιεσμένα αρχεία
        archive.Save(zipFile);
    }
}
```

## συμπέρασμα

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να συμπιέσετε αρχεία με μεμονωμένους κωδικούς πρόσβασης χρησιμοποιώντας το Aspose.Zip για .NET. Αυτή η δυνατότητα προσθέτει ένα επιπλέον επίπεδο ασφάλειας στα συμπιεσμένα αρχεία σας, διασφαλίζοντας την εμπιστευτικότητα.

## Συχνές Ερωτήσεις (Συχνές Ερωτήσεις)

### Μπορώ να χρησιμοποιήσω διαφορετικές μεθόδους κρυπτογράφησης για κάθε αρχείο;
Ναι, το Aspose.Zip για .NET σάς επιτρέπει να χρησιμοποιείτε διαφορετικές μεθόδους κρυπτογράφησης για κάθε αρχείο κατά τη συμπίεση.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση;
 Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή του Aspose.Zip για .NET[εδώ](https://releases.aspose.com/).

### Πώς μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα;
 Επισκέψου το[Aspose.Zip φόρουμ](https://forum.aspose.com/c/zip/37) για βοήθεια από την κοινότητα και υποστήριξη Aspose.

### Πού μπορώ να βρω αναλυτική τεκμηρίωση για το Aspose.Zip για .NET;
 Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/zip/net/).

### Μπορώ να αγοράσω μια προσωρινή άδεια για δοκιμαστικούς σκοπούς;
 Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
