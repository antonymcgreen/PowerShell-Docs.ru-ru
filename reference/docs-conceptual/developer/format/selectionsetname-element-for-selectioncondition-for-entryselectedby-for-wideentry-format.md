---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 44c88ce75ae485e1c48ceb08bfd12f739a632996
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787450"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a>Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)

Указывает набор типов .NET, которые активируют условие. При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения расширенного представления.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) селектионкондитион для EntrySelectedBy для WideEntry в SelectionSetName для SelectionCondition (формат)

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
|[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|Определяет условие, которое должно существовать, чтобы использовать это определение.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения. Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования. Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также

[Создание широкого представления](./creating-a-wide-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Определение наборов выделенных фрагментов](./defining-selection-sets.md)

[Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
