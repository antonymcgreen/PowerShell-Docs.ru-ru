---
ms.date: 09/13/2016
ms.topic: reference
title: Как создать файл форматирования (.format.ps1xml)
description: Как создать файл форматирования (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651994"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>Как создать файл форматирования (.format.ps1xml)

В этом разделе описывается создание файла форматирования (.format.ps1XML).

> [!NOTE]
> Можно также создать файл форматирования, сделав копию одного из файлов, предоставляемых Windows PowerShell. При создании копии существующего файла удалите имеющуюся цифровую подпись и добавьте собственную сигнатуру в новый файл.

### <a name="to-create-a-formatps1xml-file"></a>Создание .format.ps1XML-файла.

1. Создайте текстовый файл (. txt) с помощью текстового редактора, например Блокнота.

2. Скопируйте следующие строки в файл форматирования.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - `<Configuration></Configuration>`Теги определяют корневой `Configuration` узел. Все дополнительные XML-теги будут заключены в этот узел.

   - `<ViewDefinitions></ViewDefinitions>`Теги определяют `ViewDefinitions` узел. Все представления определяются в этом узле.

3. Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки Module. При сохранении файла используйте следующий формат имени:  `MyFile.format.ps1xml` . Файлы форматирования должны использовать `.format.ps1xml` расширение.

   Теперь все готово к добавлению представлений в файл форматирования. Количество представлений, которые могут быть определены в файле форматирования, не ограничено. Можно добавить одно представление для каждого объекта, несколько представлений для одного и того же объекта или одно представление, используемое несколькими объектами.

## <a name="see-also"></a>См. также:

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
