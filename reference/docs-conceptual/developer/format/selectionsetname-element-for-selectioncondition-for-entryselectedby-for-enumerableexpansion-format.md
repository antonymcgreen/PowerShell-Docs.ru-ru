---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e18c74bb95c658f2c3e7b7454628f78d523f7609
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787501"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие будет выполнено.

Элемент конфигурации Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансионс элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy для EnumerableExpansion (Format) SelectionSetName для SelectionCondition в EntrySelectedBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

## <a name="see-also"></a>См. также

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
