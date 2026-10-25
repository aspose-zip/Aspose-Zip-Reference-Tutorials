---
date: 2026-10-25
description: Μάθετε πώς να αποσυμπιέσετε τον κωδικό zip και να ορίσετε το compression
  algorithm όταν συμπιέζετε αρχεία tar με Aspose.Zip για .NET, βελτιώνοντας την αποδοτικότητα
  αποθήκευσης και την ασφάλεια.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Αποσυμπίεση Αρχείων και Μορφές
og_description: Μάθετε πώς να αποσυμπιέσετε τον κωδικό zip και να ορίσετε το compression
  algorithm όταν συμπιέζετε αρχεία tar με Aspose.Zip για .NET, βελτιώνοντας την αποδοτικότητα
  αποθήκευσης και την ασφάλεια.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Αποσυμπίεση κωδικού zip και συμπίεση αρχείων tar με Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Αποσυμπίεση κωδικού zip και συμπίεση αρχείων tar με Aspose.Zip
url: /el/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποσυμπίεση κωδικού zip και συμπίεση αρχείων tar με Aspose.Zip

## Εισαγωγή

Σε αυτόν τον οδηγό θα ανακαλύψετε τεχνικές **extract zip password**, θα μάθετε πώς να ορίζετε τον αλγόριθμο συμπίεσης κατά τη δημιουργία αρχείων tar‑based, και θα δείτε πώς να δημιουργείτε TarGz, TarBz2 και άλλες μορφές με το Aspose.Zip για .NET. Είτε δημιουργείτε μια υπηρεσία αντιγράφων ασφαλείας, έναν πελάτη cloud‑storage ή μια γραμμή επεξεργασίας δεδομένων, η εξοικείωση με αυτές τις λειτουργίες μειώνει το κόστος αποθήκευσης, επιταχύνει τις μεταφορές και ασφαλίζει ευαίσθητα αρχεία.

## Γρήγορες απαντήσεις
- **Τι είναι το TarBz2;** Ένα συμπιεσμένο αρχείο που συνδυάζει τη συσκευασία TAR με τη συμπίεση BZIP2 για υψηλούς λόγους συμπίεσης.  
- **Γιατί να επιλέξετε το Aspose.Zip για .NET;** Υποστηρίζει πάνω από 50 μορφές αρχείων και συμπίεσης, λειτουργεί σε Windows, Linux και macOS, και διατηρεί τη χρήση μνήμης κάτω από 10 MB για αρχεία πολλαπλών εκατοντάδων megabytes.  
- **Μπορώ να δημιουργήσω ένα αρχείο TarGz;** Ναι – το Aspose.Zip προσφέρει TarGz, TarLz, TarXz, TarZ και άλλα.  
- **Πώς αποσυμπιέζω ένα zip αρχείο προστατευμένο με κωδικό;** Ορίστε την ιδιότητα `Password` σε κάθε `ArchiveEntry` πριν καλέσετε το `Extract`.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται εμπορική άδεια για παραγωγή· διατίθεται δωρεάν δοκιμαστική έκδοση για αξιολόγηση.

## Τι είναι η συμπίεση tar;

Η συμπίεση tar συνδυάζει το κοντέινερ TAR με έναν αλγόριθμο συμπίεσης όπως BZIP2, GZIP, LZMA ή XZ. Το αποτέλεσμα είναι ένα ενιαίο αρχείο (π.χ., `.tar.gz`, `.tar.bz2`) που μπορεί να αποσυμπιεστεί σε Linux, macOS και Windows. Διατηρεί την αρχική ιεραρχία καταλόγων, επιτρέπει εξαγωγή τυχαίας πρόσβασης και υποστηρίζεται ευρέως από εργαλεία γραμμής εντολών και βιβλιοθήκες προγραμματισμού, καθιστώντας το ιδανικό για διανομή πολλαπλών πλατφορμών και αποθήκευση αρχείων.

