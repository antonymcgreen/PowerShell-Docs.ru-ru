---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)
description: Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)
ms.openlocfilehash: 4d600a366d2be1c453f05b301bdf575351dd51c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667765"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a>Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)

Определяет свойства или скрипты, значения которых отображаются в строке.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблеровентриес для Таблеконтрол (Format) Таблеровентри для таблеровентриес для TableControl (Format) TableColumnItems для TableControlEntry в TableControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnItems` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипт, значение которого отображается в столбце строки.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Определяет данные, отображаемые в строке таблицы.|

## <a name="remarks"></a>Комментарии

`TableColumnItem`Для каждого столбца строки требуется элемент. Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableColumnItems` элемент, определяющий три свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Таблеколумнитем (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Элемент Таблеровентри (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
