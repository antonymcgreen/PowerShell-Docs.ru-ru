---
title: Элемент Ентриселектедби для Кустоментри для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368783"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)

Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для представления (Format) Ентриселектедби Элемент для Кустоментри представления (Format)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение представления элемента управления.|
|[Элемент TypeName для Ентриселектедби для Кустоментри (Format)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение представления элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Кустоментри для Кустоментриес для представления (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|Определяет элементы управления, используемые конкретными объектами .NET.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать для использования записи, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства имеют `true`. Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [представление пользовательского элемента управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также:

[Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[Элемент TypeName для Ентриселектедби для Кустоментри (Format)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент Кустоментри для Кустоментриес для представления (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Представление пользовательского элемента управления](./creating-custom-controls.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
