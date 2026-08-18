---
date: 2026-07-04
description: Узнайте, как сжать несколько файлов tar с использованием Aspose.Zip для
  .NET и эффективно создавать архивы tar.lz.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Сжатие в TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как сжать несколько файлов tar с помощью Aspose.Zip для .NET
url: /ru/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сжать несколько файлов tar с помощью Aspose.Zip для .NET

В современном .NET-разработке эффективное упаковывание файлов может значительно уменьшить размер развертывания и время передачи по сети. **Сжатие нескольких файлов tar** — частое требование, когда нужен легковесный TAR‑архив с LZ‑сжатием для резервных копий, распространения или загрузки в облако. В этом руководстве мы пошагово рассмотрим **пример сжатия tar.lz** с использованием библиотеки Aspose.Zip, чтобы вы могли быстро создать **архив tar.lz** в своих приложениях.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.Zip for .NET.  
- **Сколько времени займет реализация?** Около 5‑10 минут для базового примера.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия требуется для продакшна.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Можно ли сжать несколько файлов одновременно?** Да — просто добавьте больше записей перед сохранением.

## Как сжать несколько файлов tar с помощью Aspose.Zip для .NET?
Загрузите исходные файлы, создайте экземпляр `TarArchive`, добавьте каждый файл с помощью `CreateEntry` и завершите вызовом `SaveLzipped`. Библиотека internally обрабатывает структуру TAR и LZ‑сжатие, поэтому вы получаете один файл `*.tar.lz` всего за несколько строк кода. Такой подход работает в Windows, Linux и macOS без каких‑либо нативных зависимостей.

## Что такое сжатие tar.lz?
`tar.lz` — это TAR‑архив, сжатый с использованием алгоритма LZMA (часто просто называют **LZ**). Он сочетает простоту группировки файлов TAR с высоким коэффициентом сжатия LZ, делая его идеальным для резервных копий, распространения пакетов или любой ситуации, где важна пропускная способность.

## Почему использовать Aspose.Zip для .NET?
Aspose.Zip предоставляет полностью управляемое, кроссплатформенное решение, которое создает TAR, ZIP и LZ‑основанные архивы без внешних инструментов, поддерживает более 30 форматов архивов и обеспечивает до 30 % лучшего сжатия больших файлов, предлагая детальные исключения для надёжной обработки ошибок. Он также бесшовно интегрируется с .NET‑фреймворками логирования и предоставляет подробные события прогресса.

## Предварительные требования
- **Aspose.Zip for .NET** library – скачайте её по ссылке [here](https://releases.aspose.com/zip/net/).  
- Папка, содержащая файлы, которые вы хотите заархивировать. Путь к этой папке будет сохранён в переменной `dataDir` (вы зададите её в Шаге 3).

## Импорт пространств имён
Добавьте необходимые пространства имён, чтобы компилятор знал, где находятся используемые классы.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Как создать архив tar.lz – пошаговое руководство

### Шаг 1: Сжать один файл
Первый пример демонстрирует базовый сценарий — добавление одного файла в TAR‑архив и последующее сохранение его как **tar.lz** файла.

`TarArchive` класс представляет контейнер TAR, который может содержать несколько файлов в одном архиве.  

**Объяснение**

- `new TarArchive()` создаёт пустой контейнер TAR.  
- `CreateEntry` добавляет файл `alice29.txt` из вашего `dataDir`.  
- `SaveLzipped` записывает архив на диск и применяет LZ‑сжатие, создавая `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Шаг 2: Сжать несколько файлов в один архив
Часто требуется собрать несколько файлов вместе. Просто вызовите `CreateEntry` для каждого файла перед сохранением. Это демонстрирует **add files to tar lz** и эффективно **compress multiple files tar**.

**Объяснение**

- Код следует той же схеме, что и в Шаге 1, но добавляет вторую запись (`lcet10.txt`).  
- Вы можете повторять `CreateEntry` столько раз, сколько нужно; библиотека автоматически управляет внутренней структурой TAR.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Шаг 3: Указать каталог документов
Замените заполнитель реальным путём к папке, где находятся ваши исходные файлы. Этот путь используется в примерах выше.

**Объяснение**

- Установите `dataDir` в полностью квалифицированный путь к папке, например, `@\"C:\\MyFiles\\\"`.  
- Хранение пути в переменной делает код переиспользуемым и упрощает поддержку.

```csharp
string dataDir = "Your Document Directory";
```

## Распространённые ошибки и устранение неполадок
| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| `FileNotFoundException` при запуске примера | `dataDir` указывает на несуществующую папку или имя файла написано с ошибкой | Проверьте путь и имена файлов; используйте `Path.Combine` для надёжности. |
| Файл вывода имеет **0 KB** | `archive.SaveLzipped` был вызван до добавления каких‑либо записей | Убедитесь, что хотя бы один вызов `CreateEntry` предшествует `SaveLzipped`. |
| Сжатие кажется медленным | Большие файлы с буфером по умолчанию | Рассмотрите обработку файлов кусками или использование асинхронного ввода‑вывода, если важна производительность. |

## Заключение
Теперь вы знаете **как сжать tar.lz** файлы с помощью Aspose.Zip для .NET, независимо от того, работаете ли вы с одним документом или с набором файлов. Этот **пример сжатия tar.lz** демонстрирует чистый, готовый к продакшену способ **создать архив tar lz**, который можно легко передать или сохранить. Вы можете сжимать файлы в tar.lz, используя тот же API, вызывая `SaveLzipped` после добавления всех нужных записей.

## Часто задаваемые вопросы

**Q:** Могу ли я сжимать файлы любого размера с помощью Aspose.Zip для .NET?  
**A:** Да, библиотека работает как с небольшими, так и с очень большими файлами; просто убедитесь, что у вас достаточно памяти и места на диске для временной структуры TAR.

**Q:** Совместим ли код с последним выпуском Aspose.Zip?  
**A:** Пример ориентирован на текущую версию; всегда поддерживайте пакет NuGet в актуальном состоянии для исправлений ошибок и новых функций.

**Q:** Есть ли лицензионные нюансы?  
**A:** Для использования в продакшене требуется коммерческая лицензия. Смотрите детали лицензирования на сайте [Aspose website](https://purchase.aspose.com/buy).

**Q:** Могу ли я использовать это в коммерческом проекте?  
**A:** Конечно — как только у вас будет действующая лицензия, вы можете внедрять библиотеку в любое коммерческое приложение.

**Q:** Где я могу получить помощь, если возникнут проблемы?  
**A:** Посетите [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) для поддержки сообщества и официальной помощи.

---

**Последнее обновление:** 2026-07-04  
**Тестировано с:** Aspose.Zip for .NET (latest release)  
**Автор:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Похожие руководства

- [Создать tar‑архив и добавить файлы в tar с Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Как сжать tar и создать TarBz2 с Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Добавить файлы в tar и создать tarxz‑архив с Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}