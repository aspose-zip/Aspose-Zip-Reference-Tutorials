---
date: 2026-07-09
description: Μάθετε πώς να προσθέσετε κωδικό σε zip σε ASP.NET χρησιμοποιώντας το
  Aspose.Zip για .NET, με κρυπτογράφηση zip φακέλου και συμπίεση καταλόγου. Οδηγός
  βήμα‑βήμα για έργα .NET.
keywords:
- add password zip
- zip folder encryption
- compress entire directory
- .net zip encryption
- zip directory .net
lastmod: 2026-07-09
linktitle: Προσθήκη κωδικού σε zip σε ASP.NET – Συμπίεση καταλόγου & φακέλου
og_description: Προσθήκη κωδικού σε zip σε ASP.NET χρησιμοποιώντας το Aspose.Zip.
  Μάθετε κρυπτογράφηση zip φακέλου, συμπίεση ολόκληρου καταλόγου και διαχείριση αρχείων
  zip αποδοτικά.
og_image_alt: 'Developer guide: add password zip in ASP.NET with Aspose.Zip'
og_title: Προσθήκη κωδικού σε zip σε ASP.NET – Συμπίεση καταλόγου & φακέλου
schemas:
- author: Aspose
  dateModified: '2026-07-09'
  description: Learn how to add password zip in ASP.NET using Aspose.Zip for .NET,
    with zip folder encryption and directory compression. Step‑by‑step guide for .NET
    projects.
  headline: Add Password Zip in ASP.NET – Directory & Folder Compression
  type: TechArticle
- description: Learn how to add password zip in ASP.NET using Aspose.Zip for .NET,
    with zip folder encryption and directory compression. Step‑by‑step guide for .NET
    projects.
  name: Add Password Zip in ASP.NET – Directory & Folder Compression
  steps:
  - name: '**Instantiate `ZipPackage`** – this object will hold the archive you are
      building.'
    text: '**Instantiate `ZipPackage`** – this object will hold the archive you are
      building.'
  - name: '**Add the target directory** using `AddFolder`, which automatically includes
      sub‑folders and files.'
    text: '**Add the target directory** using `AddFolder`, which automatically includes
      sub‑folders and files.'
  - name: '**Configure encryption** (optional) by setting `ZipPassword` and `EncryptionAlgorithm`.'
    text: '**Configure encryption** (optional) by setting `ZipPassword` and `EncryptionAlgorithm`.'
  - name: '**Save the archive** to a `.zip` file.'
    text: '**Save the archive** to a `.zip` file.'
  type: HowTo
- questions:
  - answer: Yes. When saving the archive, provide a `ZipPassword` and select `EncryptionAlgorithm.Aes256`
      to secure the file.
    question: Can I create a password‑protected zip archive using Aspose.Zip?
  - answer: Absolutely. You can work with `FileStream` objects, allowing you to compress
      or extract files of any size efficiently.
    question: Does Aspose.Zip support streaming large files without loading them entirely
      into memory?
  - answer: Use the `SplitArchive` method to define a maximum part size; Aspose.Zip
      will automatically create sequential split files.
    question: What if I need to split a large archive into multiple parts?
  - answer: Yes. Open the archive in `Update` mode and call `AddFile` or `AddFolder`
      to append new content.
    question: Is it possible to add files to an existing zip archive?
  - answer: Aspose.Zip for .NET supports .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10.
    question: Which .NET runtimes are officially supported?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip archive
- Aspose.Zip
- .NET compression
title: Προσθήκη κωδικού σε zip σε ASP.NET – Συμπίεση καταλόγου & φακέλου
url: /el/net/directory-and-folder-compression/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη κωδικού πρόσβασης zip σε ASP.NET – Συμπίεση καταλόγου & φακέλου

## Εισαγωγή

