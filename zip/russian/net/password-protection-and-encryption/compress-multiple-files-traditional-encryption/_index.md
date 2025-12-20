---
date: 2025-12-20
description: Узнайте, как защитить ZIP‑архив паролем с помощью Aspose.Zip для .NET,
  используя традиционное шифрование. Это руководство показывает, как шифровать ZIP‑файлы
  и эффективно добавлять файлы в архив.
linktitle: Compress Multiple Files with Traditional Encryption
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Защита ZIP‑архива паролем с Aspose.Zip .NET
url: /ru/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Защита zip‑архива паролем с помощью Aspose.Zip .NET

## Введение

Добро пожаловать в этот пошаговый учебник о **том, как защитить zip‑архив паролем** с использованием традиционного шифрования Aspose.Zip для .NET. Aspose.Zip — мощная библиотека, позволяющая разработчикам легко создавать, читать и управлять zip‑архивами. В этом руководстве мы покажем, как сжать несколько файлов, добавить их в zip и защитить архив паролем — при этом код останется чистым и поддерживаемым.

## Быстрые ответы
- **Что означает “password protect zip archive”?** Это шифрование zip‑файла, при котором его содержимое можно открыть только после ввода правильного пароля.  
- **Какая библиотека обеспечивает эту возможность в .NET?** Aspose.Zip for .NET предоставляет встроенную поддержку традиционного шифрования.  
- **Нужна ли лицензия для продакшна?** Да, для использования в продакшн‑среде требуется коммерческая лицензия; доступна бесплатная пробная версия.  
- **Можно ли запускать это на Linux?** Конечно — Aspose.Zip кроссплатформенный и работает на Windows, Linux и macOS.  
- **Сколько файлов можно добавить?** Можно добавить любое количество файлов; в примере показаны три, но подход масштабируется.

## Что такое “password protect zip archive”?

Zip‑архив, защищённый паролем, использует шифрование (в данном случае традиционное PKZIP‑шифрование) для запутывания данных файлов внутри архива. При попытке извлечения архива пользователь должен ввести правильный пароль для расшифровки содержимого.

## Почему использовать Aspose.Zip для этой задачи?

- **Simple API** – Одна строка кода для включения шифрования.  
- **No external dependencies** – Чистый .NET, без нативных DLL.  
- **Cross‑platform** – Работает с .NET Framework, .NET Core и .NET 5/6+.  
- **Performance‑optimized** – Эффективно обрабатывает большие файлы.

## Необходимые условия

- **Aspose.Zip for .NET** – Скачайте её с официального сайта [здесь](https://releases.aspose.com/zip/net/).  
- **Папка с файлами** – Замените `"Your Document Directory"` в примере кода реальным путём к директории, содержащей файлы, которые нужно заархивировать.

## Импорт пространств имён

Начните с импорта необходимых пространств имён, чтобы работать с классами Aspose.Zip:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Как зашифровать zip с помощью традиционного шифрования

### Шаг 1: Настройка zip‑файла (Защита zip‑архива паролем)

Создайте zip‑файл и сконфигурируйте параметры традиционного шифрования. Пароль `"p@s$"` приведён лишь как пример — замените его на надёжный пароль для реальных проектов.

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Create archive with traditional encryption settings
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Continue to the next step...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

### Добавление файлов в zip‑архив

Теперь добавьте каждый файл, который хотите включить. Метод `CreateEntry` принимает имя файла внутри zip и поток (`source1`, `source2`, `source3`), указывающий на реальные данные файла.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

### Сохранение zip‑файла (сжатие файлов с паролем)

Наконец, сохраните архив на диск. Этот шаг записывает зашифрованный zip‑файл в указанное ранее место.

```csharp
archive.Save(zipFile);
```

> **Pro tip:** Всегда закрывайте потоки (операторы `using`), чтобы быстро освобождать файловые дескрипторы, особенно при работе с большими файлами.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **Incorrect password error** | Несоответствие пароля или опечатка в `TraditionalEncryptionSettings` | Проверьте строку пароля и убедитесь, что тот же пароль используется при извлечении. |
| **File not added** | Поток источника (`sourceX`) равен null или уже закрыт | Откройте потоки источника с помощью `File.OpenRead` перед передачей их в `CreateEntry`. |
| **Performance slowdown on large files** | Используется уровень сжатия по умолчанию при большом количестве крупных записей | Рассмотрите возможность установки `CompressionLevel` в `ArchiveEntrySettings` для ускорения обработки. |

## Часто задаваемые вопросы

**Q: Можно ли использовать это как в Windows, так и в Linux?**  
A: Да, Aspose.Zip for .NET полностью кроссплатформенный и работает на Windows, Linux и macOS.

**Q: Доступна ли бесплатная пробная версия?**  
A: Конечно — вы можете попробовать бесплатную версию Aspose.Zip for .NET [здесь](https://releases.aspose.com/).

**Q: Где получить поддержку при возникновении проблем?**  
A: Посетите официальный [форум Aspose.Zip](https://forum.aspose.com/c/zip/37) для получения помощи от сообщества и официальной поддержки.

**Q: Есть ли временные лицензии для оценки?**  
A: Да, временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Где находится полная документация API?**  
A: Подробные справочные материалы доступны [здесь](https://reference.aspose.com/zip/net/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}