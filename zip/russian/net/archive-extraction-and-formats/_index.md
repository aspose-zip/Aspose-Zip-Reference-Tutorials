---
date: 2026-06-19
description: Узнайте, как сжимать tar‑файлы, создавать архивы targz и извлекать zip‑файлы,
  защищённые паролем, с помощью Aspose.Zip for .NET — повышая эффективность хранения
  и безопасность.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Извлечение архивов и форматы
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как сжимать tar‑файлы с помощью Aspose.Zip for .NET
url: /ru/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сжимать tar‑файлы с помощью Aspose.Zip для .NET

## Введение

В этом руководстве вы узнаете **как сжимать tar** файлы с помощью Aspose.Zip для .NET, научитесь создавать архивы TarGz и увидите, как извлекать zip‑архивы, защищённые паролем. Эффективная работа с архивами — ключевой навык современного .NET‑разработчика: будь то сервис резервного копирования, клиент облачного хранилища или конвейер обработки данных, владение этими форматами снижает затраты на хранение, ускоряет передачу и защищает конфиденциальные данные.

## Быстрые ответы
- **Что такое TarBz2?** Сжатый архив, который сочетает упаковку TAR с компрессией BZIP2 для высокого коэффициента сжатия.  
- **Почему выбрать Aspose.Zip для .NET?** Он предоставляет единый, удобный API для создания и извлечения множества форматов архивов без внешних зависимостей.  
- **Могу ли я создать архив TarGz?** Да — Aspose.Zip поддерживает TarGz, TarLz, TarXz, TarZ и другие.  
- **Как извлечь zip‑архив, защищённый паролем?** Используйте свойство `Password` объекта `ArchiveEntry` при извлечении.  
- **Нужна ли лицензия для использования в продакшене?** Для продакшена требуется коммерческая лицензия; доступна бесплатная пробная версия для оценки.

## Что такое сжатие Tar?
Tar (Tape Archive) — это контейнерный формат, который объединяет несколько файлов и каталогов в один поток без сжатия. Когда вы применяете алгоритм сжатия, такой как BZIP2, GZip, LZMA или XZ, результатом становится **tar‑based archive** вроде `.tar.bz2`, `.tar.gz`, `.tar.lz` и т.д. Эти форматы широко поддерживаются в Linux, macOS и Windows, что делает их идеальными для кросс‑платформенного обмена данными.

## Почему использовать Aspose.Zip для .NET для работы с этими форматами?
Aspose.Zip предоставляет **unified, dependency‑free API**, поддерживающий более 50 форматов архивов и сжатия, включая TarBz2, TarGz, TarLz, TarXz и TarZ. Он работает на Windows, Linux и macOS, а его потоковая архитектура удерживает использование памяти ниже 10 МБ даже для архивов размером в несколько сотен мегабайт. Защита паролем встроена, позволяя шифровать отдельные записи без дополнительных библиотек.

## Предварительные требования
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 или .NET 5–10.  
- NuGet‑пакет Aspose.Zip for .NET установлен (`Install-Package Aspose.Zip`).  
- Базовые знания работы с файловой системой C# и системой проектов .NET.

## Пошаговое руководство

### Как сжимать tar‑файлы — прямой ответ
`Archive` представляет файл архива и предоставляет методы для добавления записей и сохранения.  
Создайте экземпляр `Archive`, добавьте нужные файлы, установите `CompressionType.BZip2` и вызовите `Save` с `ArchiveFormat.TarBz2`. Библиотека записывает контейнер TAR и сжимает его за один проход, поэтому вам не придётся загружать весь архив в память.

### Шаг 1: Выберите нужный формат архива
Определите, какой tar‑based формат лучше всего соответствует вашему компромиссу между скоростью и степенью сжатия:

- **TarBz2** – Наивысшее соотношение сжатия (≈30 % меньше, чем TarGz), но медленнее.  
- **TarGz** – Хороший баланс скорости и размера; идеален для большинства сценариев облачного хранилища.  
- **TarLz / TarXz** – Очень высокое сжатие при умеренной скорости, полезно для архивного хранения.  
- **TarZ** – Устаревший формат для совместимости со старыми Unix‑утилитами.

### Шаг 2: Создайте новый экземпляр `Archive`
`Archive` — объект верхнего уровня, представляющий один архивный файл в памяти.  

Класс `Archive` управляет процессом упаковки и сжатия, предоставляя методы для добавления записей и записи окончательного файла.

### Шаг 3: Добавьте файлы и папки
Вы можете добавить целое дерево каталогов с помощью `AddAll` или добавить отдельные файлы с `AddFile`. Сохранение исходной иерархии папок так же просто, как передать путь к базовому каталогу.

### Шаг 4: Установите нужный тип сжатия
`CompressionType` перечисляет поддерживаемые алгоритмы.  

`CompressionType` определяет алгоритм (BZip2, GZip, LZMA, XZ и т.д.), который будет применён к потоку TAR во время сохранения.

