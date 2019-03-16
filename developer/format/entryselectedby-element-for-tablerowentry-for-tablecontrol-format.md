---
title: Элемент EntrySelectedBy для TableRowEntry для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058765"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a>Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)

Определяет типы .NET, использовать это определение представления таблицы или условие, которое должен существовать для данного определения для использования.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации (формат)

## <a name="syntax"></a>Синтаксис

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет условие, которое должен существовать для данного определения представления таблицы для использования.|
|[Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Задает набор типов .NET, которые используют это определение представления таблицы.|
|[TypeName-элемент для EntrySelectedBy для TableControl (формат)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает тип .NET, который использует это определение представления таблицы.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableRowEntry для TableControl (формат)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Определяет данные, которые отображаются в строке таблицы.|

## <a name="remarks"></a>Замечания

Необходимо указать по крайней мере один тип, выбора или условию выбора для определения представления таблицы. Не ограничено максимальное число дочерних элементов, которые можно использовать.

Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`. Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableRowEntry` элемент, который используется для отображения свойств [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

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

[Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[Элемент TableRowEntry для TableControl (формат)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[TypeName-элемент для EntrySelectedBy для TableControl (формат)](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
