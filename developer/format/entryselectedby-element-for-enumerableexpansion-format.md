---
title: Элемент EntrySelectedBy для EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af6aff8-4c2d-4f08-9bb1-e1f3ed3e583e
caps.latest.revision: 11
ms.openlocfilehash: 6a371bdbb85d07730c32931a4a79ee40856ce298
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855590"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)

Определяет типы .NET, которые используют это определение или условие, которое должен существовать для данного определения для использования.

Элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) элемент EnumerableExpansion (формат) EntrySelectedBy элемент конфигурации для EnumerableExpansion (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать разверните коллекцию объектов данного определения.|
|[Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение разворачиваются как коллекции объектов.|
|[TypeName-элемент для EntrySelectedBy для EnumerableExpansion (формат)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение разворачиваются как коллекции объектов.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)|Определяет, как определенные коллекции .NET, объекты развертываются в том случае, когда они отображаются в представлении.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, выбора или условию выбора для определения записи. Не ограничено максимальное число дочерних элементов, которые можно использовать.

Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`. Дополнительные сведения об условиях выделения, см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)

[Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[TypeName-элемент для EntrySelectedBy для EnumerableExpansion (формат)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
