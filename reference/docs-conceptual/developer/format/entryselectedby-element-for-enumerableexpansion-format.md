---
title: Элемент Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 031bf10cfb1aed2c737fdd53fa4f20f025351d40
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783676"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a>Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)

Определяет типы .NET, которые используют это определение, или условие, которое должно существовать, чтобы использовать это определение.

Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби для Енумерабликспансион (Format)

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

|Элемент|Description|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.|
|[Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение того, как разворачиваются объекты коллекции.|
|[Элемент TypeName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение того, как разворачиваются объекты коллекции.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Description|
|-------------|-----------------|
|[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)|Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.|

## <a name="remarks"></a>Remarks

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи определения. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true` . Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент EnumerableExpansion (формат)](./enumerableexpansion-element-format.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Элемент TypeName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
