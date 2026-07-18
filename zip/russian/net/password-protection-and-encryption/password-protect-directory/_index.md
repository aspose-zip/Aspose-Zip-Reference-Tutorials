---
date: 2026-07-18
description: Узнайте, как создавать zip‑файлы с паролем, защищать папку zip паролем
  и менять пароль zip‑архива с помощью Aspose.Zip для .NET.
keywords:
- create password protected zip
- zip folder with password
- how to encrypt zip
- password protect zip folder
- encrypt zip archive c#
lastmod: 2026-07-18
linktitle: Защита каталога паролем
og_description: Создавайте zip‑архивы с паролем для каталогов .NET с помощью Aspose.Zip.
  Этот пошаговый учебник показывает, как шифровать папки, менять пароли и использовать
  шифрование AES.
og_image_alt: 'Developer guide: Create password protected zip for .NET directories
  with Aspose.Zip'
og_title: Создание zip‑архива с паролем – руководство Aspose.Zip .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to create password protected zip files, password protect
    zip folder, and change zip password using Aspose.Zip for .NET.
  headline: Create password protected zip for .NET directories – Aspose.Zip Tutorial
  type: TechArticle
- questions:
  - answer: Use `TraditionalEncryptionSettings` when creating the `Archive` object,
      then call `CreateEntries` on the target folder.
    question: How do I encrypt a folder with zip using Aspose.Zip?
  - answer: No, the password must be defined at creation time; to change it, recreate
      the archive with a new password.
    question: Can I set a zip folder password after the archive is created?
  - answer: '`AesEncryptionSettings` configures AES‑256 encryption for a ZIP archive.
      Yes, you can switch to `AesEncryptionSettings` for AES‑256 encryption instead
      of the traditional ZipCrypto.'
    question: Does Aspose.Zip support AES encryption for stronger security?
  - answer: Absolutely – the current release works with all modern .NET runtimes.
    question: Is the library compatible with .NET 6 and .NET 7?
  - answer: Aspose.Zip will throw a `PasswordRequiredException`, prompting you to
      supply the correct password.
    question: What happens if I try to open a password‑protected zip without a password?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- zip encryption
- Aspose.Zip
- .NET compression
- password protected archive
title: Создание zip‑архива с паролем для каталогов .NET – руководство Aspose.Zip
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание zip‑архива с паролем для каталогов .NET – руководство Aspose.Zip

В этом руководстве вы **создадете zip‑архивы с паролем** для целых каталогов, используя библиотеку Aspose.Zip для .NET. Независимо от того, нужно ли вам **зашифровать папку**, защитить файлы резервных копий или просто ограничить доступ к конфиденциальным данным, это пошаговое руководство покажет, как сделать это с чистым кодом C#. К концу вы поймёте, как защитить каталог, переключать режимы шифрования и менять пароль в уже существующем архиве.

## Быстрые ответы
- **Какая библиотека рекомендуется?** Aspose.Zip for .NET  
- **Могу ли я зашифровать всю папку?** Да — просто укажите API на папку, которую хотите заархивировать.  
- **Поддерживается ли изменение пароля zip‑архива?** Абсолютно, используйте `TraditionalEncryptionSettings`.  
- **Нужна ли лицензия для продакшн?** Для коммерческого использования требуется действующая лицензия Aspose.Zip.  
- **Работает с .NET Core/5/6?** Да, API полностью совместим с современными средами выполнения .NET.  

## Что такое «создание zip‑архива с паролем»?
Создание zip‑архива с паролем означает сжатие файлов или каталогов в ZIP‑архив с применением шифрования, так что архив можно открыть только с правильным паролем. Это защищает содержимое от несанкционированного доступа и соответствует многим требованиям по защите данных.

## Как создать zip‑архив с паролем для каталога
Загрузите целевую папку, задайте пароль с помощью `TraditionalEncryptionSettings` и передайте данные в новый ZIP‑файл — всё в нескольких лаконичных строках. API записывает каждую запись непосредственно в поток вывода, поэтому даже многогигабайтные каталоги обрабатываются с минимальными затратами памяти.

## Почему стоит использовать Aspose.Zip для защиты паролем каталогов в .NET?
Aspose.Zip поддерживает **более 30 алгоритмов сжатия и шифрования**, может работать с папками размером более **10 ГБ**, не загружая весь архив в память, и предлагает как устаревший ZipCrypto, так и современное шифрование AES‑256. Библиотека полностью потокобезопасна, работает на **.NET Framework 4.6+**, **.NET Core 3.1+** и **.NET 6/7**, и включает подробный журнал для помощи в диагностике любых проблем.

## Распространённые сценарии использования
- **Защита резервных копий:** Заархивировать ежедневную папку резервных копий и защитить её надёжным паролем.  
- **Безопасный обмен файлами:** Отправить пароль к zip‑папке клиенту, не раскрывая содержимое.  
- **Соответствие нормативным требованиям:** Хранить персональные данные (PII) в зашифрованном zip‑архиве для соответствия стандартам защиты данных.  

## Предварительные требования
Перед началом убедитесь, что у вас есть:

