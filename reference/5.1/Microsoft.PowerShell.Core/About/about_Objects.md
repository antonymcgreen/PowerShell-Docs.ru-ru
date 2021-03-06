---
description: Содержит ценные сведения об объектах в Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: 678eececc2625bf02a706e8ef61c83056443a12f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232373"
---
# <a name="about-objects"></a>Об объектах

## <a name="short-description"></a>Краткое описание

Содержит ценные сведения об объектах в Windows PowerShell.

## <a name="long-description"></a>Полное описание

Каждое действие, выполняемое в Windows PowerShell, происходит в контексте объектов. По мере перемещения данных от одной команды к другой она перемещается как один или несколько идентифицируемых объектов. Затем объект представляет собой коллекцию данных, представляющих элемент. Объект состоит из трех типов данных: типа объектов, его методов и свойств.

## <a name="types-methods-and-properties"></a>Типы, методы и свойства

Тип объекта указывает на тип объекта. Например, объект, представляющий файл, является объектом FileInfo.

Методы объекта — это действия, которые можно выполнять над объектом.
Например, объекты FileInfo имеют метод CopyTo, который можно использовать для копирования файла.

Свойства объекта хранят сведения об объекте. Например, объекты FileInfo имеют свойство LastWriteTime, которое хранит дату и время последнего обращения к файлу.

При работе с объектами можно использовать их методы и свойства в командах для выполнения действий и управления данными.

## <a name="objects-in-pipelines"></a>Объекты в конвейерах

Когда команды объединяются в конвейере, они передают данные друг другу как объекты. При выполнении первой команды она отправляет один или несколько объектов в конвейер во вторую команду. Вторая команда получает объекты из первой команды, обрабатывает объекты, а затем передает новые или измененные объекты в следующую команду в конвейере.
Это остается до тех пор, пока не будут выполнены все команды в конвейере.

В следующем примере показано, как передаются объекты из одной команды в следующую:

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

Первая команда `Get-ChildItem C:` возвращает файл или объект каталога для каждого элемента в корневом каталоге файловой системы. Объекты File и Directory передаются по конвейеру во вторую команду.

Вторая команда `where { $_.PsIsContainer -eq $false }` использует свойство PSIsContainer всех объектов файловой системы для выбора только тех файлов, которые имеют значение false ( \$ false) в свойстве PSIsContainer. Папки, которые являются контейнерами и, таким словами, имеют значение true ( \$ true) в свойстве PSIsContainer, не выбираются.

Вторая команда передает только файловые объекты в третью команду `Format-List` , которая отображает объекты файлов в списке.

## <a name="see-also"></a>См. также:

[about_Methods](about_Methods.md)

[about_Object_Creation](about_Object_Creation.md)

[about_Properties](about_Properties.md)

[about_Pipelines](about_Pipelines.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
