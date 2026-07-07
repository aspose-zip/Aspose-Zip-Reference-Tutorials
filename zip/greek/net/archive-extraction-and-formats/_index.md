---
date: 2026-06-19
description: Μάθετε πώς να συμπιέζετε αρχεία tar, να δημιουργείτε αρχεία targz και
  να εξάγετε zip αρχεία με προστασία κωδικού χρησιμοποιώντας το Aspose.Zip για .NET
  – βελτιώνοντας την αποδοτικότητα αποθήκευσης και την ασφάλεια.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Εξαγωγή Αρχείων και Μορφές
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να Συμπιέσετε Αρχεία Tar με το Aspose.Zip για .NET
url: /el/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Συμπιέσετε Αρχεία Tar με Aspose.Zip για .NET

## Εισαγωγή

Σε αυτόν τον οδηγό θα ανακαλύψετε **πώς να συμπιέσετε tar** αρχεία χρησιμοποιώντας το Aspose.Zip για .NET, θα μάθετε να δημιουργείτε αρχεία TarGz και θα δείτε πώς να εξάγετε αρχεία zip με προστασία κωδικού πρόσβασης. Η αποτελεσματική διαχείριση αρχείων είναι βασική δεξιότητα για σύγχρονους προγραμματιστές .NET—είτε δημιουργείτε υπηρεσία αντιγράφων ασφαλείας, πελάτη αποθήκευσης στο cloud ή γραμμή επεξεργασίας δεδομένων, η εξοικείωση με αυτές τις μορφές μειώνει το κόστος αποθήκευσης, επιταχύνει τις μεταφορές και διασφαλίζει την ασφάλεια των ευαίσθητων δεδομένων.

## Γρήγορες Απαντήσεις
- **Τι είναι το TarBz2;** Ένα συμπιεσμένο αρχείο που συνδυάζει τη συσκευασία TAR με συμπίεση BZIP2 για υψηλούς λόγους συμπίεσης.  
- **Γιατί να επιλέξετε το Aspose.Zip για .NET;** Προσφέρει ένα ενιαίο, εύχρηστο API για τη δημιουργία και εξαγωγή πολλών μορφών αρχείων χωρίς εξωτερικές εξαρτήσεις.  
- **Μπορώ να δημιουργήσω ένα αρχείο TarGz;** Ναι – το Aspose.Zip υποστηρίζει TarGz, TarLz, TarXz, TarZ και άλλα.  
- **Πώς να εξάγω ένα αρχείο zip με προστασία κωδικού πρόσβασης;** Χρησιμοποιήστε την ιδιότητα `Password` στο αντικείμενο `ArchiveEntry` κατά την εξαγωγή.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται εμπορική άδεια για παραγωγή· υπάρχει δωρεάν δοκιμαστική έκδοση για αξιολόγηση.

## Τι είναι η Συμπίεση Tar;

Το Tar (Tape Archive) είναι μια μορφή δοχείου που ομαδοποιεί πολλά αρχεία και καταλόγους σε μία ενιαία ροή χωρίς συμπίεση. Όταν εφαρμόζετε έναν αλγόριθμο συμπίεσης όπως BZIP2, GZip, LZMA ή XZ, το αποτέλεσμα είναι ένα **αρχείο βασισμένο σε tar** όπως `.tar.bz2`, `.tar.gz`, `.tar.lz` κ.λπ. Αυτές οι μορφές υποστηρίζονται ευρέως σε Linux, macOS και Windows, καθιστώντας τις ιδανικές για ανταλλαγή δεδομένων μεταξύ πλατφορμών.

## Γιατί να Χρησιμοποιήσετε το Aspose.Zip για .NET για τη Διαχείριση Αυτών των Μορφών;

Το Aspose.Zip παρέχει ένα **ενοποιημένο, χωρίς εξαρτήσεις API** που υποστηρίζει πάνω από 50 μορφές αρχείων και συμπίεσης, συμπεριλαμβανομένων TarBz2, TarGz, TarLz, TarXz και TarZ. Λειτουργεί σε Windows, Linux και macOS, και η αρχιτεκτονική του βασισμένη σε ροές διατηρεί τη χρήση μνήμης κάτω από 10 MB ακόμη και για αρχεία πολλών εκατοντάδων megabytes. Η προστασία με κωδικό πρόσβασης είναι ενσωματωμένη, επιτρέποντας κρυπτογράφηση ανά καταχώρηση χωρίς πρόσθετες βιβλιοθήκες.

## Προαπαιτούμενα
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, ή .NET 5–10.  
- Πακέτο NuGet Aspose.Zip for .NET εγκατεστημένο (`Install-Package Aspose.Zip`).  
- Βασική εξοικείωση με το C# file I/O και το σύστημα έργων .NET.

## Οδηγός Βήμα‑προς‑Βήμα

