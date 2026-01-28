---
date: 2026-01-28
description: Узнайте, как создать архив tar.gz, добавить файлы в tar и сжать их с
  помощью Aspose.Zip для .NET — быстрый и надёжный способ архивировать файлы.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создать архив tar.gz и добавить файлы в tar с помощью Aspose.Zip для .NET
url: /ru/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление файлов в tar и создание TarGz с помощью Aspose.Zip для .NET

## Введение

В современных приложениях .NET быстрое и надёжное **add files to tar** является распространённой задачей — будь то упаковка журналов, подготовка данных для облачного хранилища или создание пакетов развертывания. Aspose.Zip для .NET предоставляет чистый, высокопроизводительный API для **add files to tar**, а затем сжатия архива в широко используемый формат **tar.gz**. В этом руководстве вы узнаете, как **create tar.gz archive** с нуля, шаг за шагом, используя библиотеку Aspose.Zip для .NET.

## Быстрые ответы
- **Какую библиотеку следует использовать?** Aspose.Zip for .NET  
- **Как добавить файлы в tar?** Use `TarArchive.CreateEntry` for each file.  
- **Можно ли сжимать напрямую в tar.gz?** Yes—call `SaveGzipped`.  
- **Нужна ли лицензия для продакшн?** A valid Aspose license is required for non‑trial use.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое “add files to tar”?
Добавление файлов в tar‑архив означает объединение нескольких файлов в один не сжатый контейнер. Формат tar сохраняет структуру каталогов и метаданные файлов, что делает его идеальным для архивирования перед необязательным сжатием (например, gzip) для **create tar.gz archive**.

## Почему использовать Aspose.Zip для сжатия файлов в tar.gz?
- **No external tools** – всё работает внутри вашего кода .NET.  
- **High performance** – потоковый API эффективно обрабатывает большие файлы.  
- **Cross‑platform** – работает на Windows, Linux и macOS.  
- **Rich feature set** – поддерживает шифрование, защиту паролем и пользовательские атрибуты записей.  

## Предварительные требования

Before you start, make sure you have:

- Базовый опыт разработки на .NET.  
- Visual Studio (или любой другой предпочтительный IDE).  
- Aspose.Zip для .NET установлен – см. официальную документацию [здесь](https://reference.aspose.com/zip/net/).  
- Библиотека Aspose.Zip загружена по [этой ссылке](https://releases.aspose.com/zip/net/).

## Импорт пространств имён

In your .NET project, import the namespaces that expose the tar‑related classes:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Как создать tar.gz архив с помощью Aspose.Zip для .NET

### Шаг 1: Установите каталог документов

First, point the code to the folder that contains the files you want to archive.

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** При построении путей используйте `Path.Combine`, чтобы избежать проблем с разделителями, специфичными для платформы.

### Шаг 2: Инициализируйте TarArchive

Create a `TarArchive` instance that will hold the entries.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

### Шаг 3: Добавьте файлы – ядро “add files to tar”

Inside the `using` block, add each file you want to include in the archive.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Each `CreateEntry` call takes the **entry name** (how the file will appear inside the tar) and the **source file path** on disk.

### Шаг 4: Сохраните как Gzipped Tar (как compress files to tar.gz)

Finally, write the tar contents to a gzip stream to produce a compact `archive.tar.gz`.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` обрабатывает как упаковку tar, так и сжатие gzip в одном цепочечном вызове.

## Распространённые сценарии использования

| Сценарий | Почему “add files to tar” помогает |
|----------|------------------------------------|
| **Агрегация журналов** | Соберите ежедневные журналы в один архив перед загрузкой в облачное хранилище. |
| **Пакеты развертывания** | Создайте переносимые tar.gz пакеты для Linux‑серверов из конвейера сборки Windows. |
| **Резервное копирование данных** | Сохраните иерархию папок и метаданные, одновременно уменьшая размер резервной копии. |

## Распространённые проблемы и решения

- **File not found error** – Убедитесь, что `dataDir` заканчивается правильным разделителем пути, или используйте `Path.Combine`.  
- **Large files cause memory pressure** – Используйте перегрузки на основе потоков (`CreateEntry` с `Stream`), чтобы избежать загрузки целых файлов в память.  
- **Gzip output is corrupted** – Убедитесь, что архив закрыт (`using` блок) перед вызовом `SaveGzipped`.  

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Zip для .NET со всеми приложениями .NET?**  
A: Да, он работает с проектами .NET Framework, .NET Core и .NET 5/6/7.

**Q: Как я могу получить временную лицензию для Aspose.Zip для .NET?**  
A: Перейдите на страницу [temporary‑license page](https://purchase.aspose.com/temporary-license/), чтобы запросить пробную лицензию.

**Q: Существуют ли ограничения по размеру файлов?**  
A: Библиотека оптимизирована для больших файлов; жесткого ограничения размера нет, кроме доступной памяти системы.

**Q: Где я могу получить поддержку?**  
A: Используйте сообщество‑ориентированный форум поддержки [здесь](https://forum.aspose.com/c/zip/37) для получения помощи от инженеров Aspose и других разработчиков.

**Q: Могу ли я бесплатно опробовать Aspose.Zip для .NET?**  
A: Конечно — скачайте бесплатную пробную версию со страницы [Aspose Zip releases page](https://releases.aspose.com/zip/net).

## Заключение

Теперь вы узнали **how to add files to tar**, создали tar‑архив и сжали его в **tar.gz** с помощью Aspose.Zip для .NET. Этот подход устраняет внешние зависимости, предоставляет тонкий контроль над содержимым архива и масштабируется для больших наборов данных. Не стесняйтесь изучать дополнительные возможности Aspose.Zip, такие как шифрование, пользовательские атрибуты записей и потоковые API, чтобы еще больше улучшить ваш процесс архивирования.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-01-28  
**Тестировано с:** Aspose.Zip 24.11 for .NET  
**Автор:** Aspose