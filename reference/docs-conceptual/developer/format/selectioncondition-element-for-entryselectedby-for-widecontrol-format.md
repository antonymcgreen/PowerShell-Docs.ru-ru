---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
ms.openlocfilehash: 8c51ca72edc6ad174dc289c61a8987e8f9495d19
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655110"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a>Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)

Определяет условие, которое должно существовать, чтобы использовать это определение. Количество условий выбора, которое можно указать для определения расширенной записи, не ограничено.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry (Format)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента. Необходимо указать один `PropertyName` `ScriptBlock` элемент или. `SelectionSetName`Элементы и `TypeName` являются необязательными. Можно указать один из этих элементов.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает блок скрипта, который запускает условие.|
|[Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|Необязательный элемент.<br /><br /> Указывает набор типов .NET, которые инициируют условие.|
|[Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для элемента WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)|Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.|

## <a name="remarks"></a>Комментарии

Для каждой широкой записи должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.

При определении условия выбора применяются следующие требования.

- Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).

## <a name="see-also"></a>См. также:

[Создание широкого представления](./creating-a-wide-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Элемент EntrySelectedBy для элемента WideEntry (формат)](./entryselectedby-element-for-wideentry-format.md)

[Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
