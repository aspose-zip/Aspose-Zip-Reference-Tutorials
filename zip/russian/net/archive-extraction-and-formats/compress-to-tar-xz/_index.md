---
date: 2026-11-18
description: Узнайте, как добавить файлы в tar и сжать их в архив tarxz в .NET с использованием
  Aspose.Zip. Следуйте пошаговому руководству для эффективного хранения и передачи.
images:
- /net/archive-extraction-and-formats/compress-to-tar-xz/og-image.png
keywords:
- add files to tar
- compress tar with xz
- create tarxz archive
- compress files to tarxz
- generate tarxz file
lastmod: 2026-11-18
linktitle: Сжатие в TarXz
og_description: Добавление файлов в tar и создание архива tarxz с помощью Aspose.Zip.
  Узнайте, как быстро сжать файлы в TarXz в .NET, обеспечивая высокую эффективность
  сжатия и кроссплатформенную совместимость.
og_image_alt: 'Developer guide: Add files to tar and create tarxz archive using Aspose.Zip
  .NET'
og_title: Добавление файлов в tar и создание архива tarxz с помощью Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  headline: Add files to tar and create tarxz archive with Aspose.Zip
  type: TechArticle
- description: Learn how to add files to tar and compress files to tarxz archive .NET
    using Aspose.Zip. Follow this step‑by‑step guide for efficient storage and transmission.
  name: Add files to tar and create tarxz archive with Aspose.Zip
  steps:
  - name: Initialize a `TarArchive`
    text: '`TarArchive` is the top‑level object that represents a tar container in
      Aspose.Zip. It manages entries and provides methods for saving the archive.
      > **Pro tip:** The `using` statement ensures the archive is properly disposed,
      releasing any unmanaged resources.'
  - name: Add Files to the Archive
    text: Add each file you wish to include. In this example we add two text files,
      but you can add as many entries as needed. > **Why this matters:** Adding entries
      before compression lets Aspose.Zip build the tar container first, then apply
      XZ compression in a single step.
  - name: Save the Archive with XZ Compression
    text: '`SaveXzCompressed` writes the tar archive to disk while applying XZ compression,
      producing a `.tar.xz` file in one operation. > **Result:** You now have a fully‑compressed
      `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform
      that supports TarXz.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Zip works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1,
      and .NET 5–10. See the [documentation](https://reference.aspose.com/zip/net/)
      for details.
    question: Is Aspose.Zip compatible with all .NET environments?
  - answer: You can request a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Zip?
  - answer: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).
    question: Are there additional examples for other archive formats?
  - answer: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)
      for community support and official answers.
    question: Where can I get help or discuss issues?
  - answer: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).
    question: Can I try Aspose.Zip for free before buying?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- tar archive
- tarxz
title: Добавление файлов в tar и создание архива tarxz с помощью Aspose.Zip
url: /ru/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить файлы в tar и создать архив tarxz с помощью Aspose.Zip

## Введение

Если вам нужно **add files to tar** и затем **create a tarxz archive .net**, Aspose.Zip for .NET делает процесс простым и надёжным. Независимо от того, упаковываете ли вы журналы, файлы конфигурации или любые другие ресурсы для хранения или передачи, сжатие в формат TarXz обеспечивает высокий коэффициент сжатия при сохранении привычной структуры tar. В этом руководстве мы пройдём через все шаги — с полными фрагментами кода — чтобы вы могли интегрировать создание tarxz в свои .NET‑приложения с уверенностью. К концу вы поймёте, почему «add files to tar» является первым шагом к компактному кросс‑платформенному пакету.

## Быстрые ответы
- **Какой основной класс?** `TarArchive` from `Aspose.Zip.Tar`
- **Как выполнить сжатие до tarxz?** Call `SaveXzCompressed` after adding entries
- **Какие версии .NET поддерживаются?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10
- **Нужна ли лицензия?** Yes, a valid Aspose.Zip license is required for production use
- **Время реализации?** Roughly 5‑10 minutes for a basic archive

## Что такое архив TarXz?

TarXz‑архив сочетает традиционный Unix‑контейнер `tar` с XZ‑сжатием. Часть tar объединяет несколько файлов в один поток, а XZ обеспечивает сильное, без потерь сжатие. Этот формат популярен для распространения исходного кода, резервных копий и больших наборов данных, поскольку сохраняет структуру каталогов и достигает меньших размеров файлов, чем обычный tar или zip.

## Почему создавать tarxz архив .net с помощью Aspose.Zip?

Создание TarXz‑архива с Aspose.Zip предоставляет быстрое решение в один шаг без внешних инструментов. Файлы становятся на 30‑50 % меньше, чем при gzip, и вы можете работать более чем с 20 форматами архивов напрямую в .NET. Библиотека обрабатывает большие архивы без загрузки всего файла в память, что делает её идеальной для облачных сервисов и CI‑конвейеров. Кроме того, поддерживается более 50 входных и выходных форматов.

## Необходимые условия

- **Aspose.Zip for .NET** установлен (скачайте с официальной [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Папка, содержащая файлы, которые вы хотите заархивировать. В примерах ниже эта папка указана переменной `dataDir`.  
- Действительная лицензия Aspose.Zip (необязательно для оценки, требуется для продакшена).

## Импортировать пространства имён

Для доступа к функционалу TarXz достаточно импортировать соответствующие пространства имён. Дополнительные пакеты не требуются, кроме основной библиотеки Aspose.Zip.

## Как добавить файлы в tar с помощью Aspose.Zip

`TarArchive` — класс, представляющий tar‑контейнер в Aspose.Zip. Вы добавляете файлы в tar‑архив, создавая экземпляр `TarArchive`, а затем вызывая его метод `AddEntry` для каждого файла, указывая путь к источнику и, при желании, имя записи. Архив формирует tar‑контейнер в памяти, готовый к последующему XZ‑сжатию.

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Совет:** Оператор `using` гарантирует правильное освобождение архива, освобождая любые неуправляемые ресурсы.

### Шаг 1: инициализировать `TarArchive`

Создайте объект `TarArchive` внутри блока `using`, чтобы все неуправляемые ресурсы автоматически освобождались после завершения операции.

```csharp
using (TarArchive archive = new TarArchive())
{
```

### Шаг 2: добавить файлы в архив

Добавьте каждый файл, который хотите включить. В этом примере мы добавляем два текстовых файла, но вы можете добавить столько записей, сколько потребуется. Метод `AddEntry` принимает полный путь к файлу и необязательное имя записи, которое будет отображаться внутри tar.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Почему это важно:** Добавление записей до сжатия позволяет Aspose.Zip сначала построить контейнер tar, а затем применить сжатие XZ за один шаг.

### Шаг 3: сохранить архив с сжатием XZ

Метод `SaveXzCompressed` записывает tar‑архив в файл, одновременно применяя XZ‑сжатие, создавая файл `.tar.xz`, готовый к распространению.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Результат:** Теперь у вас есть полностью сжатый файл `archive.tar.xz`, который можно передавать, хранить или распаковывать на любой платформе, поддерживающей TarXz.

## Как сжать tarxz файлы с помощью Aspose.Zip

Сжатие до tarxz в Aspose.Zip — это двухшаговый процесс, упакованный в один вызов метода: сначала **add files to tar**, затем вызывается `SaveXzCompressed`. Это устраняет необходимость во внешних утилитах командной строки и сохраняет весь рабочий процесс внутри вашего .NET‑кода.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **“File not found” exception** | Неправильный путь `dataDir` | Проверьте, что путь к директории заканчивается обратным слешем (`\`) или используйте `Path.Combine`. |
| **Large memory usage** | Очень большие файлы сжимаются в памяти | Используйте `TarArchive` в режиме потоковой передачи (`SaveXzCompressed` перегрузка, принимающая `Stream`). |
| **License not applied** | Отсутствует файл лицензии | Загрузите лицензию при старте приложения: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Zip со всеми средами .NET?**  
**A:** Да, Aspose.Zip работает с .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10. Смотрите [documentation](https://reference.aspose.com/zip/net/) для деталей.

**Q: Как я могу получить временную лицензию для Aspose.Zip?**  
**A:** Вы можете запросить временную лицензию на странице [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**Q: Есть ли дополнительные примеры для других форматов архивов?**  
**A:** Конечно — изучайте полный набор примеров в [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: Где я могу получить помощь или обсудить проблемы?**  
**A:** Присоединяйтесь к обсуждению на [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) для поддержки сообщества и официальных ответов.

**Q: Могу ли я попробовать Aspose.Zip бесплатно перед покупкой?**  
**A:** Да, бесплатная пробная версия доступна на [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## Заключение

Следуя приведённым выше шагам, вы теперь знаете **как добавить файлы в tar** и **сжать tarxz** файлы, а главное — как **создать tarxz архив .net** с помощью Aspose.Zip. Этот подход даёт компактный, переносимый пакет, который легко интегрировать в любой .NET‑рабочий процесс — будь то настольное приложение, веб‑служба или автоматизированный конвейер CI/CD.

---

**Последнее обновление:** 2026-11-18  
**Тестировано с:** Aspose.Zip for .NET 24.11  
**Автор:** Aspose  



## Связанные руководства

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [How to compress tar and create TarBz2 with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [How to compress multiple files tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}