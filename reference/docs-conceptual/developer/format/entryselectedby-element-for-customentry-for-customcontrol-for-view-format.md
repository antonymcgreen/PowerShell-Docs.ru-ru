---
title: Элемент Ентриселектедби для Кустоментри для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4d4900cefb0d499397fc9dff7e037ce0a541f72f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783693"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)

Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol в элементе кустоментри для представления кустоментриес для ентриселектедби для представления (формат).

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

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

## <a name="remarks"></a>Примечания

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать для использования записи, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства равны `true` . Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [представление пользовательского элемента управления](./creating-custom-controls.md).

## <a name="see-also"></a>См. также

[Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[Элемент TypeName для Ентриселектедби для Кустоментри (Format)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[Элемент Кустоментри для Кустоментриес для представления (Format)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[Представление пользовательского элемента управления](./creating-custom-controls.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
