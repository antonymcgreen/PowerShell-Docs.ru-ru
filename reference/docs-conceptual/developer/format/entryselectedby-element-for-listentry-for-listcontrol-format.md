---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)
description: Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652292"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a>Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)

Определяет типы .NET, которые используют это определение представления списка или условие, которое должно существовать, чтобы использовать это определение. В большинстве случаев для представления списка требуется только одно определение. Однако можно указать несколько определений для представления списка, если вы хотите использовать одно и то же представление списка для отображения различных данных для разных объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для листентри для ListControl (Format) Ентриселектедби для листентри в ListControl (Format)

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

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение представления списка.|
|[Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение представления списка.|
|[Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)](./typename-element-for-entryselectedby-for-listcontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение представления списка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ListEntry для элемента ListControl (формат)](./listentry-element-for-listcontrol-format.md)|Определяет, как отображаются строки списка.|

## <a name="remarks"></a>Комментарии

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения представления списка. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true` . Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как определить объекты для представления списка с помощью имени типа .NET.

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a>См. также:

[Элемент ListEntry для элемента ListControl (формат)](./listentry-element-for-listcontrol-format.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[Создание представления списка](./creating-a-list-view.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
