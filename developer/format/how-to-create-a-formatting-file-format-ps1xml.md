---
title: Как создать файл форматирования (. format.ps1xml) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: e97e9ddb1bf81ba66e5f3cedddd22e3a861ce228
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065507"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>Как создать файл форматирования (.format.ps1xml)

В этом разделе описывается, как создать файл форматирования (. format.ps1xml).

> [!NOTE]
> Кроме того, можно создать файл форматирования путем копирования одного из файлов, предоставляемые Windows PowerShell. Если следует создать копию существующего файла, удалите существующие цифровой подписи и добавить свою собственную подпись в новый файл.

### <a name="to-create-a-formatps1xml-file"></a>Для создания. файле format.ps1xml.

1. Создайте текстовый файл (.txt) с помощью текстового редактора, например в блокноте.

2. Скопируйте следующие строки в файле форматирования.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - \<Конфигурации >\</Configuration > теги определяющие корневой `Configuration` узла. Все дополнительные теги XML будет заключаться в этот узел.

   - <ViewDefinitions> </ViewDefinitions> Теги определяют `ViewDefinitions` узла. Все представления определяются в пределах этого узла.

3. Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки модуля. При сохранении файла, используйте следующий формат имени: `MyFile.format.ps1xml`. Необходимо использовать файлы форматирования `.format.ps1xml` расширения.

   Теперь вы готовы добавить представления в файле форматирования. Нет ограничений на количество представлений, которые могут быть определены в файле форматирования. Можно добавить одно представление для каждого объекта, несколько представлений для одного объекта или одно представление, используется несколько объектов.

## <a name="see-also"></a>См. также

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
