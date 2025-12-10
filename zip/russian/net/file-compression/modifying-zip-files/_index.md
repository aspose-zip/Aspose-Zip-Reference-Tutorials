---
date: 2025-12-09
description: Узнайте, как создавать zip‑архивы на C# и извлекать вложенные zip‑файлы
  с помощью Aspose.Zip для .NET в пошаговом руководстве на C#.
linktitle: Modifying Zip Files
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создание zip‑архива C# с использованием Aspose.Zip для .NET
url: /ru/net/file-compression/modifying-zip-files/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание zip‑архива C# с использованием Aspose.Zip для .NET

## Введение

Zip‑файлы – это основной формат для упаковки и сжатия данных, но в реальных сценариях часто требуется **создавать zip‑архив C#** программы, которые также могут **извлекать вложенные zip‑файлы**, переименовывать записи или «сплющивать» вложенные архивы. Aspose.Zip для .NET предоставляет чистый, полностью управляемый API, позволяющий делать всё это без низкоуровневой работы со потоками.

В этом руководстве вы узнаете, как изменить существующий zip‑архив, извлечь вложенные zip‑записи и, наконец, собрать всё в новый плоский архив – всё это с помощью лаконичного кода C#. Независимо от того, создаёте ли вы сервис обработки файлов, утилиту резервного копирования или автоматизированный конвейер развертывания, нижеописанные шаги покажут, как выполнить задачу.

## Быстрые ответы
- **Может ли Aspose.Zip создавать zip‑архив C#?** Да – класс `Archive` позволяет создавать и редактировать zip‑файлы непосредственно в C#.
- **Как извлечь вложенные zip‑файлы?** Откройте внешнюю запись как поток, создайте второй `Archive` из этого потока, затем перечислите его записи.
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для оценки; для продакшна требуется коммерческая лицензия.
- **Поддерживаемые версии .NET?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
- **Типичное время выполнения примера?** Менее секунды для нескольких мегабайт данных.

## Что такое «create zip archive C#»?

Создание zip‑архива в C# означает программную генерацию файла `.zip`, который может содержать произвольное количество файлов или папок, при желании применяя уровни сжатия, шифрование или пользовательские метаданные. Aspose.Zip абстрагирует сложность, позволяя сосредоточиться на бизнес‑логике, а не на самом формате zip.

## Почему стоит использовать Aspose.Zip для .NET?

- **Без внешних зависимостей** – чистая .NET‑библиотека, без нативных DLL.
- **Полный контроль над записями** – добавляйте, удаляйте, переименовывайте или заменяйте файлы «на лету».
- **API, ориентированное на потоки** – работа с объектами `MemoryStream`, идеально для облачных или in‑memory сценариев.
- **Надёжная работа с вложенными архивами** – легко **извлекать вложенные zip‑файлы** без временных файлов на диске.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

