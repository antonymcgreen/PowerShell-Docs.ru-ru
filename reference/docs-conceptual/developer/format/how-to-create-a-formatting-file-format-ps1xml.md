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
ms.openlocfilehash: 7a578dd63a53562f992b2970573258b8676e2a52
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692274"
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

   - `<Configuration></Configuration>`Теги определяют корневой `Configuration` узел. Все дополнительные XML-теги будут заключены в этот узел.

   - `<ViewDefinitions></ViewDefinitions>`Теги определяют `ViewDefinitions` узел. Все представления определяются в этом узле.

3. Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки Module. При сохранении файла используйте следующий формат имени: `MyFile.format.ps1xml` . Файлы форматирования должны использовать `.format.ps1xml` расширение.

   Теперь все готово к добавлению представлений в файл форматирования. Количество представлений, которые могут быть определены в файле форматирования, не ограничено. Можно добавить одно представление для каждого объекта, несколько представлений для одного и того же объекта или одно представление, используемое несколькими объектами.

## <a name="see-also"></a>См. также:

[Создание файла форматирования и типов Windows PowerShell](./writing-a-powershell-formatting-file.md)
