---
date: 2025-12-04
description: Узнайте, как выполнять сжатие Aspose Zip, добавлять файлы в tar‑архив
  и создавать файлы TarXz в .NET с помощью Aspose.Zip. Следуйте нашему пошаговому
  руководству для эффективного хранения и передачи.
language: ru
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: 'Сжатие Aspose Zip: Сжатие в TarXz с помощью Aspose.Zip для .NET'
url: /net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сжатие Aspose Zip: Сжатие в TarXz с помощью Aspose.Zip для .NET

## Введение

## Краткие ответы
- **Какая библиотека обрабатывает сжатие?** Aspose.Zip for .NET  
- **Какой формат создает пример?** `archive.tar.xz` (TarXz)  
- **Нужна ли лицензия для разработки?** Временная лицензия работает для тестирования; полная лицензия требуется для продакшн.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Сколько времени занимает реализация?** Около 5‑10 минут для базового архива

## Что такое сжатие Aspose Zip?

Aspose Zip compression — это набор API, предоставляемых библиотекой Aspose.Zip for .NET, позволяющих программно создавать, читать и изменять архивные файлы (ZIP, TAR, GZIP, XZ и т.д.). Библиотека абстрагирует низкоуровневые детали потоков сжатия, предоставляя чистый объектно‑ориентированный способ работы с архивами.

## Почему использовать TarXz с Aspose Zip Compression?

* **Высокий коэффициент сжатия** – XZ использует алгоритм LZMA2, который часто дает файлы меньшего размера, чем стандартный GZIP.  
* **Кросс‑платформенная совместимость** – архивы TarXz широко поддерживаются в Linux, macOS и Windows.  
* **Упрощённый API** – С помощью Aspose.Zip можно создать контейнер TAR и сжать его в XZ всего за несколько строк кода.  

## Требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- **Aspose.Zip for .NET** установлен. Вы можете скачать его со официальной [страницы документации Aspose.Zip](https://reference.aspose.com/zip/net/).  
- Папка на вашем компьютере, содержащая файлы, которые вы хотите сжать. В примерах кода эта папка указывается переменной `dataDir`.

## Import Namespaces for Aspose Zip Compression

Эти пространства имён предоставляют доступ к функционалу TAR и XZ.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Step‑by‑Step Guide

### Шаг 1: Создать архив TarXz

Сначала мы создадим контейнер TAR, а затем сожмём его с помощью XZ.

#### 1.1 Инициализировать TarArchive

```csharp
using (TarArchive archive = new TarArchive())
{
```

#### 1.2 Добавить файлы в архив – Как **add files tar archive**

Метод `CreateEntry` добавляет каждый файл в контейнер TAR. Здесь мы **add files tar archive**, указывая имя записи и путь к исходному файлу.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

#### 1.3 Сохранить архив с сжатием XZ

Наконец, мы указываем Aspose.Zip сжать данные TAR с помощью XZ и записать результат на диск.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

Вот и всё — три лаконичных вызова, и у вас есть полностью сжатый файл TarXz.

### Распространённые подводные камни и советы
- **Пути к файлам** – Убедитесь, что `dataDir` заканчивается разделителем пути (`\` или `/`), чтобы избежать некорректных путей.  
- **Большие файлы** – Для очень больших исходных файлов рассмотрите возможность потоковой передачи данных вместо загрузки их целиком; Aspose.Zip поддерживает создание записей на основе потоков.  
- **Лицензия** – Если запустить код без действующей лицензии, библиотека будет работать в режиме оценки и может добавить водяной знак к результату.

## Заключение

В этом руководстве мы продемонстрировали, как **aspose zip compression** можно использовать для **add files tar archive** и создания пакета TarXz всего за несколько строк C#. Интегрируя эти шаги в ваши .NET‑приложения, вы получите эффективные кросс‑платформенные возможности архивирования, снижающие затраты на хранение и повышающие производительность передачи.

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.Zip со всеми средами .NET?**  
A: Да, Aspose.Zip работает с .NET Framework 4.5+, .NET Core 3.1+, и .NET 5/6/7. См. [documentation](https://reference.aspose.com/zip/net/) для подробностей.

**Q: Как получить временную лицензию для Aspose.Zip?**  
A: Вы можете запросить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Есть ли больше примеров использования Aspose.Zip?**  
A: Конечно. Официальная документация содержит обширный набор примеров, охватывающих ZIP, TAR, GZIP, XZ и многое другое. См. [documentation](https://reference.aspose.com/zip/net/).

**Q: Где можно получить помощь или обсудить проблемы Aspose.Zip?**  
A: Форум сообщества — отличное место для вопросов: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).

**Q: Можно ли попробовать Aspose.Zip бесплатно перед покупкой?**  
A: Да, бесплатная пробная версия доступна для скачивания [здесь](https://releases.aspose.com/zip/net).

---

**Последнее обновление:** 2025-12-04  
**Тестировано с:** Aspose.Zip 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}