---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
ms.openlocfilehash: 2fb09e27eef1ce5d6e864c72edb595817d91f729
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655037"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения табличного представления.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy для TableRowEntry в SelectionSetName для SelectionCondition (формат)

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
|[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Определяет условие, которое должно существовать для использования в этом определении табличного представления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Комментарии

Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание табличного представления](./creating-a-table-view.md).

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
