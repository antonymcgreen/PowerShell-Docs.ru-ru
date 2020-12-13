---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)
ms.openlocfilehash: b23ee5310d415cf287bf99c73b1173f70ae15f4c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651646"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элемента управления, для которого элемент Control элемента (Format) Кустоментри элемент для Кустоментриес для элементов управления элемента Ентриселектедби представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) SelectionCondition для EntrySelectedBy для элементов управления представления (Format) SelectionSetName для SelectionCondition для элементов управления представления (формат)

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
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|Определяет условие, которое должно существовать для использования определения элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Комментарии

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>См. также:

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
