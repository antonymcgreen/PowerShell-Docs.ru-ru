---
title: Типы элемента для SelectionSet (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862380"
---
# <a name="types-element-for-selectionset-format"></a>Элемент Types для элемента SelectionSet (формат)

Определяет объекты .NET, заданных в выделении.

SelectionSet элемент SelectionSets (формат) элемент (формат) для конфигурации элемента (формат) типы элемента (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Types` элемент. Должен существовать по крайней мере один дочерний элемент, но не ограничено максимальное число дочерних элементов, которые могут быть добавлены.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TypeName типов (формат)](./typename-element-for-types-format.md)|Обязательный элемент.<br /><br /> Указывает объект .NET, принадлежит к набору выбора.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionSet (формат)](./selectionset-element-format.md)|Определяет набор объектов .NET, которые можно ссылаться по имени набора.|

## <a name="remarks"></a>Замечания

Объекты, определенные этим элементом входящие в состав набора, который может использоваться представлением, по определению представления (может иметь несколько определений представлений), или при указании условию выбора.  Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В этом примере показано `SelectionSet` элемент, который определяет четыре типа .NET.

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a>См. также

[Определение наборов объектов](./defining-selection-sets.md)

[Элемент SelectionSet (формат)](./selectionset-element-format.md)

[Элемент TypeName типов (формат)](./typename-element-for-types-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
