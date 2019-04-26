---
title: Элемент EntrySelectedBy для CustomEntry для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066283"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)

Определяет типы .NET, использующих этот пользовательскую запись или условие, которое должен существовать для данной записи для использования.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для EntrySelectedBy представление (формат) Элемент для CustomEntry для представления (формат)

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
|[Элемент SelectionCondition для EntrySelectedBy для CustomEntry (формат)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного определения для использования.|
|[Элемент SelectionSetName для EntrySelectedBy для CustomEntry (формат)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение элемента управления представления.|
|[TypeName-элемент для EntrySelectedBy для CustomEntry (формат)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение элемента управления представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для CustomEntries для представления (формат)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Определяет элементы управления, используемые определенными объектами .NET.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, выбора или условию выбора для записи. Не ограничено максимальное число дочерних элементов, которые можно использовать.

Выбор условия используются для определения условия, которое должно существовать записи, которую необходимо использовать, например, если объект имеет определенное свойство или когда значения конкретного свойства или скрипта, результатом которого является `true`. Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления, см. в разделе [пользовательского элемента управления представления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для EntrySelectedBy для CustomEntry (формат)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Элемент SelectionSetName для EntrySelectedBy для CustomEntry (формат)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[TypeName-элемент для EntrySelectedBy для CustomEntry (формат)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент CustomEntry для CustomEntries для представления (формат)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Представление пользовательского элемента управления](./creating-custom-controls.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