Στη σύγχρονη ανάπτυξη .NET, η λειτουργία **add password zip** είναι απαραίτητη για την προστασία ευαίσθητων δεδομένων, τη μείωση του κόστους αποθήκευσης και την απλοποίηση της διανομής αρχείων. Αυτό το εκπαιδευτικό υλικό σας καθοδηγεί στη χρήση του Aspose.Zip για .NET για τη συμπίεση ολόκληρων καταλόγων, την εφαρμογή κρυπτογράφησης φακέλου zip και την εξαγωγή τους αργότερα. Είτε δημιουργείτε μια αλυσίδα CI/CD, είτε παραδίδετε πακέτα ενημερώσεων, είτε απλώς τακτοποιείτε αρχεία καταγραφής, η εξοικείωση με τη δημιουργία αρχείων zip με προστασία κωδικού πρόσβασης θα κάνει τα έργα σας πιο ασφαλή και επαγγελματικά.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη προσθέτει password zip;** Το Aspose.Zip για .NET παρέχει κρυπτογράφηση φακέλου zip υψηλής απόδοσης με λίγες γραμμές κώδικα.  
- **Μπορώ να συμπιέσω ολόκληρο κατάλογο με μία κλήση;** Ναι – το `AddFolder` περιλαμβάνει αναδρομικά υποφακέλους και αρχεία.  
- **Υποστηρίζεται η κρυπτογράφηση AES‑256;** Απόλυτα· ορίστε το `ZipPassword` και επιλέξτε `EncryptionAlgorithm.Aes256`.  
- **Χρειάζομαι άδεια για παραγωγή;** Μια δωρεάν δοκιμή είναι επαρκής για αξιολόγηση· απαιτείται εμπορική άδεια για χρήση σε παραγωγή.  
- **Ποια .NET runtime υποστηρίζονται;** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10.

## Τι είναι η προσθήκη κωδικού πρόσβασης zip;
`add password zip` είναι η διαδικασία δημιουργίας ενός αρχείου ZIP ενώ ενσωματώνεται κρυπτογραφικό δεδομένο (συνήθως AES‑256) ώστε μόνο οι χρήστες που γνωρίζουν τον κωδικό πρόσβασης να μπορούν να ανοίξουν το αρχείο. Αυτό προστατεύει εμπιστευτικά αρχεία κατά την αποθήκευση ή τη μετάδοση και είναι πλήρως συμβατό με οποιοδήποτε τυπικό εργαλείο ZIP.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για .NET;
Το Aspose.Zip υποστηρίζει **πάνω από 30 μορφές αρχείων και συμπίεσης**, επεξεργάζεται αρχεία έως **10 GB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, και προσφέρει ενσωματωμένο Zip64, διαίρεση αρχείου και κρυπτογράφηση AES‑256. Ο σχεδιασμός του χωρίς εξαρτήσεις σημαίνει ότι δεν χρειάζεστε εξωτερικά εργαλεία όπως το 7‑Zip, και το API είναι συνεπές σε .NET Framework, .NET Core και .NET 5‑10.

## Προαπαιτούμενα
- Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει .NET 6+)  
- Πακέτο NuGet Aspose.Zip για .NET (`Install-Package Aspose.Zip`)  
- Βασική εξοικείωση με λειτουργίες συστήματος αρχείων C#  

## Πώς να προσθέσετε κωδικό πρόσβασης zip σε ASP.NET;
`ZipPackage` είναι η κύρια κλάση του Aspose.Zip που αντιπροσωπεύει ένα αρχείο ZIP στη μνήμη.  
Για να δημιουργήσετε ένα αρχείο με προστασία κωδικού πρόσβασης, πρώτα φορτώστε το φάκελο που θέλετε να συμπιέσετε, στη συνέχεια δημιουργήστε ένα αντικείμενο `ZipPackage` που αντιπροσωπεύει το αρχείο ZIP στη μνήμη. Ορίστε την ιδιότητα `ZipPassword` στον επιθυμητό κωδικό πρόσβασης και προαιρετικά επιλέξτε έναν αλγόριθμο κρυπτογράφησης όπως AES‑256. Τέλος, καλέστε `Save` για να γράψετε το κρυπτογραφημένο zip στο δίσκο.