## Γιατί να χρησιμοποιήσετε το Aspose.Zip για .NET για τη διαχείριση αυτών των μορφών;

Το Aspose.Zip παρέχει ένα ενοποιημένο, χωρίς εξαρτήσεις API που υποστηρίζει **50+** μορφές αρχείων και συμπίεσης, συμπεριλαμβανομένων όλων των κύριων τύπων βασισμένων σε tar. Η αρχιτεκτονική ροής του επεξεργάζεται αρχεία μεγαλύτερα από 10 GB διατηρώντας τη χρήση RAM κάτω από 10 MB, καθιστώντας το ιδανικό για εργασίες διακομιστών υψηλής απόδοσης.

**Άμεση απάντηση:** Χρησιμοποιείτε το Aspose.Zip επειδή σας επιτρέπει να δημιουργείτε, συμπιέζετε και αποσυμπιέζετε αρχεία tar‑based και zip αρχεία προστατευμένα με κωδικό με ένα ενιαίο ευέλικτο API, χωρίς εξωτερικά εργαλεία, ενώ διαχειρίζεται αρχεία πολλαπλών gigabyte σε λειτουργία ροής με αποδοτική χρήση μνήμης.

## Προαπαιτούμενα
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 ή .NET 5–10.  
- Πακέτο NuGet Aspose.Zip για .NET (`Install-Package Aspose.Zip`).  
- Βασική εξοικείωση με το C# file I/O και το σύστημα έργων .NET.

## Οδηγός βήμα‑βήμα

### Πώς να συμπιέσετε αρχεία tar – άμεση απάντηση
Δημιουργήστε ένα αντικείμενο `Archive`, προσθέστε τα αρχεία που θέλετε να συσσωρεύσετε, ορίστε `CompressionType.BZip2` (ή άλλο αλγόριθμο) και καλέστε `Save` με `ArchiveFormat.TarBz2`. Η βιβλιοθήκη γράφει το κοντέινερ TAR και το συμπιέζει σε μία ροή, έτσι δεν φορτώνετε ποτέ ολόκληρο το αρχείο στη μνήμη.

### Βήμα 1: Επιλέξτε τη μορφή αρχείου που χρειάζεστε
Αποφασίστε ποια μορφή βασισμένη σε tar ταιριάζει καλύτερα με το συμβιβασμό συμπίεσης‑ταχύτητας:

- **TarBz2** – Υψηλότερος λόγος συμπίεσης (≈30 % μικρότερο από TarGz) αλλά πιο αργό.  
- **TarGz** – Καλός συμβιβασμός ταχύτητας και μεγέθους· ιδανικό για τις περισσότερες περιπτώσεις cloud‑storage.  
- **TarLz / TarXz** – Πολύ υψηλή συμπίεση με μέτρια ταχύτητα, χρήσιμη για αποθήκευση αρχείων.  
- **TarZ** – Μορφή κληρονομιάς για συμβατότητα με παλαιότερα εργαλεία Unix.

### Βήμα 2: Δημιουργήστε ένα νέο αντικείμενο `Archive`
`Archive` αντιπροσωπεύει ένα μοναδικό αρχείο archive και παρέχει μεθόδους για προσθήκη καταχωρήσεων και αποθήκευση του αρχείου.  
Η κλάση `Archive` διαχειρίζεται τη ροή συσκευασίας και συμπίεσης, εκθέτοντας μεθόδους για προσθήκη καταχωρήσεων και εγγραφή του τελικού αρχείου.

### Βήμα 3: Προσθήκη αρχείων και φακέλων
Μπορείτε να προσθέσετε ολόκληρο δέντρο καταλόγου με `AddAll` ή μεμονωμένα αρχεία με `AddFile`.  
`AddAll` προσθέτει ολόκληρο δέντρο καταλόγου στο archive, διατηρώντας τη δομή του.  
`AddFile` προσθέτει ένα μόνο αρχείο στο archive. Η διατήρηση της αρχικής ιεραρχίας φακέλων είναι τόσο απλή όσο η παροχή της διαδρομής του βασικού καταλόγου.

