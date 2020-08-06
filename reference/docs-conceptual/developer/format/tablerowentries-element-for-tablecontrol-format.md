---
title: Элемент Таблеровентриес для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4cc5d354df3e552e181a95148caa020f0041db92
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785121"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a>Элемент TableRowEntries для элемента TableControl (формат)

Определяет строки таблицы.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableRowEntries` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет данные, отображаемые в строке таблицы.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableControl (формат)](./tablecontrol-element-format.md)|Определяет формат таблицы для представления.|

## <a name="remarks"></a>Примечания

Необходимо указать один или несколько `TableRowEntry` элементов для табличного представления. Максимальное ограничение количества `TableRowEntry` элементов, которое можно добавить, не ограничено.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableRowEntries` элемент, определяющий строку, в которой отображаются значения двух свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент TableControl (формат)](./tablecontrol-element-format.md)

[Элемент Таблеровентри (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
