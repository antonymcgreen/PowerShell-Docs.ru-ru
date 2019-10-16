---
title: Элемент Таблеровентри для Таблеровентриес для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18d86af7-7ff9-4968-81be-2caa61937d49
caps.latest.revision: 10
ms.openlocfilehash: 946ffb3fe857503c02b9000238a86775969abbd6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361803"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableRowEntry`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Ентриселектедби для Таблеровентри для Таблеконтрол (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет объекты, значения свойств которых отображаются в строке.|
|[Элемент Таблеколумнитемс для Таблеровентри для Таблеконтрол (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойства или скрипты, значения которых отображаются.|
|[Элемент Wrap для Таблеровентри для Таблеконтрол (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает, что текст, превышающий ширину столбца, отображается на следующей строке.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеровентриес для Таблеконтрол (Format)](./tablerowentries-element-for-tablecontrol-format.md)|Определяет строки таблицы.|

## <a name="remarks"></a>Замечания

Необходимо указать один элемент `TableColumnItems` и один элемент `EntrySelectedBy`.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `TableRowEntry`, определяющий строку, в которой отображаются значения двух свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

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

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Ентриселектедби для Таблеровентри для Таблеконтрол (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент Таблеколумнитемс для Таблеровентри для Таблеконтрол (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент Таблеровентриес для Таблеконтрол (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[Элемент Wrap для Таблеровентри для Таблеконтрол (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
