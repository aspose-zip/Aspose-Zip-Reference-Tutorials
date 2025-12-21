---
date: 2025-12-21
description: Узнайте, как создавать zip‑файлы с паролем в .NET, шифровать папки и
  менять пароль zip‑архива с помощью Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создание zip‑архива с паролем для каталогов .NET – учебник Aspose.Zip
url: /ru/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание zip‑архива с паролем для каталогов .NET – руководство Aspose.Zip

В этом руководстве вы **создадите zip‑архив с паролем** для целых каталогов, используя библиотеку Aspose.Zip для .NET. Независимо от того, нужно ли вам **зашифровать папку**, защитить файлы резервных копий или просто ограничить доступ к конфиденциальным данным, этот пошаговый туториал покажет, как сделать это чистым кодом C#.

## Быстрые ответы
- **Какая библиотека рекомендуется?** Aspose.Zip for .NET  
- **Могу ли я зашифровать всю папку?** Да — просто укажите API на папку, которую хотите заархивировать.  
- **Поддерживается ли изменение пароля zip‑архива?** Абсолютно, используйте `TraditionalEncryptionSettings`.  
- **Нужна ли лицензия для продакшна?** Для коммерческого использования требуется действующая лицензия Aspose.Zip.  
- **Работает с .NET Core/5/6?** Да, API полностью совместим с современными средами выполнения .NET.  

## Что означает «создать zip‑архив с паролем»?
Создание zip‑архива с паролем означает сжатие файлов или каталогов в ZIP‑архив с применением шифрования, так что архив можно открыть только с правильным паролем. Это защищает содержимое от несанкционированного доступа.

## Почему стоит использовать Aspose.Zip для защиты паролем каталогов в .NET?
Aspose.Zip предоставляет простой, высокопроизводительный API, поддерживающий **c# zip password protection**, традиционное шифрование ZipCrypto и AES‑шифрование. Он эффективно обрабатывает большие каталоги и без проблем интегрируется в любой проект .NET.

## Требования
- Базовые знания программирования на C#.  
- Visual Studio (любая современная версия).  
- Библиотека Aspose.Zip for .NET — скачайте её **[здесь](https://releases.aspose.com/zip/net/)**.  
- Папка на диске, которую вы хотите защитить паролем.

## Импорт пространств имён
Добавьте необходимые пространства имён в ваш файл C#, чтобы компилятор знал, где находятся классы Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Шаг 1: Установите путь к каталогу ресурсов
Определите путь, указывающий на каталог, который вы собираетесь заархивировать и защитить.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Защитите каталог паролем
Используйте `TraditionalEncryptionSettings` для указания пароля и создания зашифрованного архива. Это ядро **c# zip password protection**.

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

## Шаг 3: Объяснение кода
- **Создание выходного файла:** `File.Open(..., FileMode.Create)` открывает (или создаёт) ZIP‑файл, который будет содержать зашифрованные данные.  
- **Выбор исходной папки:** `new DirectoryInfo(".\\CanterburyCorpus")` указывает Aspose.Zip, какой каталог сжимать.  
- **Применение пароля:** `new TraditionalEncryptionSettings("p@s$")` задаёт пароль, который будет защищать архив.  
- **Добавление записей и сохранение:** `archive.CreateEntries(corpus)` добавляет каждый файл из папки, а `archive.Save(zipFile)` записывает зашифрованный ZIP на диск.

## Как изменить пароль zip‑архива позже?
Если вам нужно **изменить пароль zip‑архива**, просто пересоздайте архив с новым экземпляром `TraditionalEncryptionSettings`, содержащим новый пароль, и сохраните его снова.

## Распространённые проблемы и советы
- **Большие папки:** Aspose.Zip передаёт данные потоково, поэтому использование памяти остаётся низким даже для огромных каталогов.  
- **Сложность пароля:** Используйте надёжный пароль (сочетание букв, цифр, символов) для повышения безопасности.  
- **Ошибки лицензии:** Убедитесь, что применён действительный файл лицензии; иначе библиотека работает в режиме оценки с ограничениями.

## Часто задаваемые вопросы

### Подходит ли Aspose.Zip for .NET для больших каталогов?
Да, Aspose.Zip for .NET разработан для эффективной работы с большими каталогами, обеспечивая оптимальную производительность.

### Можно ли изменить пароль уже защищённого каталога?
Да, вы можете изменить пароль, скорректировав `TraditionalEncryptionSettings` в коде соответствующим образом.

### Есть ли требования к лицензированию при использовании Aspose.Zip for .NET?
Да, для использования Aspose.Zip for .NET в производственной среде требуется действующая лицензия. Вы можете получить лицензию **[здесь](https://purchase.aspose.com/buy)**.

### Доступна ли бесплатная пробная версия Aspose.Zip for .NET?
Да, бесплатную пробную версию можно получить **[здесь](https://releases.aspose.com/)**.

### Где можно найти дополнительную поддержку Aspose.Zip for .NET?
Вы можете посетить **[форум Aspose.Zip](https://forum.aspose.com/c/zip/37)** для получения поддержки или вопросов.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Zip for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}