## Πώς να συμπιέσετε φάκελο .NET με το Aspose.Zip
`ZipPackage` είναι η κύρια κλάση του Aspose.Zip που αντιπροσωπεύει ένα αρχείο ZIP στη μνήμη.  
`AddFolder` προσθέτει έναν κατάλογο και τα περιεχόμενά του αναδρομικά στο αρχείο.  
Η συμπίεση ενός καταλόγου είναι απλή με το Aspose.Zip. Ξεκινήστε δημιουργώντας ένα αντικείμενο `ZipPackage`, στη συνέχεια χρησιμοποιήστε τη μέθοδο `AddFolder` για να συμπεριλάβετε τον στόχο φάκελο και όλους τους υποφακέλους. Μπορείτε να ρυθμίσετε το επίπεδο συμπίεσης και την κρυπτογράφηση πριν αποθηκεύσετε το αρχείο σε μορφή .zip.

1. **Δημιουργήστε ένα αντικείμενο `ZipPackage`** – αυτό το αντικείμενο θα κρατήσει το αρχείο που δημιουργείτε.  
2. **Προσθέστε τον στόχο φάκελο** χρησιμοποιώντας το `AddFolder`, το οποίο συμπεριλαμβάνει αυτόματα υποφακέλους και αρχεία.  
3. **Ρυθμίστε την κρυπτογράφηση** (προαιρετικά) ορίζοντας `ZipPassword` και `EncryptionAlgorithm`.  
4. **Αποθηκεύστε το αρχείο** σε ένα αρχείο `.zip`.

> *Σημείωση:* Ο πραγματικός κώδικας C# για αυτά τα βήματα παρέχεται στη συνδεδεμένη σελίδα μαθήματος «Ανεπιτήδευτη Συμπίεση Καταλόγου».

## Προσθήκη zip με προστασία κωδικού πρόσβασης .NET
Παρέχετε ένα `ZipPassword` κατά την αποθήκευση του αρχείου και επιλέξτε `EncryptionAlgorithm.Aes256`. Αυτό δημιουργεί ένα **αρχείο zip .NET με προστασία κωδικού πρόσβασης** που μόνο εξουσιοδοτημένοι χρήστες μπορούν να ανοίξουν. Η κρυπτογράφηση εφαρμόζεται ανά αρχείο, διατηρώντας την αρχική δομή φακέλου.

## Αποσυμπίεση φακέλου με το Aspose.Zip για .NET
Ανοίξτε το αρχείο zip με το `ZipPackage` σε λειτουργία ανάγνωσης, στη συνέχεια καλέστε `ExtractAll` ή `ExtractFolder` για να επαναφέρετε την αρχική ιεραρχία. Το Aspose.Zip μεταδίδει τα δεδομένα, έτσι ακόμη και αρχεία πολλαπλών γιγαμπάιτ εξάγονται χωρίς να εξαντλείται η μνήμη.

## Συνηθισμένα προβλήματα & Συμβουλές
- **Μεγάλα αρχεία:** Ενεργοποιήστε το `Zip64` όταν εργάζεστε με αρχεία μεγαλύτερα από 2 GB για να αποφύγετε περιορισμούς μεγέθους.  
- **Μήκος διαδρομής:** Ορίστε `UseLongFileNames = true` εάν η ιεραρχία φακέλων υπερβαίνει το όριο των 260 χαρακτήρων των Windows.  
- **Απόδοση:** Χρησιμοποιήστε `CompressionLevel.Fast` για γρήγορες δημιουργίες, ή `CompressionLevel.Maximum` όταν χρειάζεστε το μικρότερο μέγεθος αρχείου.  

