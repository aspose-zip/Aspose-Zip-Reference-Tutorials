---
title: Защитите свои файлы шифрование AES с помощью Aspose.Zip
linktitle: Защита паролем с помощью AES
second_title: Aspose.Zip .NET API для сжатия и архивирования файлов
description: Узнайте, как повысить безопасность ваших файлов с помощью Aspose.Zip для .NET с шифрованием AES. Следуйте нашему пошаговому руководству для оптимальной защиты.
type: docs
weight: 11
url: /ru/net/password-protection-and-encryption/password-protect-with-aes/
---

## Введение

Защита ваших конфиденциальных файлов имеет решающее значение в современную цифровую эпоху, и Aspose.Zip для .NET предоставляет надежное решение для защиты паролем ваших архивов с использованием расширенного стандарта шифрования (AES). В этом руководстве мы рассмотрим, как реализовать шифрование AES с тремя длинами ключей — 128-бит, 192-бит и 256-бит, — обеспечивая высочайший уровень безопасности ваших сжатых файлов.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

-  Aspose.Zip для .NET: убедитесь, что библиотека Aspose.Zip интегрирована в ваш проект .NET. Вы можете скачать его[здесь](https://releases.aspose.com/zip/net/).

- Каталог документов: укажите каталог, в котором расположены исходные файлы.

## Импортировать пространства имен

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Шаг 1. Защита паролем с помощью AES-128.

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

На этом этапе мы создаем zip-файл и защищаем его шифрованием AES-128. Пароль «p@s$» обеспечивает безопасность вашего архива.

## Шаг 2. Защита паролем с помощью AES-192.

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

На этом шаге показано, как реализовать шифрование AES-192 для повышения безопасности. Для обеспечения единообразия используется тот же пароль «p@s$».

## Шаг 3. Защита паролем с помощью AES-256.

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

На этом последнем этапе мы реализуем самый высокий уровень шифрования AES-256, обеспечивающий дополнительный уровень безопасности ваших сжатых файлов.

## Заключение

В этом руководстве мы рассмотрели основные шаги по защите паролем ваших архивов с использованием шифрования AES в Aspose.Zip для .NET. Независимо от того, выберете ли вы 128-битное, 192-битное или 256-битное шифрование, ваши файлы будут защищены от несанкционированного доступа.

## Часто задаваемые вопросы

### Могу ли я использовать Aspose.Zip для .NET с другими языками программирования?
Aspose.Zip в первую очередь разработан для приложений .NET, обеспечивая плавную интеграцию и оптимальную производительность.

### Безопасен ли метод шифрования AES для конфиденциальных данных?
Да, шифрование AES широко признано как безопасный и надежный метод защиты конфиденциальной информации.

### Могу ли я изменить пароль для уже зашифрованного архива?
Нет, пароль для зашифрованного архива нельзя изменить после его установки. Вам нужно будет создать новый зашифрованный архив с другим паролем.

### Существуют ли какие-либо ограничения на типы файлов, которые можно зашифровать с помощью Aspose.Zip?
Aspose.Zip поддерживает шифрование различных типов файлов, обеспечивая гибкость в защите различных типов данных.

### Что произойдет, если я забуду пароль от зашифрованного архива?
К сожалению, восстановить пароль зашифрованного архива невозможно. Крайне важно хранить пароль в безопасном месте.
