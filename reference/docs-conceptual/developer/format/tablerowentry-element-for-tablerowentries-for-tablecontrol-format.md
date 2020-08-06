---
title: Элемент Таблеровентри для Таблеровентриес для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 83076ae5b2c48992ce5e621c65fc9937efb68b87
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787416"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a>Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)

Определяет данные, отображаемые в строке таблицы.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format) Таблеровентри для Таблеровентриес в TableControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableRowEntry` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Таблеровентри для Таблеконтрол (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет объекты, значения свойств которых отображаются в строке.|
|[Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойства или скрипты, значения которых отображаются.|
|[Элемент Wrap для Таблеровентри для Таблеконтрол (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает, что текст, превышающий ширину столбца, отображается на следующей строке.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableRowEntries для элемента TableControl (формат)](./tablerowentries-element-for-tablecontrol-format.md)|Определяет строки таблицы.|

## <a name="remarks"></a>Примечания

`TableColumnItems`Необходимо указать один элемент и один `EntrySelectedBy` элемент.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableRowEntry` элемент, определяющий строку, в которой отображаются значения двух свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
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
```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Ентриселектедби для Таблеровентри для Таблеконтрол (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент TableRowEntries для элемента TableControl (формат)](./tablerowentries-element-for-tablecontrol-format.md)

[Элемент Wrap для Таблеровентри для Таблеконтрол (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
