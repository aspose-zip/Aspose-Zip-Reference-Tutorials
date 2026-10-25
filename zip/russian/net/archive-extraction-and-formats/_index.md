---
date: 2026-10-25
description: Узнайте, как извлечь пароль zip и задать алгоритм сжатия при сжатии файлов
  tar с помощью Aspose.Zip для .NET, повышая эффективность хранения и безопасность.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Извлечение архивов и форматы
og_description: Узнайте, как извлечь пароль zip и задать алгоритм сжатия при сжатии
  файлов tar с помощью Aspose.Zip для .NET, повышая эффективность хранения и безопасность.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Извлечение пароля zip и сжатие файлов tar с помощью Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Извлечение пароля zip и сжатие файлов tar с помощью Aspose.Zip
url: /ru/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Извлечение пароля zip и сжатие tar‑файлов с Aspose.Zip

## Введение

В этом руководстве вы узнаете техники **extract zip password**, научитесь задавать алгоритм сжатия при создании архивов на основе tar, а также увидите, как создавать TarGz, TarBz2 и другие форматы с помощью Aspose.Zip для .NET. Независимо от того, разрабатываете ли вы сервис резервного копирования, клиент облачного хранилища или конвейер обработки данных, освоение этих операций снижает затраты на хранение, ускоряет передачу и защищает конфиденциальные файлы.

## Быстрые ответы
- **What is TarBz2?** Сжатый архив, который сочетает упаковку TAR с компрессией BZIP2 для получения высокого коэффициента сжатия.  
- **Why choose Aspose.Zip for .NET?** Поддерживает более 50 форматов архивов и сжатия, работает на Windows, Linux и macOS и удерживает использование памяти ниже 10 МБ даже для архивов размером в несколько сотен мегабайт.  
- **Can I create a TarGz archive?** Да — Aspose.Zip предлагает TarGz, TarLz, TarXz, TarZ и другие форматы.  
- **How do I extract a password‑protected zip archive?** Установите свойство `Password` у каждого `ArchiveEntry` перед вызовом `Extract`.  
- **Do I need a license for production use?** Для производства требуется коммерческая лицензия; бесплатная пробная версия доступна для оценки.

## Что такое сжатие tar?

Сжатие tar сочетает контейнер TAR с алгоритмом сжатия, таким как BZIP2, GZIP, LZMA или XZ. В результате получается один файл (например, `.tar.gz`, `.tar.bz2`), который можно распаковать в Linux, macOS и Windows. Оно сохраняет исходную иерархию каталогов, позволяет выполнять выборочное извлечение и широко поддерживается командными утилитами и библиотеками, что делает его идеальным для кроссплатформенного распространения и архивного хранения.

## Почему использовать Aspose.Zip для .NET для работы с этими форматами?

Aspose.Zip предоставляет единый API без внешних зависимостей, поддерживающий **50+** форматов архивов и сжатия, включая все основные типы tar‑архивов. Его потоковая архитектура обрабатывает архивы более 10 ГБ, удерживая использование ОЗУ ниже 10 МБ, что делает его идеальным для серверных задач с высоким пропускным способностью.  

**Direct answer:** Вы используете Aspose.Zip, потому что он позволяет создавать, сжимать и извлекать tar‑архивы и zip‑файлы, защищённые паролем, с помощью единого плавного API без внешних инструментов, при этом эффективно работает с многогигабайтными архивами в режиме потоковой обработки.

## Требования
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 или .NET 5–10.  
- NuGet‑пакет Aspose.Zip для .NET (`Install-Package Aspose.Zip`).  
- Базовые знания работы с файловой системой C# и системы проектов .NET.

## Пошаговое руководство

### Как сжать tar‑файлы – прямой ответ
Создайте экземпляр `Archive`, добавьте нужные файлы, задайте `CompressionType.BZip2` (или другой алгоритм) и вызовите `Save` с параметром `ArchiveFormat.TarBz2`. Библиотека записывает контейнер TAR и сжимает его в одном потоковом проходе, поэтому вам никогда не придётся загружать весь архив в память.

### Шаг 1: Выберите нужный формат архива
Определите, какой tar‑формат лучше всего соответствует вашему компромиссу между скоростью и степенью сжатия:

- **TarBz2** – Наивысшее соотношение сжатия (≈30 % меньше, чем TarGz), но медленнее.  
- **TarGz** – Хороший баланс скорости и размера; идеален для большинства сценариев облачного хранилища.  
- **TarLz / TarXz** – Очень высокое сжатие при умеренной скорости, полезно для архивного хранения.  
- **TarZ** – Устаревший формат для совместимости со старыми Unix‑утилитами.

### Шаг 2: Создайте новый экземпляр `Archive`
`Archive` представляет один архивный файл и предоставляет методы для добавления записей и сохранения архива.  

Класс `Archive` управляет процессом упаковки и сжатия, предоставляя методы добавления записей и записи окончательного файла.

### Шаг 3: Добавьте файлы и папки
Вы можете добавить целое дерево каталогов с помощью `AddAll` или отдельные файлы с помощью `AddFile`.  

`AddAll` добавляет весь каталог в архив, сохраняя его структуру.  
`AddFile` добавляет один файл в архив. Сохранение исходной иерархии папок происходит просто путем указания базового пути каталога.

