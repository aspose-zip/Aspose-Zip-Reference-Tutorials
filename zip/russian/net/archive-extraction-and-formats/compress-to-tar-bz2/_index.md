---
date: 2026-08-07
description: Узнайте, как добавить файлы в tar и создать архив TarBz2 в .NET с использованием
  Aspose.Zip. Пошаговое руководство показывает создание tar, сжатие Bzip2 и советы
  по лучшим практикам.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Сжатие в TarBz2
og_description: Добавьте файлы в tar и создайте архив TarBz2 в .NET с помощью Aspose.Zip.
  Это руководство охватывает создание tar, сжатие Bzip2 и советы по устранению неполадок.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Добавить файлы в tar и создать архив TarBz2 с помощью Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Добавить файлы в tar и создать архив TarBz2 с помощью Aspose.Zip
url: /ru/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить файлы в tar и создать архив TarBz2 с помощью Aspose.Zip

В этом руководстве вы узнаете **как добавить файлы в tar** архивы и превратить их в компактный **TarBz2** файл с помощью библиотеки **Aspose.Zip** для .NET. Независимо от того, создаёте ли вы утилиту резервного копирования, публикуете пакеты развертывания или вам нужен лёгкий пакет для распространения, нижеописанные шаги проведут вас через добавление файлов в контейнер tar, применение сжатия Bzip2 и создание готового к распространению архива.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.Zip for .NET  
- **Сколько времени занимает реализация?** About 5‑10 minutes  
- **Нужна ли лицензия?** A temporary license is required for production; a free trial is available  
- **Можно ли сжать несколько файлов?** Yes – add as many entries as you like to the tar archive  
- **Совместима ли с .NET 6+?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## Что такое архив TarBz2?

Файл TarBz2 сочетает традиционный контейнер **tar** (который сохраняет структуру каталогов и метаданные файлов) со сжатием **Bzip2**, в результате чего получается сильно сжатый пакет `.tar.bz2`. Этот формат популярен в Unix‑подобных системах, поскольку обеспечивает хороший баланс между коэффициентом сжатия и скоростью распаковки.

## Почему сжимать файлы в TarBz2 с помощью Aspose.Zip?

Aspose.Zip может создать архив TarBz2 всего **за два вызова API**, эффективно работая с потоками. Он поддерживает **более 50 форматов архивов и сжатия**, обрабатывает файлы размером до **2 ГБ**, не загружая весь архив в память, и работает на .NET‑рантаймах Windows, Linux и macOS. Библиотека также предоставляет детальный контроль над именами записей, метками времени и уровнями сжатия, что делает её идеальной как для консольных утилит, так и для веб‑служб.

## Предварительные требования

- **Aspose.Zip for .NET** – загрузите последнюю версию пакета с официального сайта: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – папка, содержащая файлы, которые вы хотите заархивировать. В примерах мы ссылаемся на неё переменной `dataDir`.

> **Pro tip:** Храните исходные файлы в отдельной папке, чтобы избежать случайного включения нежелательных файлов.

## Импортировать пространства имён

Сначала импортируйте необходимые пространства имён, чтобы получить доступ к классам Tar и Bzip2 библиотеки Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Шаг 1: установить каталог документов

Определите путь, указывающий на папку, содержащую файлы, которые вы хотите заархивировать.

```csharp
string dataDir = "Your Document Directory";
```

> Замените `"Your Document Directory"` на абсолютный или относительный путь к вашей исходной папке.

## Шаг 2: добавить файлы в tar и создать архив TarBz2

`TarArchive` представляет собой tar‑контейнер в памяти, способный хранить несколько файловых записей.  
`Bzip2Archive` сжимает поток с помощью алгоритма Bzip2.  
Метод `CreateEntry` добавляет файл в tar‑архив как новую запись.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **добавляет файлы в tar** – you can call this method for every file you need in the archive.  
- `bz2.SetSource(archive)` сообщает архиву Bzip2 сжать весь tar‑поток.  
- `bz2.Save(...)` записывает окончательный **TarBz2** файл на диск.

**Tip:** Чтобы **добавить файлы в tar** массово, просто повторите `archive.CreateEntry` для каждого файла перед вызовом `bz2.Save`.

## Как добавить файлы в tar?

Загрузите исходный каталог, создайте экземпляр `TarArchive`, добавьте каждый файл с помощью `CreateEntry`, затем оберните tar‑поток в `Bzip2Archive` и вызовите `Save`. Этот двухшаговый шаблон позволяет добавить любое количество файлов и создать файл `.tar.bz2` в едином последовательном процессе, устраняя необходимость во временных файлах или внешних инструментах.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| **File not found** ошибка | Неправильный путь `dataDir` или отсутствует расширение файла | Проверьте полный путь и убедитесь, что файл существует. |
| **Empty archive** | Не добавлено записей перед `bz2.Save` | Добавьте хотя бы один вызов `CreateEntry`. |
| **Permission denied** | Приложению не хватает прав записи в папку вывода | Запустите приложение с соответствующими правами или выберите папку с правом записи. |

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Zip со всеми приложениями .NET?**  
A: Да. Он работает с .NET Framework, .NET Core, .NET 5/6 и более новыми рантаймами.

**Q: Можно ли сжимать несколько файлов одновременно?**  
A: Абсолютно. Вызывайте `CreateEntry` для каждого файла перед сохранением архива.

**Q: Где можно найти дополнительную документацию?**  
A: Подробные документы доступны в **Aspose.Zip .NET API reference**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Как получить временную лицензию для Aspose.Zip?**  
A: Вы можете **запросить временную лицензию** здесь: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Доступна ли бесплатная пробная версия?**  
A: Да, **скачайте пробную версию с Aspose releases**: [download a trial version](https://releases.aspose.com/).

## Заключение

Теперь вы знаете **как добавить файлы в tar**, сжать tar‑поток с помощью Bzip2 и создать архив **TarBz2** с использованием Aspose.Zip для .NET. Этот подход быстрый, экономичный по памяти и работает на всех современных платформах .NET. Не стесняйтесь экспериментировать с большими наборами файлов, пользовательскими именами записей или интегрировать код в свои собственные процессы резервного копирования или развертывания.

Если вы столкнётесь с какими‑либо проблемами, сообщество Aspose.Zip готово помочь — просто перейдите на **форум поддержки Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Последнее обновление:** 2026-08-07  
**Тестировано с:** Aspose.Zip for .NET (latest release)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать tar‑архив и добавить файлы в tar с Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Добавить файлы в tar и создать архив tarxz с Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Добавить файлы в tar и сжать в TarZ с Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}