### Шаг 5: Сохраните архив
`ArchiveFormat` — набор перечислений (например, `TarBz2`, `TarGz`), указывающих писателю, какой контейнер и сжатие использовать.  

Вызов `Save` записывает архив на диск в выбранном формате.

### Шаг 6: Извлечение архивов с паролями
`ArchiveEntry` представляет отдельный файл или каталог внутри архива.  

Чтобы извлечь zip, защищённый паролем, откройте архив, найдите каждую `ArchiveEntry`, задайте её свойство `Password` и вызовите `Extract`. Такая модель пароля для каждой записи позволяет защищать отдельные файлы внутри одного zip‑файла.

### Шаг 7: Проверьте результат
После извлечения сравните размеры файлов и контрольные суммы SHA‑256, чтобы убедиться, что процесс архивирования‑разархивирования сохранил целостность данных.

## Распространённые сценарии использования
- **Backup utilities** – Храните ежедневные резервные копии в формате `.tar.bz2`, сокращая затраты на хранение до 30 %.  
- **Cross‑platform data exchange** – Tar‑based форматы нативно поддерживаются инструментами Linux, macOS и Windows.  
- **Secure distribution** – Присваивайте пароли чувствительным записям, удовлетворяя требования комплаенса без дополнительных средств шифрования.

## Устранение неполадок и советы
- **Large archives** – Предпочтительно использовать потоковый API (`Archive.CreateEntryFromFile`), чтобы снизить использование памяти.  
- **Password mismatches** – Пароль, установленный для каждой `ArchiveEntry`, должен точно совпадать; иначе будет выброшено `InvalidPasswordException`.  
- **Compression level** – BZIP2 не предоставляет пользовательских уровней; если требуется более тонкая настройка, переключитесь на LZMA (`CompressionType.LZMA`) или XZ (`CompressionType.XZ`).  

## Часто задаваемые вопросы

**Q: Как создать архив TarGz?**  
A: Установите `CompressionType.GZip` и используйте `ArchiveFormat.TarGz` при вызове `Save`. Это создаст файл `.tar.gz` за один шаг.

**Q: Можно ли извлечь архив, защищённый паролем, не зная пароля?**  
A: Нет. Для каждой записи необходимо предоставить правильный пароль; в противном случае извлечение завершится с `InvalidPasswordException`.

**Q: Поддерживает ли Aspose.Zip извлечение архивов с разными паролями для каждой записи?**  
A: Да. Задайте пароль каждому `ArchiveEntry` отдельно перед вызовом `Extract`.

**Q: Какой формат обеспечивает лучшее сжатие?**  
A: Обычно TarBz2 даёт наименьший размер, затем следуют TarLz и TarXz. TarGz предлагает более быстрый, но всё‑ещё эффективный вариант.

**Q: Есть ли ограничение на количество файлов, которые можно добавить в TAR‑архив?**  
A: Практически нет, но очень большие архивы (>10 GB) могут выиграть от разбивки на несколько частей для более удобного управления.

## Руководства по извлечению архивов и форматам

### [Сжатие файлов в TarBz2 с помощью Aspose.Zip для .NET](./compress-to-tar-bz2/)
Узнайте, как сжимать файлы в формат TarBz2 в .NET с помощью Aspose.Zip. Следуйте нашему пошаговому руководству для эффективного сжатия файлов.  

### [Сжатие в TarGz с помощью Aspose.Zip для .NET](./compress-to-tar-gz/)
Исследуйте эффективное сжатие файлов в .NET с Aspose.Zip. Сжимайте в TarGz без усилий.  

### [Сжатие в TarLz с помощью Aspose.Zip для .NET](./compress-to-tar-lz/)
Легко сжимайте файлы в .NET с Aspose.Zip. Узнайте, как создавать архивы TarLz шаг за шагом.  

### [Сжатие в TarXz с помощью Aspose.Zip для .NET](./compress-to-tar-xz/)
Узнайте, как сжимать файлы в формат TarXz в .NET с помощью Aspose.Zip. Следуйте нашему руководству для эффективного хранения и передачи.  

### [Сжатие в TarZ с помощью Aspose.Zip для .NET](./compress-to-tar-z/)
Исследуйте пошаговое сжатие в TarZ с использованием Aspose.Zip для .NET. Эффективная работа с файлами для ваших .NET‑проекта.  

### [Извлечение записей архива с разными паролями в Aspose.Zip для .NET](./extract-archive-different-passwords/)
Узнайте, как извлекать записи архива с разными паролями в Aspose.Zip для .NET. Повышайте безопасность и гибкость ваших приложений.

---

**Последнее обновление:** 2026-06-19  
**Тестировано с:** Aspose.Zip for .NET 24.11  
**Автор:** Aspose

## Связанные руководства

- [Создать tar‑архив и добавить файлы в tar с помощью Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Как сжать tar и создать TarBz2 с помощью Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Добавить файлы в tar и создать архив tarxz с помощью Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}