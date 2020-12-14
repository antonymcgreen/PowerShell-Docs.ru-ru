---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)
ms.openlocfilehash: dcb59fc438ae217870566f09204fb16b8f031614
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665793"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a>Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)

Указывает свойство .NET, которое запускает условие. Если это свойство имеется или если оно имеет значение `true` , условие выполняется и используется запись таблицы.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition в EntrySelectedBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Определяет условие, которое должно существовать для использования этой записи таблицы.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET.

## <a name="remarks"></a>Комментарии

Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может одновременно указывать оба значения. Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
