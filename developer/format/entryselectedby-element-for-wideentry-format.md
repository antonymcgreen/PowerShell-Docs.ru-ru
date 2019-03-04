---
title: Элемент EntrySelectedBy для WideEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854980"
---
# <a name="entryselectedby-element-for-wideentry-format"></a>Элемент EntrySelectedBy для элемента WideEntry (формат)

Определяет типы .NET, использовать это определение широкое представление или условие, которое должен существовать для данного определения для использования.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для WideEntry (формат)

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
|[Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного определения широкое представление для использования.|
|[Элемент SelectionSetName для EntrySelectedBy для WideEntry (формат)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение широкое представление.|
|[TypeName-элемент для EntrySelectedBy для WideEntry (формат)](./typename-element-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение широкое представление.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideEntry (формат)](./wideentry-element-for-widecontrol-format.md)|Предоставляет определение широкое представление.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, выбора или условию выбора для определения широкое представление. Не ограничено максимальное число дочерних элементов, которые можно использовать.

Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или значение сценарий принимает значение `true`. Дополнительные сведения об условиях выделения, см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Элемент WideEntry (формат)](./wideentry-element-for-widecontrol-format.md)

[Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент SelectionSetName для EntrySelectedBy для WideEntry (формат)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[TypeName-элемент для EntrySelectedBy для WideEntry (формат)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[Создание широкое представление](./creating-a-wide-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
