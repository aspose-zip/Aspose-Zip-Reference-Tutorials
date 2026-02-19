---
date: 2026-02-07
description: Узнайте, как упаковать папку в .NET, сжимая каталог в zip и извлекая
  его обратно. Это руководство показывает, как упаковать папку с помощью Aspose.Zip
  для .NET.
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как заархивировать папку – сжатие каталога с помощью Aspose.Zip
url: /ru/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как заархивировать папку – Сжатие каталога с помощью Aspose.Zip для .NET

Если вы ищете понятное решение **how to zip folder** в .NET‑приложении, вы попали в нужное место. В этом руководстве мы пройдем весь процесс — сначала **compress directory to zip**, затем покажем точные шаги для **extract zip to directory** (то есть как распаковать папку). К концу вы получите переиспользуемый программный шаблон для операций zip folder, который работает на .NET Framework, .NET Core и .NET 5/6+.

## Быстрые ответы
- **What does “compress directory to zip” mean?** Это означает преобразование содержимого папки в один .zip файл.  
- **How do I extract zip to directory?** Используйте метод `Archive.ExtractToDirectory`, как показано в руководстве.  
- **Which .NET versions are supported?** Все современные версии .NET Framework, .NET Core и .NET 5/6+.  
- **Is a license required for production?** Да, для использования в продакшене требуется коммерческая лицензия Aspose.Zip.  
- **Can I automate this in CI/CD pipelines?** Конечно — просто добавьте тот же код в ваши скрипты сборки.

## Что такое “how to zip folder”?
**How to zip folder** просто означает взять каждый файл и подпапку внутри каталога и упаковать их в один сжатый архив. Это уменьшает размер хранилища, ускоряет передачу и создает переносимый пакет для развертывания.

## Почему использовать Aspose.Zip для .NET?
Aspose.Zip предоставляет **pure‑managed** API, не требующее нативных DLL, поддерживает огромные архивы и автоматически обрабатывает крайние случаи, такие как **zip archive password protection** и имена файлов в Unicode. Он также оптимизирован для производительности, что делает его идеальным, когда необходимо программно zip folder в сценариях с высокой пропускной способностью.

## Предварительные требования
- **Aspose.Zip for .NET** library installed (download it [здесь](https://releases.aspose.com/zip/net/)).  
- Папка на диске, которую вы хотите заархивировать — укажите её путь в переменной `dataDir`.  
- Среда разработки .NET (Visual Studio, VS Code или любой другой IDE по вашему выбору).

## Импорт пространств имён
Сначала подключите необходимые пространства имён:

```csharp
using Aspose.Zip;
using System.IO;
```

## Пошаговое руководство

### Шаг 1: Сжатие каталога в Zip (zip folder программно)
Мы создадим zip‑файл из каталога, который позже будете распаковывать. Вспомогательная функция `CompressDirectory.Run()` выполняет основную работу.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** Пример `CompressDirectory` упаковывает каждый файл из `dataDir` в `CompressDirectory_out.zip`. При желании переименуйте выходной файл в соответствии с вашими соглашениями об именовании.

### Шаг 2: Распаковка папки – How to Unzip Folder в .NET

#### Шаг 2.1: Открыть zip‑файл
Откройте сгенерированный архив с помощью `FileStream`. Это подготавливает файл к чтению.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Шаг 2.2: Создать экземпляр Archive
Создайте объект `Archive`, который представляет zip‑контейнер.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Шаг 2.3: Извлечь в каталог
Наконец, извлеките содержимое в новую папку. Это шаг **extract zip to directory**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Почему это важно
- **Consistency:** Использование одной и той же библиотеки для сжатия и извлечения гарантирует совместимые форматы архивов.  
- **Performance:** Aspose.Zip эффективно передаёт данные потоками, поэтому даже многогигабайтные архивы обрабатываются с небольшими затратами памяти.  
- **Security:** Встроенная поддержка защиты паролем позволяет обеспечить безопасность zip‑архива без дополнительного кода.

## Распространённые сценарии использования
- **Automated backups** – архивировать папку с логами каждую ночь и сохранять её в облачном хранилище.  
- **Deployment packages** – собрать статические веб‑ресурсы перед публикацией на сервер.  
- **Data exchange** – отправить набор файлов между сервисами в виде одного архива.

## Распространённые проблемы и решения
| Признак | Вероятная причина | Решение |
|---------|-------------------|---------|
| `UnauthorizedAccessException` при извлечении | Целевая папка только для чтения или используется | Убедитесь, что путь назначения доступен для записи и не заблокирован |
| Пустая папка вывода после извлечения | Неправильный путь к исходному zip‑файлу | Проверьте, что `dataDir + "CompressDirectory_out.zip"` указывает на правильный файл |
| Большие файлы вызывают OutOfMemoryException | Использование буфера по умолчанию для очень больших архивов | Используйте `ArchiveOptions` для увеличения размера буфера или передавайте файлы кусками |

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Zip для .NET с любым типом файлов?**  
A: Да, Aspose.Zip поддерживает все типы файлов — текст, бинарные, изображения, PDF и т.д.

**Q: Подходит ли Aspose.Zip для крупномасштабных приложений?**  
A: Да. Он разработан для высокопроизводительного сжатия zip в .NET, обрабатывая многогигабайтные архивы с небольшими затратами памяти.

**Q: Где можно найти полную документацию по Aspose.Zip для .NET?**  
A: Изучите подробную документацию [здесь](https://reference.aspose.com/zip/net/).

**Q: Можно ли попробовать Aspose.Zip перед покупкой?**  
A: Да, бесплатная пробная версия доступна на [странице загрузки Aspose.Zip](https://releases.aspose.com/).

**Q: Как получить поддержку по Aspose.Zip для .NET?**  
A: Посетите [форум Aspose.Zip](https://forum.aspose.com/c/zip/37) для получения помощи от сообщества и официальной поддержки.

---

**Последнее обновление:** 2026-02-07  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}