### Βήμα 4: Ορίστε τον επιθυμητό τύπο συμπίεσης
Η απαρίθμηση `CompressionType` καθορίζει τον αλγόριθμο συμπίεσης που εφαρμόζεται στο ρεύμα TAR.  
`CompressionType` απαριθμεί τους υποστηριζόμενους αλγόριθμους (BZip2, GZip, LZMA, XZ, κ.λπ.) που θα εφαρμοστούν κατά την αποθήκευση.

### Βήμα 5: Αποθήκευση του archive
Η απαρίθμηση `ArchiveFormat` επιλέγει το κοντέινερ και τον συνδυασμό συμπίεσης για το αρχείο εξόδου.  
Καλώντας το `Save` γράφει το archive στο δίσκο χρησιμοποιώντας την επιλεγμένη μορφή.

### Βήμα 6: Εξαγωγή αρχείων με κωδικούς πρόσβασης
`ArchiveEntry` αντιπροσωπεύει ένα μόνο αρχείο ή καταχώρηση φακέλου μέσα σε ένα archive.  
Για να εξάγετε ένα zip προστατευμένο με κωδικό, ανοίξτε το archive, εντοπίστε κάθε `ArchiveEntry`, ορίστε την ιδιότητα `Password` του και καλέστε το `Extract`. Η ιδιότητα `Password` ορίζει τον κωδικό αποκρυπτογράφησης για μια καταχώρηση zip. Αυτό το μοντέλο κωδικού ανά καταχώρηση σας επιτρέπει να προστατεύετε μεμονωμένα αρχεία μέσα σε ένα μόνο zip.

### Βήμα 7: Επαλήθευση του αποτελέσματος
Μετά την εξαγωγή, συγκρίνετε τα μεγέθη αρχείων και τα SHA‑256 checksums για να επιβεβαιώσετε ότι η διαδικασία round‑trip του archive διατήρησε την ακεραιότητα των δεδομένων.

## Συνηθισμένες περιπτώσεις χρήσης
- **Εργαλεία αντιγράφων ασφαλείας** – Αποθηκεύστε καθημερινά αντίγραφα ως `.tar.bz2` για μείωση του κόστους αποθήκευσης έως και 30 %.  
- **Διαπλατφορμική ανταλλαγή δεδομένων** – Οι μορφές βασισμένες σε tar κατανοούνται εγγενώς από εργαλεία Linux, macOS και Windows.  
- **Ασφαλής διανομή** – Αναθέστε κωδικούς σε ευαίσθητες καταχωρήσεις, ικανοποιώντας απαιτήσεις συμμόρφωσης χωρίς πρόσθετα εργαλεία κρυπτογράφησης.

## Αντιμετώπιση προβλημάτων & συμβουλές
- **Μεγάλα αρχεία** – Χρησιμοποιήστε το streaming API (`Archive.CreateEntryFromFile`) για χαμηλή χρήση μνήμης.  
- **Ασυμφωνίες κωδικού** – Ο κωδικός που ορίζεται σε κάθε `ArchiveEntry` πρέπει να ταιριάζει ακριβώς· διαφορετικά ρίχνεται `InvalidPasswordException`.  
- **Επίπεδο συμπίεσης** – Το BZIP2 δεν εκθέτει προσαρμοσμένα επίπεδα· εάν χρειάζεστε πιο ακριβή έλεγχο, μεταβείτε σε LZMA (`CompressionType.LZMA`) ή XZ (`CompressionType.XZ`).  

## Συχνές ερωτήσεις

**Ε: Πώς δημιουργώ ένα αρχείο TarGz;**  
Α: Ορίστε `CompressionType.GZip` και χρησιμοποιήστε `ArchiveFormat.TarGz` όταν καλείτε το `Save`. Αυτό παράγει ένα αρχείο `.tar.gz` σε ένα βήμα.