## Πραγματικές περιπτώσεις χρήσης
- **Συνεχείς ενσωματώσεις/συνεχή παράδοση (CI/CD):** Συσκευάστε τα αποτελέσματα κατασκευής σε αρχείο zip πριν τη δημοσίευση σε αποθήκη τεχνουργημάτων.  
- **Ανακύκλωση αρχείων καταγραφής:** Συμπιέστε τους νυχτερινούς φακέλους καταγραφής για να εξοικονομήσετε χώρο δίσκου ενώ διατηρείτε την προστασία κωδικού πρόσβασης.  
- **Ενημερώσεις λογισμικού:** Συγκεντρώστε τα αρχεία ενημέρωσης σε ένα ενιαίο κρυπτογραφημένο αρχείο για ασφαλή λήψη και εγκατάσταση.  

## Μαθήματα Συμπίεσης Καταλόγου και Φακέλου
### [Ανεπιτήδευτη Συμπίεση Καταλόγου με το Aspose.Zip για .NET](./compress-directory/)
Μάθετε να συμπιέζετε καταλόγους ανεπιτήδευτα με το Aspose.Zip για .NET. Βελτιώστε την ανάπτυξη .NET βελτιστοποιώντας τον χώρο αποθήκευσης αποδοτικά.  
### [Αποσυμπίεση Φακέλου με το Aspose.Zip για .NET](./decompress-folder/)
Κατακτήστε την τέχνη της αποσυμπίεσης φακέλων με το Aspose.Zip για .NET. Διαχειριστείτε εύκολα εργασίες συμπίεσης στα έργα σας.  

## Συχνές Ερωτήσεις

**Q: Μπορώ να δημιουργήσω ένα αρχείο zip με προστασία κωδικού πρόσβασης χρησιμοποιώντας το Aspose.Zip;**  
A: Ναι. Κατά την αποθήκευση του αρχείου, δώστε ένα `ZipPassword` και επιλέξτε `EncryptionAlgorithm.Aes256` για να ασφαλίσετε το αρχείο.

**Q: Υποστηρίζει το Aspose.Zip τη ροή μεγάλων αρχείων χωρίς να τα φορτώνει ολόκληρα στη μνήμη;**  
A: Απόλυτα. Μπορείτε να εργαστείτε με αντικείμενα `FileStream`, επιτρέποντας τη συμπίεση ή εξαγωγή αρχείων οποιουδήποτε μεγέθους αποδοτικά.

**Q: Τι κάνω αν χρειάζεται να χωρίσω ένα μεγάλο αρχείο σε πολλαπλά μέρη;**  
A: Χρησιμοποιήστε τη μέθοδο `SplitArchive` για να ορίσετε το μέγιστο μέγεθος τμήματος· το Aspose.Zip θα δημιουργήσει αυτόματα διαδοχικά αρχεία διαίρεσης.

**Q: Είναι δυνατόν να προσθέσω αρχεία σε ένα υπάρχον αρχείο zip;**  
A: Ναι. Ανοίξτε το αρχείο σε λειτουργία `Update` και καλέστε `AddFile` ή `AddFolder` για να προσθέσετε νέο περιεχόμενο.

**Q: Ποια .NET runtime υποστηρίζονται επίσημα;**  
A: Το Aspose.Zip για .NET υποστηρίζει .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, και .NET 5–10.

**Τελευταία ενημέρωση:** 2026-07-09  
**Δοκιμάστηκε με:** Aspose.Zip for .NET 24.11  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Προσθήκη κωδικού πρόσβασης σε Zip – Οδηγός Aspose.Zip για .NET](/zip/net/password-protection-and-encryption/)
- [Δημιουργία αρχείων ZIP με προστασία κωδικού πρόσβασης και κρυπτογράφηση AES χρησιμοποιώντας Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Πώς να συμπιέσετε φάκελο χρησιμοποιώντας Aspose.Zip για .NET](/zip/net/directory-and-folder-compression/compress-directory/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}