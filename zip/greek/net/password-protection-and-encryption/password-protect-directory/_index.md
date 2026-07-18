---
date: 2026-07-18
description: Μάθετε πώς να δημιουργείτε αρχεία zip με προστασία password, να προστατεύετε
  με password φακέλους zip και να αλλάζετε τον password του zip χρησιμοποιώντας το
  Aspose.Zip για .NET.
keywords:
- create password protected zip
- zip folder with password
- how to encrypt zip
- password protect zip folder
- encrypt zip archive c#
lastmod: 2026-07-18
linktitle: Προστασία Καταλόγου με Password
og_description: Δημιουργήστε αρχεία zip με προστασία password για καταλόγους .NET
  χρησιμοποιώντας το Aspose.Zip. Αυτό το step‑by‑step tutorial δείχνει πώς να κρυπτογραφείτε
  φακέλους, να αλλάζετε passwords και να αξιοποιείτε την κρυπτογράφηση AES.
og_image_alt: 'Developer guide: Create password protected zip for .NET directories
  with Aspose.Zip'
og_title: Δημιουργία zip με προστασία password – Aspose.Zip .NET Guide
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to create password protected zip files, password protect
    zip folder, and change zip password using Aspose.Zip for .NET.
  headline: Create password protected zip for .NET directories – Aspose.Zip Tutorial
  type: TechArticle
- questions:
  - answer: Use `TraditionalEncryptionSettings` when creating the `Archive` object,
      then call `CreateEntries` on the target folder.
    question: How do I encrypt a folder with zip using Aspose.Zip?
  - answer: No, the password must be defined at creation time; to change it, recreate
      the archive with a new password.
    question: Can I set a zip folder password after the archive is created?
  - answer: '`AesEncryptionSettings` configures AES‑256 encryption for a ZIP archive.
      Yes, you can switch to `AesEncryptionSettings` for AES‑256 encryption instead
      of the traditional ZipCrypto.'
    question: Does Aspose.Zip support AES encryption for stronger security?
  - answer: Absolutely – the current release works with all modern .NET runtimes.
    question: Is the library compatible with .NET 6 and .NET 7?
  - answer: Aspose.Zip will throw a `PasswordRequiredException`, prompting you to
      supply the correct password.
    question: What happens if I try to open a password‑protected zip without a password?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip encryption
- Aspose.Zip
- .NET compression
- password protected archive
title: Δημιουργία zip με προστασία password για καταλόγους .NET – Aspose.Zip Tutorial
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία zip με προστασία κωδικού πρόσβασης για καταλόγους .NET – Εγχειρίδιο Aspose.Zip

Σε αυτό το εγχειρίδιο θα **δημιουργήσετε zip αρχεία με προστασία κωδικού πρόσβασης** για ολόκληρους καταλόγους χρησιμοποιώντας τη βιβλιοθήκη Aspose.Zip για .NET. Είτε χρειάζεστε **κρυπτογράφηση φακέλου**, ασφαλή αντίγραφα ασφαλείας, είτε απλώς θέλετε να περιορίσετε την πρόσβαση σε ευαίσθητα δεδομένα, αυτός ο οδηγός βήμα‑βήμα σας δείχνει ακριβώς πώς να το κάνετε με καθαρό κώδικα C#. Στο τέλος θα καταλάβετε πώς να προστατεύσετε έναν κατάλογο, να αλλάξετε τους τρόπους κρυπτογράφησης και να αλλάξετε τον κωδικό πρόσβασης ενός υπάρχοντος αρχείου.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη συνιστάται;** Aspose.Zip για .NET  
- **Μπορώ να κρυπτογραφήσω ολόκληρο φάκελο;** Ναι – απλώς δείξτε το API στον φάκελο που θέλετε να συμπιέσετε.  
- **Υποστηρίζεται η αλλαγή κωδικού zip;** Απόλυτα, χρησιμοποιήστε `TraditionalEncryptionSettings`.  
- **Χρειάζεται άδεια για παραγωγή;** Απαιτείται έγκυρη άδεια Aspose.Zip για εμπορική χρήση.  
- **Λειτουργεί με .NET Core/5/6;** Ναι, το API είναι πλήρως συμβατό με σύγχρονες εκδόσεις .NET.  

## Τι είναι η «δημιουργία zip με προστασία κωδικού πρόσβασης»;

Η δημιουργία zip με προστασία κωδικού πρόσβασης σημαίνει συμπίεση αρχείων ή καταλόγων σε αρχείο ZIP ενώ εφαρμόζεται κρυπτογράφηση, ώστε το αρχείο να μπορεί να ανοιχθεί μόνο με τον σωστό κωδικό. Αυτό προστατεύει το περιεχόμενο από μη εξουσιοδοτημένη πρόσβαση και συμμορφώνεται με πολλές κανονιστικές απαιτήσεις προστασίας δεδομένων.

## Πώς να δημιουργήσετε zip με προστασία κωδικού πρόσβασης για έναν κατάλογο

