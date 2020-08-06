---
title: Элемент Ентриселектедби для Кустоментри для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 75a0f42e7722b54791a873200a35c8fcbbd665b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774139"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a>Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)

Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента представления (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение.|
|[Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение элемента управления.|
|[Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)](./typename-element-for-entryselectedby-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение элемента управления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)](./customentry-element-for-customcontrol-for-groupby-format.md)|Предоставляет определение элемента управления.|

## <a name="remarks"></a>Примечания

Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства не равны `true` . Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)](./typename-element-for-entryselectedby-for-groupby-format.md)

[Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)](./customentry-element-for-customentries-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
