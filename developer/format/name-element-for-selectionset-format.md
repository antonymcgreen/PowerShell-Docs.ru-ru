---
title: Элемент Name для SelectionSet (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065161"
---
# <a name="name-element-for-selectionset-format"></a>Элемент Name для элемента SelectionSet (формат)

Указывает имя, используемое для ссылки на наборе выбора.

Элемент конфигурации элемент (формат) элемент SelectionSets (формат) элемент SelectionSet (формат) имя из SelectionSet (формат)

## <a name="syntax"></a>Синтаксис

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `Name` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionSet (формат)](./selectionset-element-format.md)|Определяет один набор объектов .NET, которые можно ссылаться по имени набора.|

## <a name="text-value"></a>Текстовое значение

Укажите имя для ссылки на наборе выбора. Нет никаких ограничений, о том, какие символы можно использовать.

## <a name="remarks"></a>Замечания

Имя, указанное здесь используется в `SelectionSetName` элемент. Набора, который может использоваться представлением, по определению представления (может иметь несколько определений представлений), или при указании условию выбора. Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).

## <a name="example"></a>Пример

В этом примере показано `SelectionSet` элемент, который определяет четыре типа .NET. Имя набора выбора является «FileSystemTypes».

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

[Определение наборов Выбор](./defining-selection-sets.md)

[Элемент SelectionSet (формат)](./selectionset-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
