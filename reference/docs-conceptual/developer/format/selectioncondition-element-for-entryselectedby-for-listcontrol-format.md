---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
ms.openlocfilehash: e93499691dd0046265e43abd26497b2974546083
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655103"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)

Определяет условие, которое должно существовать для использования этого определения представления списка. Количество условий выбора, которое можно указать для определения списка, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry (Format)

## <a name="syntax"></a>Синтаксис

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|
|[Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые активируют условие.|
|[Элемент TypeName для Селектионкондитион для Ентриселектедби для Листентри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Таблеровентри (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.|

## <a name="remarks"></a>Комментарии

Лвхен вы определяете условие выбора, применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).

## <a name="see-also"></a>См. также:

[Создание представления списка](./creating-a-list-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент Листентри (Format)](./listentry-element-for-listcontrol-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Элемент TypeName для Ентриселектедби для Листентри (Format)](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
