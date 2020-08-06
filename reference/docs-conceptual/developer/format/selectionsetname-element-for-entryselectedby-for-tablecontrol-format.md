---
title: Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e68aa74b201abf345e87411db6cb2787ddd4f72b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772694"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a>Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)

Указывает набор типов .NET, которые использует эту запись табличного представления. Количество наборов выбора, которые можно указать для записи, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби элемент (Format) Селектионсетнаме для EntrySelectedBy в TableRowEntry (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, которые используют эту запись, или условие, которое должно существовать для использования этой записи.|

## <a name="text-value"></a>Текстовое значение

Укажите имя набора выбора.

## <a name="remarks"></a>Примечания

Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях. Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов. Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).

Если для записи указан набор элементов, то нельзя указать имя типа. Дополнительные сведения об указании типа .NET см. в разделе [элемент TypeName для ентриселектедби для таблеровентри (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="see-also"></a>См. также

[Элемент Ентриселектедби (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Определение наборов объектов для представления](./defining-selection-sets.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
