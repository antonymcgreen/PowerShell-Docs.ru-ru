---
title: Элемент Ентриселектедби для Таблеровентри для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 047a10fb6b38dfa8f78a7741fd50b781d4a14b6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787705"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должно существовать, чтобы использовать это определение табличного представления.|
|[Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, использующих это определение табличного представления.|
|[Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, использующий это определение табличного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеровентри для Таблеконтрол (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Определяет данные, отображаемые в строке таблицы.|

## <a name="remarks"></a>Примечания

Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения табличного представления. Максимальное количество дочерних элементов, которое можно использовать, не ограничено.

Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true` . Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableRowEntry` элемент, используемый для отображения свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

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

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент Таблеровентри для Таблеконтрол (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
