---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)
ms.openlocfilehash: a4f28c1caba3790718b99f63659cb0cbed8def16
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654991"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy, селектионкондитион для EntrySelectedBy для элемента GroupBy (Format) SelectionSetName для SelectionCondition for GroupBy (формат)

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
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Комментарии

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

Если этот элемент указан, нельзя указать элемент [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) . Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент TypeName для элемента SelectionCondition для элемента GroupBy (формат)](./typename-element-for-selectioncondition-for-groupby-format.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
