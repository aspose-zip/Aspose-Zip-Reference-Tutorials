---
date: 2026-06-19
description: Узнайте, как добавить несколько файлов в tar и сжать их в tar.gz с использованием
  Aspose.Zip for .NET — быстрый, кросс‑платформенный способ создания архивов TarGz.
keywords:
- add multiple files to tar
- compress files to tar.gz
- Aspose.Zip .NET
- tar archive .NET
- tar.gz creation
linktitle: Добавить файлы в tar
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to add multiple files to tar and compress files to tar.gz
    using Aspose.Zip for .NET – a fast, cross‑platform way to build TarGz archives.
  headline: Add multiple files to tar and create tar.gz archive with Aspose.Zip for
    .NET
  type: TechArticle
- questions:
  - answer: Yes, it works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET
      5–10 projects.
    question: Is Aspose.Zip for .NET compatible with all .NET applications?
  - answer: Visit the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      to request a trial license.
    question: How can I obtain a temporary license for Aspose.Zip for .NET?
  - answer: The library is optimized for large files; there is no hard size limit
      other than the available system memory, and it can stream archives larger than
      100 GB.
    question: Are there any file‑size limitations?
  - answer: Use the community‑driven support forum [here](https://forum.aspose.com/c/zip/37)
      for help from Aspose engineers and other developers.
    question: Where can I get support?
  - answer: Absolutely—download the free trial from the [Aspose Zip releases page](https://releases.aspose.com/zip/net/).
    question: Can I try Aspose.Zip for .NET for free?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Добавить несколько файлов в tar и создать архив tar.gz с помощью Aspose.Zip
  for .NET
url: /ru/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить несколько файлов в tar и создать архив tar.gz с помощью Aspose.Zip для .NET

## Введение

В современных .NET‑приложениях **добавление нескольких файлов в tar** и последующее **сжатие файлов в tar.gz** часто требуется — будь то объединение файлов журналов, подготовка данных для облачного хранилища или создание пакетов развертывания для Linux‑серверов. Aspose.Zip для .NET предоставляет чистый, высокопроизводительный API, позволяющий создавать tar‑архив, добавлять любое количество файлов и при необходимости сжимать его в файл tar.gz — без внешних инструментов. В этом руководстве мы пройдем полный рабочий процесс, от настройки проекта до готового к продакшену `archive.tar.gz`.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.Zip for .NET — поддерживает tar, tar.gz, zip и многие другие форматы.  
- **Как добавить несколько файлов в tar?** Вызовите `TarArchive.CreateEntry` для каждого файла, который нужно включить.  
- **Можно ли сжимать напрямую в tar.gz?** Да — вызовите `SaveGzipped` у экземпляра `TarArchive`.  
- **Нужна ли лицензия для продакшена?** Для использования не в пробном режиме требуется действующая лицензия Aspose.  
- **Какие версии .NET поддерживаются?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10.

## Что означает «добавить несколько файлов в tar»?
Добавление нескольких файлов в tar‑архив означает объединение нескольких файлов (и при желании каталогов) в один несжатый контейнер с сохранением их исходной иерархии и метаданных. Полученный файл `.tar` позже можно сжать с помощью gzip, получив архив `tar.gz`, который широко используется для распространения и резервного копирования.

## Почему стоит использовать Aspose.Zip для сжатия файлов в tar.gz?
Aspose.Zip обрабатывает весь процесс tar и gzip в памяти, устраняя необходимость в нативных утилитах. Он может обрабатывать **архивы до 500 ГБ** без загрузки всего файла в память благодаря потоковой архитектуре. Библиотека поддерживает **более 50 форматов ввода и вывода**, работает на Windows, Linux и macOS и предлагает дополнительные возможности, такие как шифрование, защита паролем и пользовательские атрибуты записей — всё через единый .NET API.

## Требования

- Базовый опыт разработки на .NET.  
- Visual Studio (или любой другой предпочитаемый IDE).  
- Aspose.Zip for .NET установлен — см. официальную документацию [здесь](https://reference.aspose.com/zip/net/).  
- Библиотека Aspose.Zip загружена по [этой ссылке](https://releases.aspose.com/zip/net/).

## Импорт пространств имён

В вашем .NET‑проекте импортируйте пространства имён, которые предоставляют классы, связанные с tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Как добавить несколько файлов в tar с помощью Aspose.Zip для .NET

С помощью Aspose.Zip вы сначала загружаете исходную папку, создаёте экземпляр `TarArchive`, затем перебираете каждый файл, вызывая `CreateEntry` для добавления его в архив. После добавления всех записей вызываете `SaveGzipped`, чтобы получить сжатый `archive.tar.gz`. Весь процесс требует всего несколько строк понятного, типобезопасного кода .NET.

### Шаг 1: Установите каталог документов

Определите папку, содержащую файлы, которые нужно заархивировать.

```csharp
string dataDir = "Your Document Directory";
```

> **Совет:** Используйте `Path.Combine` при построении путей, чтобы избежать проблем с разделителями, специфичными для платформы.  
> Метод `Path.Combine` безопасно соединяет имена каталогов и файлов, используя соответствующий разделитель для операционной системы.

### Шаг 2: Создать архив TarGz

Теперь мы создадим tar‑архив, добавим записи и сожмём его в одном последовательном потоке.

#### 2.1 Инициализация TarArchive

Класс `TarArchive` — это объект верхнего уровня Aspose.Zip, представляющий tar‑контейнер в памяти. Его создание подготавливает пустой архив, готовый к добавлению записей.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Добавление файлов — ядро «добавления нескольких файлов в tar»

`CreateEntry` создаёт новую запись внутри tar‑архива. Метод принимает **имя записи** (путь внутри tar) и **путь к исходному файлу** на диске. Вызывайте его многократно, чтобы добавить нужное количество файлов.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Каждый вызов `CreateEntry` добавляет один файл; вы можете перебрать коллекцию файлов в каталоге, чтобы добавить десятки или сотни файлов с минимальным объёмом кода.

#### 2.3 Сохранить как Gzipped Tar (как сжать файлы в tar.gz)

`SaveGzipped` записывает содержимое tar в gzip‑поток, создавая компактный файл `archive.tar.gz`, готовый к распространению или хранению.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

Метод автоматически обрабатывает заголовки и окончания gzip, поэтому вы получаете соответствующий стандартам tar.gz без дополнительных шагов.

## Распространённые сценарии использования

| Сценарий | Почему «добавление нескольких файлов в tar» полезно |
|----------|---------------------------------------------------|
| **Агрегация журналов** | Объединить ежедневные журналы в один архив перед загрузкой в облачное хранилище. |
| **Пакеты развертывания** | Создать переносимые tar.gz‑пакеты для Linux‑серверов из конвейера сборки Windows. |
| **Резервное копирование данных** | Сохранить иерархию папок и метаданные, одновременно уменьшая размер резервной копии. |

## Распространённые проблемы и решения

- **Ошибка «файл не найден»** — Убедитесь, что `dataDir` заканчивается соответствующим разделителем пути, или используйте `Path.Combine`.  
- **Большие файлы вызывают нагрузку на память** — Используйте перегрузку `CreateEntry` на основе потоков (`CreateEntry(string entryName, Stream source)`), чтобы избежать загрузки целых файлов в память.  
- **Вывод gzip повреждён** — Убедитесь, что `TarArchive` освобождён (через блок `using`) перед вызовом `SaveGzipped`.  

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Zip для .NET со всеми приложениями .NET?**  
A: Да, он работает с .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и проектами .NET 5–10.

**Q: Как получить временную лицензию для Aspose.Zip для .NET?**  
A: Перейдите на страницу [временной лицензии](https://purchase.aspose.com/temporary-license/), чтобы запросить пробную лицензию.

**Q: Есть ли ограничения по размеру файлов?**  
A: Библиотека оптимизирована для больших файлов; жёсткого ограничения размера нет, кроме доступной системной памяти, и она может потоково обрабатывать архивы более 100 ГБ.

**Q: Где можно получить поддержку?**  
A: Используйте поддерживаемый сообществом форум [здесь](https://forum.aspose.com/c/zip/37) для получения помощи от инженеров Aspose и других разработчиков.

**Q: Можно ли бесплатно опробовать Aspose.Zip для .NET?**  
A: Конечно — скачайте бесплатную пробную версию со страницы [релизов Aspose Zip](https://releases.aspose.com/zip/net/).

## Заключение

Теперь вы знаете, как **добавить несколько файлов в tar**, создать tar‑архив и **сжать файлы в tar.gz** с помощью Aspose.Zip для .NET. Этот подход устраняет внешние зависимости, предоставляет полный контроль над содержимым архива и масштабируется до очень больших наборов данных. Исследуйте дополнительные возможности, такие как шифрование, пользовательские атрибуты записей и потоковые API, чтобы ещё больше улучшить ваш процесс архивирования.

---

**Последнее обновление:** 2026-06-19  
**Тестировано с:** Aspose.Zip 24.11 for .NET  
**Автор:** Aspose

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как сжать несколько файлов tar с помощью Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [Добавить файлы в tar и создать архив tarxz с помощью Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Как сжать tar и создать TarBz2 с помощью Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}