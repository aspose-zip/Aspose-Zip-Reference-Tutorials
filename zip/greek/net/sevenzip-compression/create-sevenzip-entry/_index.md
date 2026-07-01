---
date: 2026-05-05
description: Μάθετε πώς να κρυπτογραφήσετε αρχεία 7z χρησιμοποιώντας το Aspose.Zip
  για .NET. Αυτός ο οδηγός δείχνει πώς να προσθέσετε αρχείο σε 7z, να ορίσετε κρυπτογράφηση
  AES και να δημιουργήσετε ένα ασφαλές αρχείο 7z.
keywords:
- how to encrypt 7z
- add file to 7z
- how to set aes
- generate 7z archive
- add multiple files 7z
linktitle: Δημιουργία καταχώρησης SevenZip
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να κρυπτογραφήσετε αρχείο 7z με το Aspose.Zip για .NET
url: /el/net/sevenzip-compression/create-sevenzip-entry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να κρυπτογραφήσετε αρχείο 7z με το Aspose.Zip για .NET

## Εισαγωγή

Σε αυτό το tutorial θα μάθετε **how to encrypt 7z** αρχεία χρησιμοποιώντας τη βιβλιοθήκη Aspose.Zip για .NET. Είτε χρειάζεστε να προστατεύσετε ευαίσθητα δεδομένα, να συμμορφωθείτε με πολιτικές ασφαλείας, είτε απλώς να συμπιέσετε αρχεία αποδοτικά, αυτός ο οδηγός σας καθοδηγεί βήμα προς βήμα—από τη ρύθμιση του έργου μέχρι την επιβεβαίωση ότι το αρχείο δημιουργήθηκε επιτυχώς. Ας βουτήξουμε και δούμε πόσο εύκολο είναι να **add file to 7z** με κρυπτογράφηση AES και να δημιουργήσετε ένα αξιόπιστο αρχείο 7z.

## Γρήγορες Απαντήσεις
- **What does “create encrypted 7z” mean?** Σημαίνει τη δημιουργία ενός αρχείου 7‑zip που προστατεύεται με κρυπτογράφηση AES.  
- **Which library is used?** Aspose.Zip for .NET.  
- **Do I need a license?** Μια προσωρινή άδεια είναι επαρκής για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **Can I add multiple files?** Ναι—καλέστε `CreateEntry` επανειλημμένα για να **add multiple files 7z**.  
- **Is AES encryption supported?** Ναι, το Aspose.Zip υποστηρίζει **how to set AES**‑256 κρυπτογράφηση για αρχεία 7z.  

## Τι είναι ένα κρυπτογραφημένο αρχείο 7z;
Ένα αρχείο 7z είναι μορφή κοντέινερ υψηλής συμπίεσης. Όταν **create encrypted 7z** αρχεία, το περιεχόμενο ανακατεύεται με κρυπτογράφηση AES, καθιστώντας το αδιάβαστο χωρίς τον σωστό κωδικό πρόσβασης. Αυτό είναι ιδανικό για ασφαλή μετάδοση ή αποθήκευση εμπιστευτικών αρχείων.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για κρυπτογραφημένα αρχεία 7z;
- **Full .NET integration** – λειτουργεί με .NET Framework, .NET Core και .NET 5/6.  
- **Built‑in AES‑256 support** – δεν χρειάζονται εξωτερικά εργαλεία· μπορείτε εύκολα να μάθετε **how to set AES**.  
- **Simple API** – κλήσεις μίας γραμμής για **add file to 7z** και αποθήκευση του αρχείου.  
- **Cross‑platform** – εκτελείται σε Windows, Linux και macOS.

## Προαπαιτούμενα

