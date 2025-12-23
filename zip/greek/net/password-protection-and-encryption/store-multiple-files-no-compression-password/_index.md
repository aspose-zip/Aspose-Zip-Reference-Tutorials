---
date: 2025-12-23
description: Μάθετε πώς να προστατεύετε με κωδικό πρόσβασης αρχεία zip και πώς να
  κρυπτογραφείτε ένα αρχείο zip χρησιμοποιώντας το Aspose.Zip για .NET. Αποθηκεύστε
  πολλαπλά αρχεία χωρίς συμπίεση με έναν ασφαλή κωδικό πρόσβασης.
linktitle: Store Multiple Files Without Compression with Password
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Πώς να προστατεύσετε με κωδικό ένα αρχείο ZIP με το Aspose.Zip για .NET
url: /el/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προστατεύσετε με κωδικό πρόσβασης ένα ZIP με Aspose.Zip για .NET

Στη σύγχρονη ανάπτυξη .NET, η ασφάλεια των αρχείων σας είναι εξίσου σημαντική με τη συμπίεσή τους. Αυτό το tutorial δείχνει **how to password protect zip** αρχεία χρησιμοποιώντας το Aspose.Zip για .NET, ενώ επίσης παρουσιάζει πώς να **create zip archive .net** χωρίς συμπίεση και πώς να **how to encrypt zip archive** με κρυπτογράφηση AES. Στο τέλος αυτού του οδηγού θα έχετε μια σαφή, βήμα‑βήμα λύση που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο C#.

## Γρήγορες Απαντήσεις
- **What is the primary library?** Aspose.Zip for .NET  
- **Can I store files without compression?** Yes – use `StoreCompressionSettings`.  
- **How do I add a password?** Provide an `AesEcryptionSettings` instance with your password.  
- **Is AES‑256 supported?** Absolutely – set `EncryptionMethod.AES256`.  
- **What .NET versions work?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Τι είναι το “how to password protect zip”;
Η προστασία με κωδικό πρόσβασης προσθέτει ένα επίπεδο κρυπτογράφησης σε ένα αρχείο ZIP, εξασφαλίζοντας ότι μόνο οι χρήστες που γνωρίζουν τον κωδικό μπορούν να εξάγουν τα περιεχόμενά του. Το Aspose.Zip κάνει αυτή τη διαδικασία απλή, επιτρέποντάς σας να ορίσετε τις ρυθμίσεις κρυπτογράφησης κατά τη δημιουργία του αρχείου.

## Γιατί να χρησιμοποιήσετε Aspose.Zip για .NET;
- **No external dependencies** – pure .NET library.  
- **Full control** over compression, encryption, and archive structure.  
- **Supports modern encryption** methods like AES‑256.  
- **Handles large files** efficiently with streaming APIs.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

- **Aspose.Zip for .NET Library** – download it **[here](https://releases.aspose.com/zip/net/)**.  
- **Document Directory** – a folder that contains the files you want to archive. In the examples, the variable `dataDir` points to this location.

## Εισαγωγή Namespaces

Πρώτα, εισάγετε τα namespaces που απαιτούνται για εργασία με το Aspose.Zip:

```csharp
// The path to the resource directory.
string dataDir = "Your Document Directory"

// Import Aspose.Zip namespaces
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Πώς να δημιουργήσετε Zip Archive .NET χωρίς συμπίεση

### Βήμα 1: Άνοιγμα του αρχείου Zip

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

Εδώ δημιουργούμε ένα νέο αρχείο αρχείου που θα περιέχει τις καταχωρήσεις μας. Η σημαία `FileMode.Create` εξασφαλίζει ότι δημιουργείται ένα φρέσκο αρχείο σε κάθε εκτέλεση.

### Βήμα 2: Άνοιγμα του αρχείου προέλευσης

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Ανοίγουμε το πρώτο αρχείο προέλευσης (`alice29.txt`). Μπορείτε να επαναλάβετε αυτό το τμήμα για επιπλέον αρχεία που θέλετε να αποθηκεύσετε.

### Βήμα 3: Δημιουργία Αρχείου με “zip archive without compression”

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

- `StoreCompressionSettings()` tells Aspose.Zip **not to compress** the file, giving you a **zip archive without compression**.  
- `AesEcryptionSettings("p@s$", EncryptionMethod.AES256)` is where we **how to encrypt zip archive** – the password is `"p@s$"` and the encryption method is AES‑256.

### Βήμα 4: Προσθήκη καταχώρησης στο αρχείο και αποθήκευση

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Το αρχείο προστίθεται στο αρχείο και το αρχείο αποθηκεύεται στο δίσκο, ολοκληρώνοντας τη διαδικασία **how to password protect zip**.

## Συνηθισμένα Πιθανά Σφάλματα & Συμβουλές

- **Password Complexity** – Use a strong password; simple strings are easy to brute‑force.  
- **Stream Disposal** – The `using` statements automatically close streams, preventing file locks.  
- **Multiple Files** – To add more files, simply open additional `FileStream` objects and call `CreateEntry` for each.  
- **Compatibility** – AES‑256 encrypted ZIPs are supported by most modern archive tools (WinRAR, 7‑Zip, etc.).

## Συχνές Ερωτήσεις

**Q: Can I use other encryption methods besides AES‑256?**  
A: Yes, Aspose.Zip supports ZipCrypto and other AES levels. Adjust the `EncryptionMethod` enum accordingly.

**Q: Is it possible to encrypt an existing archive?**  
A: You need to recreate the archive with the desired encryption settings; Aspose.Zip does not modify encryption on the fly.

**Q: Does storing files without compression increase archive size?**  
A: Slightly, because the original file bytes are stored directly. This is useful when you need fast extraction or want to preserve original file integrity.

**Q: How do I retrieve the password‑protected files?**  
A: Open the archive with an `Archive` instance that includes the same `AesEcryptionSettings` (password) used during creation.

**Q: Are there limits on file size or number of entries?**  
A: Aspose.Zip handles large files and thousands of entries, limited only by system memory and storage.

## Πρόσθετοι Πόροι

- **Aspose.Zip Documentation** – detailed API reference **[here](https://reference.aspose.com/zip/net/)**.  
- **Community Support** – ask questions on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.  
- **Free Trial** – get a trial version **[here](https://releases.aspose.com/)**.  
- **Temporary License** – request a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.  
- **Purchase Options** – buy a full license **[here](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}