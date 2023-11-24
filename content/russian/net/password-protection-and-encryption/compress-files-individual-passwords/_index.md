---
title: Безопасное сжатие файлов в .NET с помощью Aspose.Zip
linktitle: Сжатие файлов с индивидуальными паролями
second_title: Aspose.Zip .NET API для сжатия и архивирования файлов
description: Узнайте, как повысить безопасность файлов в приложениях .NET! Следуйте нашему пошаговому руководству по сжатию файлов с отдельными паролями с помощью Aspose.Zip для .NET.
type: docs
weight: 16
url: /ru/net/password-protection-and-encryption/compress-files-individual-passwords/
---

## Введение

В мире разработки .NET эффективное управление файлами и их сжатие является важнейшей задачей. Aspose.Zip для .NET предоставляет мощное решение для сжатия файлов, предлагая различные функции для улучшения ваших приложений. Одной из примечательных особенностей является возможность сжимать файлы с отдельными паролями, обеспечивая дополнительный уровень безопасности. В этом уроке мы покажем вам процесс сжатия файлов с отдельными паролями с помощью Aspose.Zip для .NET.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

-  Aspose.Zip для .NET: убедитесь, что в вашем проекте .NET установлена библиотека Aspose.Zip. Вы можете найти необходимую документацию[здесь](https://reference.aspose.com/zip/net/).

-  Загрузка: Если вы еще этого не сделали, загрузите библиотеку Aspose.Zip для .NET с сайта[эта ссылка](https://releases.aspose.com/zip/net/).

- Каталог документов: подготовьте каталог, содержащий файлы, которые вы хотите сжать.

## Импортировать пространства имен

В вашем проекте .NET обязательно импортируйте необходимые пространства имен:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Шаг 1. Установите путь к каталогу ресурсов

Определите путь к каталогу ресурсов, в котором расположены ваши файлы.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2. Сжатие файлов с индивидуальными паролями

Теперь давайте сожмем файлы с индивидуальными паролями. Мы будем использовать три файла примера (`alice29.txt`, `asyoulik.txt` , и`fields.c`) с разными паролями для каждого.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Сжимайте каждый файл с индивидуальным паролем
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Сохраните сжатые файлы
        archive.Save(zipFile);
    }
}
```

## Заключение

Поздравляем! Вы успешно научились сжимать файлы с отдельными паролями с помощью Aspose.Zip для .NET. Эта функция добавляет дополнительный уровень безопасности к вашим сжатым файлам, обеспечивая конфиденциальность.

## Часто задаваемые вопросы (FAQ)

### Могу ли я использовать разные методы шифрования для каждого файла?
Да, Aspose.Zip для .NET позволяет использовать разные методы шифрования для каждого файла во время сжатия.

### Доступна ли пробная версия?
 Да, вы можете получить доступ к бесплатной пробной версии Aspose.Zip для .NET.[здесь](https://releases.aspose.com/).

### Как я могу получить поддержку, если у меня возникнут проблемы?
 Посетить[Форум Aspose.Zip](https://forum.aspose.com/c/zip/37) за помощь сообщества и поддержку Aspose.

### Где я могу найти подробную документацию по Aspose.Zip для .NET?
 Документация доступна[здесь](https://reference.aspose.com/zip/net/).

### Могу ли я приобрести временную лицензию для тестирования?
 Да, вы можете приобрести временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