### Шаг 4: Установите желаемый тип сжатия
Перечисление `CompressionType` задаёт алгоритм сжатия, применяемый к потоку TAR.  

`CompressionType` перечисляет поддерживаемые алгоритмы (BZip2, GZip, LZMA, XZ и др.), которые будут применены при сохранении.

### Шаг 5: Сохраните архив
Перечисление `ArchiveFormat` выбирает комбинацию контейнера и сжатия для выходного файла.  

Вызов `Save` записывает архив на диск в выбранном формате.

### Шаг 6: Извлечение архивов с паролями
`ArchiveEntry` представляет отдельный файл или каталог внутри архива.  

Чтобы извлечь zip‑архив, защищённый паролем, откройте архив, найдите каждый `ArchiveEntry`, присвойте ему свойство `Password` и вызовите `Extract`. Свойство `Password` задаёт пароль расшифровки для конкретной записи zip. Такая модель паролей на уровне записей позволяет защищать отдельные файлы внутри одного zip‑файла.

### Шаг 7: Проверьте результат
После извлечения сравните размеры файлов и контрольные суммы SHA‑256, чтобы убедиться, что архивный круговой процесс сохранил целостность данных.

## Распространённые сценарии использования
- **Утилиты резервного копирования** – Храните ежедневные резервные копии в формате `.tar.bz2`, экономя до 30 % места.  
- **Кроссплатформенный обмен данными** – Форматы на основе tar нативно поддерживаются инструментами Linux, macOS и Windows.  
- **Безопасное распространение** – Присваивайте пароли чувствительным записям, удовлетворяя требования комплаенса без дополнительных средств шифрования.

## Устранение неполадок и советы
- **Большие архивы** – Используйте потоковый API (`Archive.CreateEntryFromFile`), чтобы держать использование памяти на низком уровне.  
- **Несоответствие паролей** – Пароль, установленный у каждого `ArchiveEntry`, должен точно совпадать; иначе будет выброшено `InvalidPasswordException`.  
- **Уровень сжатия** – BZIP2 не предоставляет пользовательских уровней; если нужен более тонкий контроль, переключитесь на LZMA (`CompressionType.LZMA`) или XZ (`CompressionType.XZ`).  

## Часто задаваемые вопросы

**Q: Как создать архив TarGz?**  
A: Установите `CompressionType.GZip` и используйте `ArchiveFormat.TarGz` при вызове `Save`. Это создаст файл `.tar.gz` за один шаг.

**Q: Можно ли извлечь архив, защищённый паролем, не зная пароля?**  
A: Нет. Для каждой записи необходимо предоставить правильный пароль; иначе извлечение завершится с `InvalidPasswordException`.

**Q: Поддерживает ли Aspose.Zip извлечение архивов с разными паролями для каждой записи?**  
A: Да. Присвойте пароль каждому `ArchiveEntry` отдельно перед вызовом `Extract`.

**Q: Какой формат обеспечивает лучшее сжатие?**  
A: Обычно TarBz2 даёт наименьший размер, затем TarLz и TarXz. TarGz предлагает более быстрый, но всё ещё эффективный вариант.

**Q: Есть ли ограничение на количество файлов, которые можно добавить в TAR‑архив?**  
A: Практически нет, но чрезвычайно большие архивы (>10 GB) могут выиграть от разбивки на несколько частей для более удобного обращения.

## Учебники по извлечению архивов и форматам

### [Сжатие файлов в TarBz2 с Aspose.Zip для .NET](./compress-to-tar-bz2/)
Узнайте, как сжимать файлы в формат TarBz2 в .NET с помощью Aspose.Zip. Следуйте нашему пошаговому руководству для эффективного сжатия файлов.  
### [Сжатие в TarGz с Aspose.Zip для .NET](./compress-to-tar-gz/)
Изучите эффективное сжатие файлов в .NET с Aspose.Zip. Сжимайте в TarGz без усилий.  
### [Сжатие в TarLz с Aspose.Zip для .NET](./compress-to-tar-lz/)
Легко сжимайте файлы в .NET с Aspose.Zip. Узнайте, как создавать архивы TarLz пошагово.  
### [Сжатие в TarXz с Aspose.Zip для .NET](./compress-to-tar-xz/)
Научитесь сжимать файлы в формат TarXz в .NET с помощью Aspose.Zip. Следуйте нашему руководству для эффективного хранения и передачи.  
### [Сжатие в TarZ с Aspose.Zip для .NET](./compress-to-tar-z/)
Изучите пошаговое сжатие в TarZ с использованием Aspose.Zip для .NET. Эффективная работа с файлами для ваших .NET‑проектов.  
### [Извлечение записей архива с разными паролями в Aspose.Zip для .NET](./extract-archive-different-passwords/)
Узнайте, как извлекать записи архива с разными паролями в Aspose.Zip для .NET. Повышайте безопасность и гибкость в своих приложениях.

## Связанные учебники

- [Создание tar‑архива и добавление файлов в tar с Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Как сжать tar и создать TarBz2 с Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Добавление файлов в tar и создание tarxz‑архива с Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Последнее обновление:** 2026-10-25  
**Тестировано с:** Aspose.Zip for .NET 24.11  
**Автор:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}