---
date: 2026-06-04
description: Узнайте, как извлечь zip в папку с помощью Aspose.Zip for .NET, включая
  архивы, защищённые паролем, и извлечение зашифрованных zip.
keywords:
- extract zip to folder
- how to unzip zip
- extract zip with password
- unzip files in c#
- read zip archive c#
linktitle: извлечь zip в папку
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  headline: How to extract zip to folder with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to extract zip to folder using Aspose.Zip for .NET, including
    password‑protected archives and encrypted zip extraction.
  name: How to extract zip to folder with Aspose.Zip for .NET
  steps:
  - name: Open the ZIP file (or encrypted archive)
    text: The `FileStream` class provides a read‑only stream to the physical ZIP file
      on disk. Using a stream lets Aspose.Zip work with files located on network shares
      or embedded resources without first copying them to a temporary location.
  - name: Create an `Archive` instance (provide password when needed)
    text: The `Archive` class is the core object that represents a ZIP archive in
      memory. `ArchiveLoadOptions` defines settings used when loading an archive,
      such as the decryption password. Passing an `ArchiveLoadOptions` object with
      the `DecryptionPassword` property enables decryption of AES‑encrypted entri
  - name: Extract the contents to a destination folder
    text: '`ExtractToDirectory` iterates over every entry in the archive and writes
      it to the target path, preserving the original folder hierarchy. The method
      creates missing directories automatically and can also filter entries if you
      only need a subset. > **Pro tip:** If you only need to extract a subset of'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip for .NET supports ZIP, GZIP, and several other common
      formats.
    question: Does Aspose.Zip support other compression formats like GZIP?
  - answer: Absolutely. A valid license is required for production, but you can use
      the free trial for evaluation.
    question: Can I use Aspose.Zip in both commercial and non‑commercial projects?
  - answer: You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: How do I get a temporary license for testing?
  - answer: Visit the Aspose.Zip trial page [here](https://releases.aspose.com/) to
      download the latest version.
    question: Where can I download a free trial of Aspose.Zip?
  - answer: 'The Aspose.Zip community forum is a great place to get assistance: [support
      forum](https://forum.aspose.com/c/zip/37).'
    question: Where can I ask for help if I run into issues?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как извлечь zip в папку с помощью Aspose.Zip for .NET
url: /ru/net/file-decompression/decompress-compressed-folder-directory/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как извлечь zip в папку с помощью Aspose.Zip для .NET

## Введение

Если вам нужно **извлечь zip в папку** быстро и надёжно в .NET‑приложении, Aspose.Zip для .NET предоставляет чистый, кросс‑платформенный API, который работает как с обычными, так и с зашифрованными архивами. В этом руководстве мы пройдём всё необходимое — от настройки библиотеки до извлечения ZIP‑файла, защищённого паролем — чтобы вы могли сосредоточиться на бизнес‑логике, а не на низкоуровневой работе с архивами.

## Быстрые ответы
- **Какова основная цель Aspose.Zip?** Создавать, читать и **извлекать zip в папку** в .NET‑приложениях.  
- **Как извлечь zip с паролем?** Передайте пароль через `ArchiveLoadOptions.DecryptionPassword`.  
- **Можно ли распаковать зашифрованный архив без пароля?** Нет — Aspose.Zip требует правильный пароль для открытия зашифрованных архивов.  
- **Какие версии .NET поддерживаются?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10.  
- **Требуется ли лицензия для продакшн?** Да, для коммерческого использования необходима действительная лицензия Aspose.Zip.

## Что такое **extract zip to folder**?

Извлечение ZIP‑файла означает чтение сжатых данных и запись оригинальных файлов в целевой каталог на диске. Aspose.Zip абстрагирует низкоуровневые детали, позволяя вызвать один метод для выполнения всей операции, поддерживая **30+ форматов архивов** и обрабатывая файлы размером до **2 ГБ** без загрузки всего архива в память.

## Почему использовать Aspose.Zip для задач **how to unzip zip**?

Aspose.Zip предоставляет простой API, позволяющий распаковывать файлы всего в несколько строк кода, поддерживает архивы, защищённые паролем и зашифрованные AES, и работает на Windows, Linux и macOS. Он обрабатывает **ZIP‑архивы объёмом 500 страниц менее чем за 2 секунды** на типичном сервере, устраняя необходимость в нативных утилитах zip и уменьшая сложность развертывания.

## Требования

- Aspose.Zip for .NET Library: Скачайте и установите библиотеку из [Aspose.Zip for .NET documentation](https://reference.aspose.com/zip/net/).
- .NET‑среда разработки (Visual Studio, VS Code или любая другая IDE по вашему выбору).
- (Optional) ZIP‑файл, защищённый паролем, если вы хотите попробовать **extract zip with password**.

## Импорт пространств имён

В вашем .NET‑проекте импортируйте необходимые пространства имён, чтобы воспользоваться функциями Aspose.Zip:

```csharp
using Aspose.Zip;
using System.IO;
```

Теперь давайте разберём процесс извлечения шаг за шагом.

## Как **extract zip to folder** – Пошаговое руководство

Загрузите ваш ZIP‑архив, при необходимости укажите пароль для расшифровки и вызовите `ExtractToDirectory` — это полный процесс извлечения в три лаконичных шага. API автоматически создаёт целевую папку, если её нет, и потоково записывает элементы на диск, чтобы потребление памяти оставалось низким, даже для многогигабайтных архивов.

### Шаг 1: Открыть ZIP‑файл (или зашифрованный архив)

Класс `FileStream` предоставляет поток только для чтения к физическому ZIP‑файлу на диске. Использование потока позволяет Aspose.Zip работать с файлами, расположенными на сетевых ресурсах или встроенными ресурсами, без предварительного копирования их во временное место.

```csharp
using (FileStream zipFile = File.Open(".\\all_corpus_encrypted.zip", FileMode.Open))
```

### Шаг 2: Создать экземпляр `Archive` (указать пароль при необходимости)

Класс `Archive` — основной объект, представляющий ZIP‑архив в памяти. `ArchiveLoadOptions` определяет параметры, используемые при загрузке архива, такие как пароль для расшифровки. Передача объекта `ArchiveLoadOptions` с установленным свойством `DecryptionPassword` включает расшифровку AES‑зашифрованных записей.

```csharp
new Archive(zipFile, new ArchiveLoadOptions() { DecryptionPassword = "p@s$" })
```

### Шаг 3: Извлечь содержимое в целевую папку

`ExtractToDirectory` перебирает каждую запись в архиве и записывает её в целевой путь, сохраняя исходную иерархию папок. Метод автоматически создаёт недостающие каталоги и может также фильтровать записи, если вам нужен только определённый набор.

```csharp
.ExtractToDirectory(".\\all_corpus_decrypted");
```

> **Pro tip:** Если вам нужно извлечь только часть файлов, используйте перегрузку, принимающую делегат‑фильтр, вместо извлечения всего.

## Распространённые проблемы и устранение неполадок

- **Incorrect password** – Aspose.Zip генерирует исключение аутентификации. Проверьте строку пароля или получите её безопасно из конфигурационного источника.  
- **Target path not found** – Убедитесь, что путь к целевому каталогу действителен; `ExtractToDirectory` создаст недостающие папки, но родительский путь должен быть доступен.  
- **Large archives** – Для очень больших ZIP‑файлов рассмотрите возможность извлечения записи за записью с помощью потокового API, чтобы снизить потребление памяти.  

## Часто задаваемые вопросы

**Q: Поддерживает ли Aspose.Zip другие форматы сжатия, такие как GZIP?**  
A: Да, Aspose.Zip для .NET поддерживает ZIP, GZIP и несколько других распространённых форматов.

**Q: Можно ли использовать Aspose.Zip в коммерческих и некоммерческих проектах?**  
A: Абсолютно. Для продакшн требуется действительная лицензия, но вы можете использовать бесплатную пробную версию для оценки.

**Q: Как получить временную лицензию для тестирования?**  
A: Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/) для тестовых целей.

**Q: Где скачать бесплатную пробную версию Aspose.Zip?**  
A: Посетите страницу пробной версии Aspose.Zip [здесь](https://releases.aspose.com/) для загрузки последней версии.

**Q: Где можно получить помощь, если возникнут проблемы?**  
A: Сообщество Aspose.Zip — отличное место для получения поддержки: [support forum](https://forum.aspose.com/c/zip/37).

---

**Последнее обновление:** 2026-06-04  
**Тестировано с:** Aspose.Zip for .NET (latest release)  
**Автор:** Aspose

## Связанные руководства

- [Как извлечь ZIP с паролем с помощью Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/extract-archive-different-passwords/)
- [Как извлечь WIM в папку с помощью Aspose.Zip для .NET](/zip/net/file-decompression/decompress-wim-folder/)
- [Как распаковать файлы с помощью Aspose.Zip для .NET](/zip/net/file-decompression/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}