---
title: Элемент Таблеколумнитемс для Таблеровентри для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43684ce-7c3d-4d14-8dbd-061c111ee805
caps.latest.revision: 12
ms.openlocfilehash: d05437aaa9652e7f81d0854d1a746acffe145699
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361813"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a>Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)

Определяет свойства или скрипты, значения которых отображаются в строке.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format) Таблеровентри для Таблеровентриес в TableControl (Format) Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableColumnItems`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнитем для Таблеколумнитемс для Таблеконтрол (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипт, значение которого отображается в столбце строки.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеровентри для Таблеровентриес для Таблеконтрол (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Определяет данные, отображаемые в строке таблицы.|

## <a name="remarks"></a>Замечания

Для каждого столбца строки требуется элемент `TableColumnItem`. Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан элемент `TableColumnItems`, определяющий три свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

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

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Таблеколумнитем (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Элемент Таблеровентри (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