1. **Aspose.Zip для .NET**, установленный в вашем проекте. Скачать можно **[здесь](https://releases.aspose.com/zip/net/)**.  
2. Папка, содержащая исходные zip‑файлы, с которыми вы будете работать. Замените `"Your Document Directory"` в кодовых фрагментах на реальный путь на вашей машине.  
3. Среда разработки .NET (Visual Studio, VS Code или Rider) с целевой платформой .NET Framework 4.6+ или .NET Core 3.1+.

## Подключение пространств имён

Сначала импортируем необходимые пространства имён:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Пошаговое руководство

### Шаг 1: Открытие внешнего zip‑файла  

Мы открываем существующий архив (`outer.zip`). Инструкция `using` гарантирует автоматическое закрытие файла.

```csharp
using (Archive outer = new Archive(dataDir + "outer.zip"))
{
    // Code for Step 1
}
```

### Шаг 2: Поиск вложенных zip‑записей  

Далее сканируем внешний архив в поисках записей, заканчивающихся на `.zip`. Это и есть **внутренние zip‑файлы**, которые нужно извлечь.

```csharp
List<ArchiveEntry> entriesToDelete = new List<ArchiveEntry>();
List<string> namesToInsert = new List<string>();
List<MemoryStream> contentToInsert = new List<MemoryStream>();

foreach (ArchiveEntry entry in outer.Entries)
{
    if (entry.Name.EndsWith(".zip", StringComparison.InvariantCultureIgnoreCase))
    {
        entriesToDelete.Add(entry);
        MemoryStream innerCompressed = new MemoryStream();
        entry.Open().CopyTo(innerCompressed);
        
        // Code for extracting inner entries
    }
}
```

### Шаг 3: Извлечение вложенных записей  

Теперь рассматриваем каждый внутренний zip как отдельный `Archive`. Здесь мы **извлекаем вложенные zip‑файлы** и собираем их содержимое в памяти.

```csharp
using (Archive inner = new Archive(innerCompressed))
{
    foreach (ArchiveEntry ie in inner.Entries)
    {
        namesToInsert.Add(ie.Name);
        MemoryStream content = new MemoryStream();
        ie.Open().CopyTo(content);
        
        // Code for extracting content of inner entries
    }
}
```

### Шаг 4: Удаление записей вложенных архивов  

Получив необходимые данные, удаляем оригинальные записи вложенных zip‑файлов из внешнего архива.

```csharp
foreach (ArchiveEntry e in entriesToDelete)
{
    outer.DeleteEntry(e);
}
```

### Шаг 5: Добавление изменённых записей во внешний zip  

Наконец, вставляем извлечённые файлы обратно во внешний архив, эффективно «сплющивая» структуру, и сохраняем результат как `flatten.zip`.

```csharp
for (int i = 0; i < namesToInsert.Count; i++)
{
    outer.CreateEntry(namesToInsert[i], contentToInsert[i]);
}

outer.Save(dataDir + "flatten.zip");
```

Следуя этим пяти шагам, вы **создали zip‑архив C#**, содержащий те же файлы, что и оригинал, но без вложенных уровней zip.

## Распространённые проблемы и решения

| Проблема | Почему возникает | Решение |
|----------|------------------|---------|
| `ArgumentNullException` при открытии вложенного архива | Позиция потока `innerCompressed` находится в конце | Вызовите `innerCompressed.Position = 0;` перед созданием `Archive` |
| Большие файлы вызывают высокое потребление памяти | Все вложенные записи хранятся в объектах `MemoryStream` | Для очень больших архивов используйте временные файлы на диске (`Path.GetTempFileName()`) |
| Отсутствуют записи после «сплющивания» | Забыл добавить извлечённое содержимое в список `contentToInsert` | Убедитесь, что `contentToInsert.Add(content);` вызывается внутри внутреннего цикла |

## Часто задаваемые вопросы

### Вопрос 1: Можно ли использовать Aspose.Zip для .NET с другими языками программирования?

**Ответ:** Aspose.Zip в первую очередь предназначен для приложений .NET. Тем не менее, Aspose предоставляет библиотеки для различных языков программирования, каждая из которых адаптирована под свою среду.

### Вопрос 2: Доступна ли бесплатная пробная версия Aspose.Zip для .NET?

**Ответ:** Да, бесплатную пробную версию можно получить **[здесь](https://releases.aspose.com/)**.

### Вопрос 3: Как получить поддержку по Aspose.Zip для .NET?

**Ответ:** Для поддержки и обсуждений посетите **[форум Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

### Вопрос 4: Можно ли приобрести временную лицензию для Aspose.Zip для .NET?

**Ответ:** Да, временную лицензию можно оформить **[здесь](https://purchase.aspose.com/temporary-license/)**.

### Вопрос 5: Где найти документацию по Aspose.Zip для .NET?

**Ответ:** Документация доступна **[здесь](https://reference.aspose.com/zip/net/)**.

---

**Последнее обнов:** 2025-12-09  
**Тестировано с:** Aspose.Zip 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}