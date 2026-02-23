---
date: 2026-02-23
description: Узнайте, как добавлять файлы в tar и сжимать их в архив tarxz в .NET
  с помощью Aspose.Zip. Следуйте этому пошаговому руководству для эффективного хранения
  и передачи.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Добавление файлов в tar и создание архива tarxz с помощью Aspose.Zip
url: /ru/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

codes exactly.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление файлов в tar и создание tarxz архива с Aspose.Zip

## Введение

Если вам нужно **add files to tar** и затем **create a tarxz archive .net**, Aspose.Zip for .NET делает процесс простым и надёжным. Независимо от того, упаковываете ли вы журналы, файлы конфигурации или любые другие ресурсы для хранения или передачи, сжатие в формат TarXz даёт высокий коэффициент сжатия, сохраняя знакомую структуру tar. В этом руководстве мы пройдём все шаги — включая фрагменты кода — чтобы вы могли интегрировать создание tarxz в свои .NET‑приложения с уверенностью.

## Быстрые ответы
- **What is the primary class?** `TarArchive` from `Aspose.Zip.Tar`
- **How to compress tarxz?** Use `SaveXzCompressed` after adding entries
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **License needed?** Yes, a valid Aspose.Zip license for production
- **Typical implementation time?** ~5‑10 minutes

## Что такое архив TarXz?

**TarXz archive** сочетает традиционный Unix‑контейнер `tar` с XZ‑сжатием. Часть tar объединяет несколько файлов в один поток, а XZ обеспечивает сильное, без потерь, сжатие. Этот формат популярен для распространения исходного кода, резервных копий и больших наборов данных, потому что сохраняет структуру каталогов и достигает меньшего размера файлов, чем обычный tar или zip.

## Почему создавать tarxz архив .net с помощью Aspose.Zip?

- **High compression ratio** – XZ often compresses 30‑50 % smaller than gzip.  
- **Cross‑platform compatibility** – TarXz files can be opened on Linux, macOS, and Windows.  
- **Simple API** – Aspose.Zip abstracts the low‑level details, letting you focus on your business logic.  
- **No external tools** – Everything runs inside your .NET process, perfect for cloud or CI pipelines.

## Требования

Перед началом убедитесь, что у вас есть:

- **Aspose.Zip for .NET** установлен (скачайте с официальной [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Папка, содержащая файлы, которые вы хотите заархивировать. В примерах ниже эта папка обозначена переменной `dataDir`.  
- Действительная лицензия Aspose.Zip (необязательно для оценки, требуется для продакшн‑использования).

## Импорт пространств имён

Сначала импортируйте пространства имён, которые предоставляют функциональность TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Как добавить файлы в tar с помощью Aspose.Zip

Ниже представлено пошаговое руководство, показывающее точно, как **add files to tar** перед их сжатием.

### Шаг 1: Инициализировать `TarArchive`

Создайте новый экземпляр `TarArchive`, который будет содержать файлы для сжатия.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Pro tip:** The `using` statement ensures the archive is properly disposed, releasing any unmanaged resources.

### Шаг 2: Добавить файлы в архив

Добавьте каждый файл, который хотите включить. В этом примере мы добавляем два текстовых файла, но вы можете добавить столько записей, сколько потребуется.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Why this matters:** Adding entries before compression lets Aspose.Zip build the tar container first, then apply XZ compression in a single step.

### Шаг 3: Сохранить архив с XZ‑сжатием

Наконец, запишите tar‑архив на диск, используя XZ‑сжатие. Полученный файл будет иметь расширение `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Result:** You now have a fully‑compressed `archive.tar.xz` file that can be transferred, stored, or unpacked on any platform that supports TarXz.

## Как сжать tarxz файлы с помощью Aspose.Zip

Процесс, показанный выше, по сути — это **how to compress tarxz** файлы: вы сначала добавляете файлы в tar‑контейнер (`add files to tar`), а затем вызываете `SaveXzCompressed`. Такой однострочный вызов устраняет необходимость во внешних инструментах командной строки и сохраняет всё внутри вашего кода .NET.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| **“File not found” exception** | Incorrect `dataDir` path | Verify the directory path ends with a backslash (`\`) or use `Path.Combine`. |
| **Large memory usage** | Very large files being compressed in memory | Use `TarArchive` in streaming mode (`SaveXzCompressed` overload that accepts a `Stream`). |
| **License not applied** | Missing license file | Load the license at application start: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Часто задаваемые вопросы

**Q: Is Aspose.Zip compatible with all .NET environments?**  
A: Yes, Aspose.Zip works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+. See the [documentation](https://reference.aspose.com/zip/net/) for details.

**Q: How can I obtain a temporary license for Aspose.Zip?**  
A: You can request a temporary license from the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/).

**Q: Are there additional examples for other archive formats?**  
A: Absolutely—explore the full set of examples in the [Aspose.Zip API reference](https://reference.aspose.com/zip/net/).

**Q: Where can I get help or discuss issues?**  
A: Join the conversation on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community support and official answers.

**Q: Can I try Aspose.Zip for free before buying?**  
A: Yes, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/zip/net).

## Заключение

Следуя приведённым выше шагам, вы теперь знаете **how to add files to tar** и **compress tarxz** файлы, а главное — как **create tarxz archive .net** с помощью Aspose.Zip. Этот подход даёт компактный, переносимый пакет, который можно без проблем интегрировать в любой .NET‑рабочий процесс — будь то настольная утилита, веб‑служба или автоматизированный конвейер CI/CD.

---

**Последнее обновление:** 2026-02-23  
**Тестировано с:** Aspose.Zip for .NET 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}