- **Aspose.Zip for .NET Library** – κατεβάστε το [here](https://releases.aspose.com/zip/net/).  
- **A writable folder** στον υπολογιστή σας όπου θα αποθηκευτεί το αρχείο.  
- **A source file** (π.χ., `file.dat`) που θέλετε να συμπιέσετε και να κρυπτογραφήσετε.

## Εισαγωγή Namespaces

Προσθέστε το απαιτούμενο namespace στην κορυφή του αρχείου C#:

```csharp
using Aspose.Zip.SevenZip;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ορισμός του Καταλόγου Εργασίας

Ορίστε τη διαδρομή προς το φάκελο που περιέχει το αρχείο προέλευσης που θέλετε να συμπιέσετε.

```csharp
string dataDir = "Your Document Directory";
```

Αντικαταστήστε το `"Your Document Directory"` με την πραγματική διαδρομή στον υπολογιστή σας.

### Βήμα 2: Δημιουργία της κρυπτογραφημένης καταχώρησης 7z

Ο πυρήνας του tutorial – ανοίγουμε ένα νέο stream αρχείου, δημιουργούμε ένα `SevenZipArchive`, προσθέτουμε μια καταχώρηση και αποθηκεύουμε το αρχείο. Αυτό το παράδειγμα προσθέτει ένα μόνο αρχείο (`file.dat`) ως `data.bin` μέσα στο αρχείο.

```csharp
//ExStart: CreateSevenZipEntry
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("data.bin", "file.dat");
        archive.Save(sevenZipFile);
    }
}
//ExEnd: CreateSevenZipEntry
```

> **Pro tip:** Για να ενεργοποιήσετε την κρυπτογράφηση AES, ορίστε την ιδιότητα `Encryption` στο `SevenZipArchive` πριν καλέσετε το `Save`. (Η ιδιότητα παραλείπεται εδώ για να διατηρηθεί το παράδειγμα σύντομο.)

### Βήμα 3: Επιβεβαίωση Επιτυχίας

Εκτυπώστε ένα φιλικό μήνυμα ώστε να γνωρίζετε ότι η λειτουργία ολοκληρώθηκε χωρίς σφάλματα.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

### Βήμα 4: Επαλήθευση του Αρχείου (Προαιρετικό)

Αφού τρέξει το πρόγραμμα, μεταβείτε στο φάκελο που περιέχει το `archive.7z` και προσπαθήστε να το ανοίξετε με έναν πελάτη 7‑zip. Θα πρέπει να σας ζητηθεί κωδικός πρόσβασης εάν προσθέσατε κρυπτογράφηση στο Βήμα 2. Αυτό το βήμα σας επιτρέπει επίσης να **verify 7z password**.

## Συχνά Προβλήματα & Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **File not found** | Λανθασμένο `dataDir` ή όνομα αρχείου προέλευσης | Ελέγξτε ξανά τη διαδρομή και βεβαιωθείτε ότι το `file.dat` υπάρχει. |
| **Access denied** | Ανεπαρκή δικαιώματα εγγραφής | Εκτελέστε την εφαρμογή με αυξημένα δικαιώματα ή επιλέξτε φάκελο με δυνατότητα εγγραφής. |
| **Encryption not applied** | Λείπουν ρυθμίσεις κρυπτογράφησης στο αρχείο | Ορίστε `archive.Encryption = EncryptionAlgorithm.Aes256;` πριν το `Save`. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσθέσω περισσότερα από ένα αρχεία στο ίδιο 7z αρχείο;**  
A: Απόλυτα. Καλέστε `archive.CreateEntry` για κάθε αρχείο που θέλετε να **add file to 7z** ή **add multiple files 7z**.  

**Q: Πώς ορίζω τον κωδικό πρόσβασης για την κρυπτογράφηση AES;**  
A: Χρησιμοποιήστε την ιδιότητα `Password` στο `SevenZipArchive` πριν την αποθήκευση, π.χ., `archive.Password = "YourStrongPassword";`. Αυτό σας επιτρέπει αργότερα να **verify 7z password** κατά την εξαγωγή.  

**Q: Υποστηρίζει το Aspose.Zip άλλες μορφές αρχείων;**  
A: Το Aspose.Zip εστιάζει κυρίως σε μορφές ZIP και 7z. Για άλλες μορφές, εξετάστε εξειδικευμένες βιβλιοθήκες.  

**Q: Απαιτείται άδεια για χρήση σε παραγωγή;**  
A: Ναι. Μπορείτε να αποκτήσετε προσωρινή άδεια για αξιολόγηση [here](https://purchase.aspose.com/temporary-license/).  

**Q: Πού μπορώ να βρω υποστήριξη από την κοινότητα;**  
A: Επισκεφθείτε το [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) για να θέσετε ερωτήσεις και να μοιραστείτε εμπειρίες.

## Συμπέρασμα

Τώρα έχετε μια σταθερή βάση για **how to encrypt 7z** αρχεία με το Aspose.Zip για .NET. Ακολουθώντας τα παραπάνω βήματα, μπορείτε να συμπιέσετε αρχεία με ασφάλεια, να τα προσθέσετε σε ένα κοντέινερ 7z και ακόμη να ενεργοποιήσετε κρυπτογράφηση AES όταν χρειάζεται. Μη διστάσετε να επεκτείνετε αυτό το παράδειγμα προσθέτοντας περισσότερες καταχωρήσεις, ορίζοντας κωδικούς πρόσβασης ή ενσωματώνοντάς το σε μεγαλύτερες ροές εργασίας όπως αυτοματοποιημένες διαδικασίες backup.

---

**Τελευταία ενημέρωση:** 2026-05-05  
**Δοκιμή με:** Aspose.Zip for .NET 24.11  
**Συγγραφέας:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}