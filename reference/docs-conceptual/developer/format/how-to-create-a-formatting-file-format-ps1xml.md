---
title: Создание файла форматирования (. Format. ps1xml) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: e97e9ddb1bf81ba66e5f3cedddd22e3a861ce228
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363623"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>Как создать файл форматирования (.format.ps1xml)

В этом разделе описывается создание файла форматирования (Format. ps1xml).

> [!NOTE]
> Можно также создать файл форматирования, сделав копию одного из файлов, предоставляемых Windows PowerShell. При создании копии существующего файла удалите имеющуюся цифровую подпись и добавьте собственную сигнатуру в новый файл.

### <a name="to-create-a-formatps1xml-file"></a>Для создания файла. Format. ps1xml.

1. Создайте текстовый файл (. txt) с помощью текстового редактора, например Блокнота.

2. Скопируйте следующие строки в файл форматирования.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - \<Конфигурация >\</Настройка > Теги определяют корневой узел `Configuration`. Все дополнительные XML-теги будут заключены в этот узел.

   - <ViewDefinitions></ViewDefinitions> Теги определяют узел `ViewDefinitions`. Все представления определяются в этом узле.

3. Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки Module. При сохранении файла используйте следующий формат имени: `MyFile.format.ps1xml`. Файлы форматирования должны использовать расширение `.format.ps1xml`.

   Теперь все готово к добавлению представлений в файл форматирования. Количество представлений, которые могут быть определены в файле форматирования, не ограничено. Можно добавить одно представление для каждого объекта, несколько представлений для одного и того же объекта или одно представление, используемое несколькими объектами.

## <a name="see-also"></a>См. также:

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