**Ε: Μπορώ να εξάγω ένα αρχείο προστατευμένο με κωδικό χωρίς να γνωρίζω τον κωδικό;**  
Α: Όχι. Κάθε καταχώρηση πρέπει να του δοθεί ο σωστός κωδικός· η εξαγωγή αποτυγχάνει με `InvalidPasswordException` διαφορετικά.

**Ε: Υποστηρίζει το Aspose.Zip την εξαγωγή αρχείων με διαφορετικούς κωδικούς ανά καταχώρηση;**  
Α: Ναι. Αναθέστε κωδικό σε κάθε `ArchiveEntry` ξεχωριστά πριν καλέσετε το `Extract`.

**Ε: Ποια μορφή παρέχει την καλύτερη συμπίεση;**  
Α: Το TarBz2 συνήθως δίνει το μικρότερο μέγεθος, ακολουθείται από TarLz και TarXz. Το TarGz προσφέρει μια πιο γρήγορη, αλλά ακόμη αποτελεσματική εναλλακτική.

**Ε: Υπάρχει όριο στον αριθμό των αρχείων που μπορώ να προσθέσω σε ένα αρχείο TAR;**  
Α: Πρακτικά κανένα, αλλά εξαιρετικά μεγάλα αρχεία (>10 GB) μπορεί να ωφεληθούν από το διαχωρισμό σε πολλαπλά μέρη για ευκολότερη διαχείριση.

## Μαθήματα εξαγωγής αρχείων και μορφών

### [Συμπίεση αρχείων σε TarBz2 με Aspose.Zip για .NET](./compress-to-tar-bz2/)
Μάθετε πώς να συμπιέζετε αρχεία σε μορφή TarBz2 σε .NET χρησιμοποιώντας το Aspose.Zip. Ακολουθήστε τον οδηγό βήμα‑βήμα για αποδοτική συμπίεση αρχείων.

### [Συμπίεση σε TarGz με Aspose.Zip για .NET](./compress-to-tar-gz/)
Εξερευνήστε αποδοτική συμπίεση αρχείων σε .NET με το Aspose.Zip. Συμπιέστε σε TarGz χωρίς κόπο.

### [Συμπίεση σε TarLz με Aspose.Zip για .NET](./compress-to-tar-lz/)
Συμπιέστε αρχεία σε .NET με το Aspose.Zip χωρίς κόπο. Μάθετε να δημιουργείτε αρχεία TarLz βήμα‑βήμα.

### [Συμπίεση σε TarXz με Aspose.Zip για .NET](./compress-to-tar-xz/)
Μάθετε να συμπιέζετε αρχεία σε μορφή TarXz σε .NET χρησιμοποιώντας το Aspose.Zip. Ακολουθήστε τον οδηγό μας για αποδοτική αποθήκευση και μετάδοση.

### [Συμπίεση σε TarZ με Aspose.Zip για .NET](./compress-to-tar-z/)
Εξερευνήστε τη βήμα‑βήμα συμπίεση σε TarZ χρησιμοποιώντας το Aspose.Zip για .NET. Αποδοτική διαχείριση αρχείων για τα .NET έργα σας.

### [Εξαγωγή καταχωρήσεων αρχείου με διαφορετικούς κωδικούς στο Aspose.Zip για .NET](./extract-archive-different-passwords/)
Μάθετε πώς να εξάγετε καταχωρήσεις αρχείου με διαφορετικούς κωδικούς στο Aspose.Zip για .NET. Ενισχύστε την ασφάλεια και την ευελιξία στις εφαρμογές σας.

## Σχετικά μαθήματα

- [Δημιουργία αρχείου tar και προσθήκη αρχείων στο tar με Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Πώς να συμπιέσετε tar και να δημιουργήσετε TarBz2 με Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Προσθήκη αρχείων στο tar και δημιουργία αρχείου tarxz με Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Last Updated:** 2026-10-25  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}