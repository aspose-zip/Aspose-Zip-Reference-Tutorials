---
date: 2026-03-05
description: Μάθετε πώς να δημιουργείτε zip με κωδικό πρόσβασης και να συμπιέζετε
  αρχεία με κρυπτογράφηση στο Aspose.Zip για .NET. Προστατέψτε τα αρχεία σας με λύσεις
  zip .NET που προστατεύονται με κωδικό πρόσβασης.
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Δημιουργία Zip με κωδικό πρόσβασης χρησιμοποιώντας το Aspose.Zip .NET
url: /el/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Zip με Κωδικό Πρόσβασης χρησιμοποιώντας Aspose.Zip .NET

## Εισαγωγή

Σε αυτό το tutorial θα μάθετε πώς να **δημιουργήσετε zip με κωδικό πρόσβασης** προστασία ενώ προσθέτετε πολλαπλά αρχεία σε ένα ενιαίο αρχείο. Το Aspose.Zip for .NET κάνει εύκολη τη **συμπίεση αρχείων με κρυπτογράφηση**, παρέχοντάς σας μια ασφαλή ροή εργασίας συμπίεσης zip που λειτουργεί τόσο σε Windows όσο και σε Linux. Θα περάσουμε βήμα‑βήμα από τον ορισμό του κωδικού zip μέχρι την αποθήκευση του τελικού αρχείου, ώστε να μπορείτε να προστατεύετε ευαίσθητα δεδομένα στις .NET εφαρμογές σας.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται zip με κωδικό πρόσβασης;** Aspose.Zip for .NET  
- **Πόσα αρχεία μπορώ να προσθέσω;** Απεριόριστα – προσθέστε όσες καταχωρήσεις χρειάζεστε  
- **Ποια κρυπτογράφηση χρησιμοποιείται;** Παραδοσιακή κρυπτογράφηση Zip (PKZIP)  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται εμπορική άδεια  
- **Είναι συμβατό με .NET Core;** Απόλυτα – λειτουργεί με .NET 5/6 και .NET Core  

## Τι είναι η «δημιουργία zip με κωδικό πρόσβασης»;
Η δημιουργία zip με κωδικό πρόσβασης σημαίνει την παραγωγή ενός τυπικού αρχείου ZIP όπου κάθε καταχώρηση κρυπτογραφείται με έναν κωδικό που καθορίζετε. Αυτό προστατεύει το περιεχόμενο από μη εξουσιοδοτημένη πρόσβαση, διατηρώντας ταυτόχρονα τη συμβατότητα του αρχείου με τα περισσότερα εργαλεία αποσυμπίεσης.

## Γιατί να χρησιμοποιήσετε ασφαλή συμπίεση zip με Aspose.Zip;
- **Υποστήριξη πολλαπλών πλατφορμών** – λειτουργεί σε Windows, Linux και macOS.  
- **Χωρίς εξωτερικές εξαρτήσεις** – καθαρή υλοποίηση .NET.  
- **Παραδοσιακή κρυπτογράφηση** – συμβατή με παλαιότερα εργαλεία zip.  
- **Απλό API** – ορίστε τον κωδικό μία φορά και προσθέστε όσα αρχεία θέλετε.  

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- **Aspose.Zip for .NET** εγκατεστημένο. Μπορείτε να το κατεβάσετε από [εδώ](https://releases.aspose.com/zip/net/).  
- Έναν φάκελο που περιέχει τα αρχεία που θέλετε να συμπιέσετε. Αντικαταστήστε το `"Your Document Directory"` στον κώδικα με την πραγματική διαδρομή των αρχείων σας.  

## Εισαγωγή Namespaces

Στο .NET project σας, εισάγετε τα απαραίτητα namespaces ώστε να μπορείτε να δουλέψετε με το Aspose.Zip API:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Πώς να ορίσετε κωδικό zip και να προσθέσετε πολλαπλά αρχεία zip

### Βήμα 1: Ρύθμιση του αρχείου Zip και ορισμός του κωδικού  

Ξεκινάμε δημιουργώντας ένα νέο αρχείο και διαμορφώνοντας **set zip password** χρησιμοποιώντας το `TraditionalEncryptionSettings`. Αυτό το βήμα εξασφαλίζει ότι κάθε καταχώρηση που θα προσθέσουμε θα κρυπτογραφείται με τον ίδιο κωδικό.

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings (password = "p@s$")
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### Βήμα 2: Προσθήκη πολλαπλών αρχείων στο αρχείο  

Τώρα **add multiple files zip** καταχωρήσεις. Στο παράδειγμα προσθέτουμε τρία δείγματα αρχείων κειμένου, αλλά μπορείτε να συμπεριλάβετε οποιοδήποτε τύπο αρχείου.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### Βήμα 3: Αποθήκευση του αρχείου Zip  

Τέλος, αποθηκεύουμε το αρχείο στο δίσκο. Αυτό ολοκληρώνει τη λειτουργία **create zip with password**.

```csharp
archive.Save(zipFile);
```

Συγχαρητήρια! Έχετε ολοκληρώσει επιτυχώς τη **create zip with password** και τη **compress files with encryption** χρησιμοποιώντας το Aspose.Zip for .NET.

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| **Ο κωδικός πρόσβασης δεν εφαρμόστηκε** | Οι ρυθμίσεις κρυπτογράφησης παραλείφθηκαν κατά τη δημιουργία του `Archive` | Βεβαιωθείτε ότι περνάτε `new TraditionalEncryptionSettings("yourPassword")` στο `ArchiveEntrySettings`. |
| **Το αρχείο δεν βρέθηκε** | Τα `source1`, `source2`, `source3` δείχνουν σε λανθασμένες διαδρομές | Χρησιμοποιήστε `File.ReadAllBytes(Path.Combine(yourFolder, "filename"))` για να φορτώσετε τα δεδομένα. |
| **Συμβατότητα με εργαλεία αποσυμπίεσης** | Ορισμένα σύγχρονα εργαλεία αναμένουν κρυπτογράφηση AES | Η παραδοσιακή κρυπτογράφηση υποστηρίζεται ευρέως· αν χρειάζεστε AES, χρησιμοποιήστε `AesEncryptionSettings` αντί. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Zip για .NET σε Linux;**  
Α: Ναι, το Aspose.Zip for .NET είναι πλήρως cross‑platform και λειτουργεί τόσο σε Windows όσο και σε Linux περιβάλλοντα.

**Ε: Υπάρχει δωρεάν δοκιμή;**  
Α: Ναι, μπορείτε να δοκιμάσετε δωρεάν το Aspose.Zip for .NET [εδώ](https://releases.aspose.com/).

**Ε: Πώς μπορώ να λάβω υποστήριξη αν αντιμετωπίσω προβλήματα;**  
Α: Επισκεφθείτε το [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) για βοήθεια από την κοινότητα και επίσημες επιλογές υποστήριξης.

**Ε: Είναι οι προσωρινές άδειες επιλογή για αξιολόγηση;**  
Α: Απόλυτα – μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να βρω την πλήρη αναφορά API;**  
Α: Λεπτομερής τεκμηρίωση είναι διαθέσιμη [εδώ](https://reference.aspose.com/zip/net/).

---

**Τελευταία ενημέρωση:** 2026-03-05  
**Δοκιμάστηκε με:** Aspose.Zip 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}