Φορτώστε τον στόχο φάκελο, ρυθμίστε έναν κωδικό με `TraditionalEncryptionSettings` και ρέξτε τα δεδομένα σε νέο αρχείο ZIP – όλα σε λίγες σύντομες εντολές. Το API γράφει κάθε καταχώρηση απευθείας στο ρεύμα εξόδου, έτσι ακόμη και κατάλογοι πολλαπλών γιγαμπάιτ επεξεργάζονται με ελάχιστη χρήση μνήμης.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για προστασία κωδικού πρόσβασης καταλόγου .NET;

Το Aspose.Zip υποστηρίζει **πάνω από 30 αλγόριθμους συμπίεσης και κρυπτογράφησης**, μπορεί να χειριστεί φακέλους μεγαλύτερους από **10 GB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, και προσφέρει τόσο το κλασικό ZipCrypto όσο και τη σύγχρονη κρυπτογράφηση AES‑256. Η βιβλιοθήκη είναι πλήρως thread‑safe, λειτουργεί σε **.NET Framework 4.6+**, **.NET Core 3.1+**, και **.NET 6/7**, και περιλαμβάνει λεπτομερή καταγραφή για να σας βοηθήσει στην αντιμετώπιση προβλημάτων.

## Κοινές περιπτώσεις χρήσης
- **Προστασία αντιγράφων ασφαλείας:** Συμπιέστε έναν φάκελο καθημερινών αντιγράφων ασφαλείας και κλειδώστε τον με ισχυρό κωδικό.  
- **Ασφαλής ανταλλαγή αρχείων:** Στείλτε έναν κωδικό zip σε πελάτη χωρίς να εκθέσετε το περιεχόμενο.  
- **Συμμόρφωση με κανονισμούς:** Αποθηκεύστε προσωπικά δεδομένα (PII) σε κρυπτογραφημένο zip για να τηρήσετε πρότυπα προστασίας δεδομένων.  

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις προγραμματισμού C#.  
- Visual Studio (οποιαδήποτε πρόσφατη έκδοση).  
- Βιβλιοθήκη Aspose.Zip για .NET – κατεβάστε την **[εδώ](https://releases.aspose.com/zip/net/)**.  
- Έναν φάκελο στο δίσκο που θέλετε να προστατέψετε με κωδικό πρόσβασης.

## Εισαγωγή Namespaces
Προσθέστε τα απαιτούμενα namespaces στο αρχείο C# ώστε ο μεταγλωττιστής να γνωρίζει πού βρίσκονται οι κλάσεις του Aspose.Zip.

## Βήμα 1: Ορίστε τη Διαδρομή στον Κατάλογο Πόρων
Καθορίστε τη διαδρομή που δείχνει στον κατάλογο που θέλετε να συμπιέσετε και να προστατέψετε.

## Βήμα 2: Προστασία Καταλόγου με Κωδικό Πρόσβασης
`TraditionalEncryptionSettings` ορίζει τον κωδικό και τον αλγόριθμο κρυπτογράφησης για ένα αρχείο ZIP.  
Χρησιμοποιήστε αυτό το αντικείμενο ρυθμίσεων όταν δημιουργείτε το στιγμιότυπο `Archive` για να εφαρμόσετε προστασία ZipCrypto.

## Βήμα 3: Εξήγηση του Κώδικα
`Archive` αντιπροσωπεύει ένα αρχείο ZIP και παρέχει μεθόδους για προσθήκη καταχωρήσεων και αποθήκευση του αρχείου.

- **Δημιουργία του αρχείου εξόδου:** `File.Open(..., FileMode.Create)` ανοίγει (ή δημιουργεί) το αρχείο ZIP που θα περιέχει τα κρυπτογραφημένα δεδομένα.  
- **Επιλογή του πηγαίου φακέλου:** `new DirectoryInfo(".\\CanterburyCorpus")` λέει στο Aspose.Zip ποιον κατάλογο να συμπιέσει.  
- **Εφαρμογή του κωδικού:** `new TraditionalEncryptionSettings("p@s$")` ορίζει τον κωδικό που θα προστατεύει το αρχείο.  
- **Προσθήκη καταχωρήσεων & αποθήκευση:** `archive.CreateEntries(corpus)` προσθέτει κάθε αρχείο στον φάκελο, και `archive.Save(zipFile)` γράφει το κρυπτογραφημένο ZIP στο δίσκο.  

## Πώς να αλλάξετε τον κωδικό πρόσβασης zip αργότερα;

Για να αλλάξετε τον κωδικό, πρέπει να δημιουργήσετε ξανά το αρχείο επειδή ο κωδικός αποθηκεύεται στην κεντρική κεφαλίδα του καταλόγου. Δημιουργήστε ένα νέο `TraditionalEncryptionSettings` με τον επιθυμητό κωδικό, ανοίξτε το υπάρχον αρχείο, αντιγράψτε τις καταχωρήσεις του σε ένα νέο στιγμιότυπο `Archive` χρησιμοποιώντας τις νέες ρυθμίσεις, και στη συνέχεια αποθηκεύστε το νέο αρχείο. Αυτή η διαδικασία κρυπτογραφεί ξανά όλες τις καταχωρήσεις με τον νέο κωδικό.

## Συμβουλές για ισχυρό κωδικό πρόσβασης φακέλου zip
- Χρησιμοποιήστε συνδυασμό κεφαλαίων, πεζών, αριθμών και συμβόλων.  
- Στοχεύστε τουλάχιστον 12 χαρακτήρες· οι μεγαλύτεροι κωδικοί είναι εκθετικά πιο δύσκολοι στην αποκρυπτογράφηση.  
- Αποφύγετε κοινές λέξεις ή μοτίβα· σκεφτείτε τη χρήση φράσης-κωδικού.

## Κοινά Προβλήματα & Συμβουλές
- **Μεγάλοι φάκελοι:** Το Aspose.Zip ρέει δεδομένα, έτσι η χρήση μνήμης παραμένει κάτω από **150 MB** ακόμη και για καταλόγους 5 GB.  
- **Πολυπλοκότητα κωδικού:** Χρησιμοποιήστε ισχυρό κωδικό (γράμματα, αριθμούς, σύμβολα) για καλύτερη ασφάλεια.  
- **Σφάλματα άδειας:** Βεβαιωθείτε ότι έχετε εφαρμόσει έγκυρο αρχείο άδειας· διαφορετικά η βιβλιοθήκη λειτουργεί σε λειτουργία αξιολόγησης με περιορισμούς.  
- **Ο κωδικός zip δεν αναγνωρίζεται:** Επαληθεύστε ότι χρησιμοποιείτε την ίδια μέθοδο κρυπτογράφησης (`TraditionalEncryptionSettings`) όταν ανοίγετε το αρχείο.

## Συχνές Ερωτήσεις

### Είναι το Aspose.Zip για .NET κατάλληλο για μεγάλους καταλόγους;
Ναι, το Aspose.Zip για .NET έχει σχεδιαστεί για αποτελεσματική διαχείριση μεγάλων καταλόγων, παρέχοντας βέλτιστη απόδοση.

### Μπορώ να αλλάξω τον κωδικό πρόσβασης για έναν ήδη προστατευμένο κατάλογο;
Ναι, μπορείτε να τροποποιήσετε τον κωδικό αλλάζοντας το `TraditionalEncryptionSettings` στον κώδικα ανάλογα.

### Υπάρχουν απαιτήσεις αδειοδότησης για τη χρήση του Aspose.Zip για .NET;
Ναι, απαιτείται έγκυρη άδεια για χρήση του Aspose.Zip για .NET σε παραγωγικό περιβάλλον. Μπορείτε να αποκτήσετε άδεια **[εδώ](https://purchase.aspose.com/buy)**.

### Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Zip για .NET;
Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή **[εδώ](https://releases.aspose.com/)**.

### Πού μπορώ να βρω πρόσθετη υποστήριξη για το Aspose.Zip για .NET;
Μπορείτε να επισκεφθείτε το **[Φόρουμ Aspose.Zip](https://forum.aspose.com/c/zip/37)** για οποιαδήποτε υποστήριξη ή ερώτηση.

## Γρήγορο FAQ (φιλικό προς AI)

**Ε: Πώς κρυπτογραφώ έναν φάκελο με zip χρησιμοποιώντας το Aspose.Zip;**  
Α: Χρησιμοποιήστε `TraditionalEncryptionSettings` κατά τη δημιουργία του αντικειμένου `Archive`, στη συνέχεια καλέστε `CreateEntries` στον στόχο φάκελο.

**Ε: Μπορώ να ορίσω κωδικό zip φακέλου μετά τη δημιουργία του αρχείου;**  
Α: Όχι, ο κωδικός πρέπει να οριστεί κατά τη δημιουργία· για αλλαγή, δημιουργήστε ξανά το αρχείο με νέο κωδικό.

**Ε: Υποστηρίζει το Aspose.Zip κρυπτογράφηση AES για μεγαλύτερη ασφάλεια;**  
Α: Το `AesEncryptionSettings` ρυθμίζει κρυπτογράφηση AES‑256 για ένα αρχείο ZIP. Ναι, μπορείτε να μεταβείτε σε `AesEncryptionSettings` για AES‑256 αντί για το παραδοσιακό ZipCrypto.

**Ε: Είναι η βιβλιοθήκη συμβατή με .NET 6 και .NET 7;**  
Α: Απόλυτα – η τρέχουσα έκδοση λειτουργεί με όλα τα σύγχρονα .NET runtime.

**Ε: Τι συμβαίνει αν προσπαθήσω να ανοίξω ένα zip με προστασία κωδικού χωρίς κωδικό;**  
Α: Το Aspose.Zip θα ρίξει μια `PasswordRequiredException`, ζητώντας τον σωστό κωδικό.

---

**Τελευταία ενημέρωση:** 2026-07-18  
**Δοκιμή με:** Aspose.Zip για .NET (τελευταία έκδοση)  
**Συγγραφέας:** Aspose

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Σχετικά Εγχειρίδια

- [Create Password Protected ZIP with Aspose.Zip for .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Create Password Protected ZIP Files with AES Encryption using Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Aspose.Zip for .NET - Password Protect Zip Archive & Store Multiple Files Without Compression](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}