### Πώς να Συμπιέσετε Αρχεία Tar – Άμεση Απάντηση
`Archive` αντιπροσωπεύει ένα αρχείο αρχείου και παρέχει μεθόδους για προσθήκη καταχωρήσεων και αποθήκευση.  
Δημιουργήστε μια παρουσία `Archive`, προσθέστε τα αρχεία που θέλετε να ομαδοποιήσετε, ορίστε `CompressionType.BZip2` και καλέστε `Save` με `ArchiveFormat.TarBz2`. Η βιβλιοθήκη γράφει το κοντέινερ TAR και το συμπιέζει σε μία ενιαία ροή, έτσι δεν φορτώνετε ποτέ ολόκληρο το αρχείο στη μνήμη.

### Βήμα 1: Επιλέξτε τη μορφή αρχείου που χρειάζεστε
Αποφασίστε ποια μορφή βασισμένη σε tar ταιριάζει καλύτερα με το συμβιβασμό συμπίεσης‑ταχύτητας:

- **TarBz2** – Υψηλότερος λόγος συμπίεσης (≈30 % μικρότερο από TarGz) αλλά πιο αργό.  
- **TarGz** – Καλός συμβιβασμός ταχύτητας και μεγέθους· ιδανικό για τις περισσότερες περιπτώσεις αποθήκευσης στο cloud.  
- **TarLz / TarXz** – Πολύ υψηλή συμπίεση με μέτρια ταχύτητα, χρήσιμη για αποθήκευση αρχείων.  
- **TarZ** – Κληρονομική μορφή για συμβατότητα με παλαιότερα εργαλεία Unix.

### Βήμα 2: Δημιουργήστε μια νέα παρουσία `Archive`
`Archive` είναι το αντικείμενο υψηλότερου επιπέδου που αντιπροσωπεύει ένα μοναδικό αρχείο αρχείου στη μνήμη.  

Η κλάση `Archive` διαχειρίζεται τη ροή συσκευασίας και συμπίεσης, εκθέτοντας μεθόδους για προσθήκη καταχωρήσεων και εγγραφή του τελικού αρχείου.

### Βήμα 3: Προσθέστε αρχεία και φακέλους
Μπορείτε να προσθέσετε ολόκληρο δέντρο καταλόγου με `AddAll` ή να προσθέσετε μεμονωμένα αρχεία με `AddFile`. Η διατήρηση της αρχικής ιεραρχίας φακέλων είναι τόσο απλή όσο η παροχή της διαδρομής του βασικού καταλόγου.

### Βήμα 4: Ορίστε τον επιθυμητό τύπο συμπίεσης
`CompressionType` απαριθμεί τους υποστηριζόμενους αλγόριθμους.  

`CompressionType` ορίζει τον αλγόριθμο (BZip2, GZip, LZMA, XZ, κ.λπ.) που θα εφαρμοστεί στη ροή TAR κατά την αποθήκευση.

### Βήμα 5: Αποθηκεύστε το αρχείο
`ArchiveFormat` είναι ένα σύνολο enum (π.χ., `TarBz2`, `TarGz`) που ενημερώνει τον γράφτη ποιο κοντέινερ και ποια συμπίεση να χρησιμοποιήσει.  

Η κλήση του `Save` γράφει το αρχείο στο δίσκο χρησιμοποιώντας την επιλεγμένη μορφή.

### Βήμα 6: Εξαγωγή αρχείων με κωδικούς πρόσβασης
`ArchiveEntry` αντιπροσωπεύει μία μεμονωμένη καταχώρηση αρχείου ή καταλόγου μέσα σε ένα αρχείο.  

Για να εξάγετε ένα zip με προστασία κωδικού πρόσβασης, ανοίξτε το αρχείο, εντοπίστε κάθε `ArchiveEntry`, ορίστε την ιδιότητα `Password` του και καλέστε `Extract`. Αυτό το μοντέλο κωδικού ανά καταχώρηση σας επιτρέπει να προστατεύετε μεμονωμένα αρχεία μέσα σε ένα μόνο zip.

### Βήμα 7: Επαληθεύστε το αποτέλεσμα
Μετά την εξαγωγή, συγκρίνετε τα μεγέθη των αρχείων και τα αθροίσματα ελέγχου SHA‑256 για να επιβεβαιώσετε ότι η διαδρομή του αρχείου διατήρησε την ακεραιότητα των δεδομένων.

## Συνηθισμένες Περιπτώσεις Χρήσης
- **Εργαλεία αντιγράφων ασφαλείας** – Αποθηκεύστε καθημερινά αντίγραφα ως `.tar.bz2` για μείωση του κόστους αποθήκευσης έως και 30 %.  
- **Ανταλλαγή δεδομένων μεταξύ πλατφορμών** – Οι μορφές βασισμένες σε Tar κατανοούνται εγγενώς από εργαλεία Linux, macOS και Windows.  
- **Ασφαλής διανομή** – Αναθέστε κωδικούς πρόσβασης σε ευαίσθητες καταχωρήσεις, ικανοποιώντας απαιτήσεις συμμόρφωσης χωρίς πρόσθετα εργαλεία κρυπτογράφησης.

