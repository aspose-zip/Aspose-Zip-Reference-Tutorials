---
title: Zabezpečte své soubory – šifrování AES pomocí Aspose.Zip
linktitle: Ochrana heslem pomocí AES
second_title: Aspose.Zip .NET API pro kompresi a archivaci souborů
description: Zjistěte, jak zvýšit zabezpečení souborů pomocí Aspose.Zip for .NET se šifrováním AES. Pro optimální ochranu postupujte podle našeho podrobného průvodce.
weight: 11
url: /cs/net/password-protection-and-encryption/password-protect-with-aes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zabezpečte své soubory – šifrování AES pomocí Aspose.Zip


## Úvod

Zabezpečení vašich citlivých souborů je v dnešní digitální době zásadní a Aspose.Zip for .NET poskytuje robustní řešení pro ochranu vašich archivů heslem pomocí Advanced Encryption Standard (AES). V tomto tutoriálu prozkoumáme, jak implementovat šifrování AES se třemi délkami klíče – 128-bit, 192-bit a 256-bit – zajišťující nejvyšší úroveň zabezpečení vašich komprimovaných souborů.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Zip for .NET: Ujistěte se, že máte knihovnu Aspose.Zip integrovanou do vašeho projektu .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/zip/net/).

- Adresář dokumentů: Mít adresář, kde jsou umístěny zdrojové soubory.

## Importovat jmenné prostory

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Krok 1: Ochrana heslem pomocí AES-128

```csharp
//ExStart:PasswordProtectWithAES128
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES128_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES128))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: PasswordProtectWithAES128
```

tomto kroku vytvoříme soubor zip a chráníme jej šifrováním AES-128. Heslo "p@s$" zajišťuje bezpečnost vašeho archivu.

## Krok 2: Ochrana heslem pomocí AES-192

```csharp
//ExStart:PasswordProtectWithAES192
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES192_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES192))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
//ExEnd: PasswordProtectWithAES192
```

Tento krok ukazuje, jak implementovat šifrování AES-192 pro lepší zabezpečení. Pro konzistenci se používá stejné heslo "p@s$".

## Krok 3: Ochrana heslem pomocí AES-256

```csharp
//ExStart:PasswordProtectWithAES256
using (FileStream zipFile = File.Open(dataDir + "PasswordProtectWithAES256_out.zip", FileMode.Create))
{
    using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
    {
        using (var archive = new Archive(new ArchiveEntrySettings(null, new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
        {
            archive.CreateEntry("alice29.txt", source1);
            archive.Save(zipFile);
        }
    }
}
// ExEnd: PasswordProtectWithAES256
```

V tomto posledním kroku implementujeme nejvyšší úroveň šifrování, AES-256, která poskytuje další vrstvu zabezpečení pro vaše komprimované soubory.

## Závěr

V tomto tutoriálu jsme probrali základní kroky k ochraně vašich archivů heslem pomocí šifrování AES v Aspose.Zip pro .NET. Ať už zvolíte 128bitové, 192bitové nebo 256bitové šifrování, vaše soubory budou v bezpečí před neoprávněným přístupem.

## Často kladené otázky

### Mohu používat Aspose.Zip pro .NET s jinými programovacími jazyky?
Aspose.Zip je primárně určen pro aplikace .NET, zajišťuje bezproblémovou integraci a optimální výkon.

### Je metoda šifrování AES bezpečná pro citlivá data?
Ano, šifrování AES je široce uznáváno jako bezpečný a robustní způsob ochrany citlivých informací.

### Mohu změnit heslo k již zašifrovanému archivu?
Ne, heslo pro šifrovaný archiv nelze změnit, jakmile je nastaveno. Budete muset vytvořit nový šifrovaný archiv s jiným heslem.

### Existují nějaká omezení pro typy souborů, které lze šifrovat pomocí Aspose.Zip?
Aspose.Zip podporuje šifrování různých typů souborů a zajišťuje flexibilitu při zabezpečení různých druhů dat.

### Co se stane, když zapomenu heslo k šifrovanému archivu?
Bohužel neexistuje způsob, jak obnovit heslo zašifrovaného archivu. Je důležité uchovávat heslo na bezpečném místě.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
