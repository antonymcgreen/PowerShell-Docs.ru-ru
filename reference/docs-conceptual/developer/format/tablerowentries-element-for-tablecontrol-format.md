---
title: Элемент Таблеровентриес для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: 88de19be02de4933f892e02093403a82ccdd5788
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368153"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableRowEntries`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеровентри для Таблеровентриес для Таблеконтрол (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет данные, отображаемые в строке таблицы.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеконтрол (Format)](./tablecontrol-element-format.md)|Определяет формат таблицы для представления.|

## <a name="remarks"></a>Замечания

Необходимо указать один или несколько элементов `TableRowEntry` для табличного представления. Не существует максимального ограничения числа элементов `TableRowEntry`, которые могут быть добавлены, а также их порядка.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `TableRowEntries`, определяющий строку, в которой отображаются значения двух свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

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

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Таблеконтрол (Format)](./tablecontrol-element-format.md)

[Элемент Таблеровентри (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