## Επίλυση Προβλημάτων & Συμβουλές
- **Μεγάλα αρχεία** – Προτιμήστε το streaming API (`Archive.CreateEntryFromFile`) για χαμηλή χρήση μνήμης.  
- **Ασυμφωνίες κωδικού** – Ο κωδικός που ορίζεται σε κάθε `ArchiveEntry` πρέπει να ταιριάζει ακριβώς· διαφορετικά θα προκληθεί `InvalidPasswordException`.  
- **Επίπεδο συμπίεσης** – Το BZIP2 δεν εκθέτει προσαρμοσμένα επίπεδα· εάν χρειάζεστε πιο ακριβή έλεγχο, μεταβείτε σε LZMA (`CompressionType.LZMA`) ή XZ (`CompressionType.XZ`).  

## Συχνές Ερωτήσεις

**Q: Πώς να δημιουργήσω ένα αρχείο TarGz;**  
A: Ορίστε `CompressionType.GZip` και χρησιμοποιήστε `ArchiveFormat.TarGz` κατά την κλήση του `Save`. Αυτό παράγει ένα αρχείο `.tar.gz` σε ένα βήμα.

**Q: Μπορώ να εξάγω ένα αρχείο με προστασία κωδικού πρόσβασης χωρίς να γνωρίζω τον κωδικό;**  
A: Όχι. Κάθε καταχώρηση πρέπει να του δοθεί ο σωστός κωδικός· διαφορετικά η εξαγωγή αποτυγχάνει με `InvalidPasswordException`.

**Q: Υποστηρίζει το Aspose.Zip την εξαγωγή αρχείων με διαφορετικούς κωδικούς ανά καταχώρηση;**  
A: Ναι. Αναθέστε έναν κωδικό σε κάθε `ArchiveEntry` ξεχωριστά πριν καλέσετε `Extract`.

**Q: Ποια μορφή παρέχει την καλύτερη συμπίεση;**  
A: Το TarBz2 συνήθως δίνει το μικρότερο μέγεθος, ακολουθούμενο από TarLz και TarXz. Το TarGz προσφέρει μια πιο γρήγορη, ακόμη αποτελεσματική εναλλακτική.

**Q: Υπάρχει όριο στον αριθμό των αρχείων που μπορώ να προσθέσω σε ένα αρχείο TAR;**  
A: Στην πράξη δεν υπάρχει, αλλά εξαιρετικά μεγάλα αρχεία (>10 GB) μπορεί να ωφεληθούν από το διαχωρισμό σε πολλαπλά τμήματα για ευκολότερη διαχείριση.

## Εκπαιδευτικά για Εξαγωγή Αρχείων και Μορφές

### [Συμπίεση Αρχείων σε TarBz2 με Aspose.Zip για .NET](./compress-to-tar-bz2/)
Μάθετε πώς να συμπιέζετε αρχεία σε μορφή TarBz2 στο .NET χρησιμοποιώντας το Aspose.Zip. Ακολουθήστε τον οδηγό βήμα‑προς‑βήμα για αποτελεσματική συμπίεση αρχείων.

### [Συμπίεση σε TarGz με Aspose.Zip για .NET](./compress-to-tar-gz/)
Εξερευνήστε αποτελεσματική συμπίεση αρχείων στο .NET με το Aspose.Zip. Συμπιέστε σε TarGz με ευκολία.

### [Συμπίεση σε TarLz με Aspose.Zip για .NET](./compress-to-tar-lz/)
Συμπιέστε αρχεία στο .NET με το Aspose.Zip χωρίς κόπο. Μάθετε να δημιουργείτε αρχεία TarLz βήμα‑προς‑βήμα.

### [Συμπίεση σε TarXz με Aspose.Zip για .NET](./compress-to-tar-xz/)
Μάθετε να συμπιέζετε αρχεία σε μορφή TarXz στο .NET χρησιμοποιώντας το Aspose.Zip. Ακολουθήστε τον οδηγό μας για αποδοτική αποθήκευση και μετάδοση.

### [Συμπίεση σε TarZ με Aspose.Zip για .NET](./compress-to-tar-z/)
Εξερευνήστε τη βήμα‑προς‑βήμα συμπίεση σε TarZ χρησιμοποιώντας το Aspose.Zip για .NET. Αποτελεσματική διαχείριση αρχείων για τα .NET έργα σας.

### [Εξαγωγή Καταχωρήσεων Αρχείου με Διαφορετικούς Κωδικούς στο Aspose.Zip για .NET](./extract-archive-different-passwords/)
Μάθετε πώς να εξάγετε καταχωρήσεις αρχείου με διαφορετικούς κωδικούς στο Aspose.Zip για .NET. Ενισχύστε την ασφάλεια και την ευελιξία στις εφαρμογές σας.

---

**Τελευταία Ενημέρωση:** 2026-06-19  
**Δοκιμάστηκε Με:** Aspose.Zip for .NET 24.11  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία αρχείου tar και προσθήκη αρχείων στο tar με Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Πώς να συμπιέσετε tar και να δημιουργήσετε TarBz2 με Aspose.Zip για .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Προσθήκη αρχείων στο tar και δημιουργία αρχείου tarxz με Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}