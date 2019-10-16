---
title: Элемент Ентриселектедби для Таблеровентри для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363343"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a>Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)

Определяет типы .NET, использующие это определение табличного представления, или условие, которое должно существовать, чтобы использовать это определение.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение табличного представления.|
|[Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение табличного представления.|
|[Элемент TypeName для Ентриселектедби для Таблеконтрол (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение табличного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеровентри для Таблеконтрол (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Определяет данные, отображаемые в строке таблицы.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения табличного представления. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true`. Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `TableRowEntry`, используемый для отображения свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент Таблеровентри для Таблеконтрол (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Элемент TypeName для Ентриселектедби для Таблеконтрол (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