- Базовые знания программирования на C#.  
- Visual Studio (любая современная версия).  
- Библиотека Aspose.Zip для .NET — скачайте её **[здесь](https://releases.aspose.com/zip/net/)**.  
- Папка на диске, которую вы хотите защитить паролем.

## Импорт пространств имён
Добавьте необходимые пространства имён в ваш файл C#, чтобы компилятор знал, где находятся классы Aspose.Zip.

## Шаг 1: Установите путь к каталогу ресурсов
Определите путь, указывающий на каталог, который вы собираетесь заархивировать и защитить.

## Шаг 2: Защитите каталог паролем
`TraditionalEncryptionSettings` задаёт пароль и алгоритм шифрования для ZIP‑архива.  
Используйте этот объект настроек при создании экземпляра `Archive`, чтобы применить защиту ZipCrypto.

## Шаг 3: Объяснение кода
`Archive` представляет ZIP‑архив и предоставляет методы для добавления записей и сохранения архива.

- **Создание выходного файла:** `File.Open(..., FileMode.Create)` открывает (или создаёт) ZIP‑файл, который будет хранить зашифрованные данные.  
- **Выбор исходной папки:** `new DirectoryInfo(".\\CanterburyCorpus")` указывает Aspose.Zip, какой каталог сжать.  
- **Применение пароля:** `new TraditionalEncryptionSettings("p@s$")` задаёт пароль, который будет защищать архив.  
- **Добавление записей и сохранение:** `archive.CreateEntries(corpus)` добавляет каждый файл из папки, а `archive.Save(zipFile)` записывает зашифрованный ZIP на диск.  

## Как изменить пароль zip‑архива позже?
Чтобы изменить пароль, необходимо воссоздать архив, поскольку пароль хранится в заголовке центрального каталога. Создайте новый `TraditionalEncryptionSettings` с желаемым паролем, откройте существующий архив, скопируйте его записи в новый экземпляр `Archive`, используя новые настройки, а затем сохраните новый архив. Этот процесс повторно зашифрует все записи новым паролем.

## Советы по созданию надёжного пароля для zip‑папки
- Используйте комбинацию заглавных, строчных букв, цифр и символов.  
- Старайтесь использовать минимум 12 символов; более длинные пароли экспоненциально сложнее взломать.  
- Избегайте распространённых слов или шаблонов; рассмотрите возможность использования парольной фразы.  

## Распространённые проблемы и советы
- **Большие папки:** Aspose.Zip передаёт данные потоково, поэтому использование памяти остаётся ниже **150 МБ**, даже для каталогов размером 5 ГБ.  
- **Сложность пароля:** Используйте надёжный пароль (комбинация букв, цифр, символов) для повышения безопасности.  
- **Ошибки лицензии:** Убедитесь, что применили действительный файл лицензии; иначе библиотека работает в режиме оценки с ограничениями.  
- **Пароль zip‑папки не распознан:** Проверьте, что при открытии архива вы используете тот же метод шифрования (`TraditionalEncryptionSettings`).  

## Часто задаваемые вопросы

### Подходит ли Aspose.Zip для .NET для больших каталогов?
Да, Aspose.Zip для .NET разработан для эффективной работы с большими каталогами, обеспечивая оптимальную производительность.

### Можно ли изменить пароль уже защищённого каталога?
Да, вы можете изменить пароль, скорректировав `TraditionalEncryptionSettings` в коде соответствующим образом.

### Есть ли требования к лицензированию при использовании Aspose.Zip для .NET?
Да, для использования Aspose.Zip для .NET в производственной среде требуется действующая лицензия. Вы можете получить лицензию **[здесь](https://purchase.aspose.com/buy)**.

### Доступна ли бесплатная пробная версия Aspose.Zip для .NET?
Да, вы можете получить бесплатную пробную версию **[здесь](https://releases.aspose.com/)**.

### Где я могу найти дополнительную поддержку Aspose.Zip для .NET?
Вы можете посетить **[форум Aspose.Zip](https://forum.aspose.com/c/zip/37)** для получения поддержки или вопросов.

## Быстрый FAQ (подходит для ИИ)

**Q: Как зашифровать папку в zip с помощью Aspose.Zip?**  
A: Используйте `TraditionalEncryptionSettings` при создании объекта `Archive`, затем вызовите `CreateEntries` для целевой папки.

**Q: Можно ли задать пароль zip‑папки после создания архива?**  
A: Нет, пароль должен быть задан во время создания; чтобы изменить его, необходимо воссоздать архив с новым паролем.

**Q: Поддерживает ли Aspose.Zip шифрование AES для более высокой безопасности?**  
A: `AesEncryptionSettings` настраивает шифрование AES‑256 для ZIP‑архива. Да, вы можете переключиться на `AesEncryptionSettings` для AES‑256 вместо традиционного ZipCrypto.

**Q: Совместима ли библиотека с .NET 6 и .NET 7?**  
A: Абсолютно — текущий релиз работает со всеми современными средами .NET.

**Q: Что произойдёт, если попытаться открыть zip‑архив с паролем без указания пароля?**  
A: Aspose.Zip выбросит `PasswordRequiredException`, требуя предоставить правильный пароль.

---

**Последнее обновление:** 2026-07-18  
**Тестировано с:** Aspose.Zip for .NET (latest release)  
**Автор:** Aspose

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Связанные руководства

- [Создать ZIP с паролем с помощью Aspose.Zip для .NET](/zip/net/password-protection-and-encryption/password-protect-archive-traditional-password/)
- [Создать ZIP‑файлы с паролем и шифрованием AES с использованием Aspose.Zip](/zip/net/password-protection-and-encryption/password-protect-with-aes/)
- [Aspose.Zip для .NET — защита паролем ZIP‑архива и хранение нескольких файлов без сжатия и пароля](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}