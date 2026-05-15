---
date: 2026-05-15
description: Узнайте, как создавать ZIP‑файлы, защищённые паролем, и сжимать файлы
  с паролями с помощью Aspose.Zip для .NET в несколько простых шагов.
keywords:
- create password protected zip
- compress files with passwords
- Aspose.Zip .NET
linktitle: Сжатие файлов с отдельными паролями
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to create password protected zip files and compress files
    with passwords using Aspose.Zip for .NET in a few simple steps.
  headline: Create Password Protected ZIP in .NET with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip lets you choose the encryption algorithm (e.g., AES‑256)
      for each entry when you add it to the archive.
    question: Can I use different encryption methods for each file?
  - answer: Yes, you can access the free trial of Aspose.Zip for .NET [here](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance
      from the community and Aspose support.
    question: How can I get support if I encounter issues?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/).
    question: Where can I find detailed documentation for Aspose.Zip for .NET?
  - answer: Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создание ZIP-файла с паролем в .NET с помощью Aspose.Zip
url: /ru/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание ZIP‑архива с паролем в .NET с помощью Aspose.Zip

## Введение

В этом руководстве вы узнаете, как **создавать ZIP‑файлы с паролем** в приложении .NET с использованием Aspose.Zip. Защищённое сжатие необходимо, когда требуется передавать конфиденциальные данные или хранить чувствительные документы, не раскрывая их неавторизованным лицам.

**Aspose.Zip** — это библиотека .NET, позволяющая программно создавать, читать и шифровать ZIP‑архивы. Она поддерживает шифрование AES‑256 и позволяет назначать уникальный пароль для каждой записи в архиве.

## Быстрые ответы
- **Что делает Aspose.Zip?** Он создаёт и управляет ZIP‑архивами, включая защиту паролем для отдельных файлов.  
- **Сколько паролей я могу назначить?** Один уникальный пароль на файл; количество записей не ограничено.  
- **Какой алгоритм шифрования используется?** AES‑256, обеспечивающий 256‑битную безопасность.  
- **Нужна ли лицензия для тестирования?** Доступна бесплатная пробная версия; для продакшн‑использования требуется лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Требования

Прежде чем приступить к руководству, убедитесь, что у вас есть следующие требования:

- Aspose.Zip для .NET: Убедитесь, что библиотека Aspose.Zip установлена в вашем проекте .NET. Необходимую документацию можно найти [здесь](https://reference.aspose.com/zip/net/).

- Загрузка: Если вы ещё не сделали этого, скачайте библиотеку Aspose.Zip для .NET по [этой ссылке](https://releases.aspose.com/zip/net/).

- Каталог документов: Подготовьте каталог, содержащий файлы, которые вы хотите сжать.

## Импорт пространств имён

В вашем проекте .NET убедитесь, что импортированы необходимые пространства имён:

`ZipFile` — основной класс Aspose.Zip для создания ZIP‑архивов и назначения индивидуальных паролей каждой записи.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Как создать ZIP‑архивы с паролем в .NET?

Загрузите целевую папку, создайте объект `ZipFile`, добавьте каждый файл со своим паролем и в конце вызовите `Save` для записи архива. Весь процесс требует всего несколько строк кода и гарантирует, что каждая запись зашифрована указанным вами паролем.

### Шаг 1: Установите путь к каталогу ресурсов

Укажите путь к каталогу ресурсов, где находятся ваши файлы.

```csharp
string dataDir = "Your Document Directory";
```

### Шаг 2: Сжать файлы с отдельными паролями

Теперь сожмём файлы с индивидуальными паролями. Мы используем три примерных файла (`alice29.txt`, `asyoulik.txt` и `fields.c`) с разными паролями для каждого.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

## Зачем использовать защиту паролем для ZIP‑архивов?

Aspose.Zip поддерживает **более 30 алгоритмов сжатия** и может шифровать архивы с помощью AES‑256, обеспечивая до **256‑битной защиты**. Он способен обрабатывать архивы размером в несколько сотен мегабайт без загрузки всего файла в память, что делает его идеальным для высокопроизводительных серверных сценариев. Кроме того, защита паролем помогает соответствовать нормативным требованиям, таким как GDPR и HIPAA, гарантируя, что чувствительные данные остаются зашифрованными как в состоянии покоя, так и при передаче.

## Заключение

Поздравляем! Вы успешно узнали, как **создавать ZIP‑файлы с паролем** и **сжимать файлы с паролями** с помощью Aspose.Zip для .NET. Эта функция добавляет дополнительный уровень защиты вашим сжатым файлам, обеспечивая конфиденциальность и соответствие политикам защиты данных.

## Часто задаваемые вопросы

**Q: Могу ли я использовать разные методы шифрования для каждого файла?**  
A: Да, Aspose.Zip позволяет выбрать алгоритм шифрования (например, AES‑256) для каждой записи при добавлении её в архив.

**Q: Доступна ли пробная версия?**  
A: Да, вы можете получить бесплатную пробную версию Aspose.Zip для .NET [здесь](https://releases.aspose.com/).

**Q: Как получить поддержку, если возникнут проблемы?**  
A: Посетите [форум Aspose.Zip](https://forum.aspose.com/c/zip/37) для получения помощи от сообщества и поддержки Aspose.

**Q: Где можно найти подробную документацию по Aspose.Zip для .NET?**  
A: Документация доступна [здесь](https://reference.aspose.com/zip/net/).

**Q: Можно ли приобрести временную лицензию для тестирования?**  
A: Да, временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**Последнее обновление:** 2026-05-15  
**Тестировано с:** Aspose.Zip 24.11 для .NET  
**Автор:** Aspose

## Связанные руководства

- [Создать ZIP‑архив с паролем с помощью Aspose.Zip для .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Защита ZIP‑файлов паролем с шифрованием AES с помощью Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Сжатие нескольких файлов с шифрованием в Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}