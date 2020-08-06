---
title: Элемент Таблехеадерс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b3176cbe1316d5b30cb61831d9915a80389709a5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787433"
---
# <a name="tableheaders-element-format"></a>Элемент TableHeaders (формат)

Определяет заголовки для столбцов таблицы.

Элемент Виевдефинитионс (Format) представления (Format) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `TableHeaders` элемента. Должен существовать дочерний элемент для каждого свойства объекта, который должен быть отображен. Сведения о заголовке столбца отображаются в том порядке, в котором указаны дочерние элементы.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)|Необязательный элемент.<br /><br /> Определяет метку, ширину и выравнивание данных для столбца табличного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableControl (формат)](./tablecontrol-element-format.md)|Определяет формат таблицы для представления.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан `TableHeaders` элемент, определяющий два заголовка столбцов.

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)

[Элемент TableControl (формат)](./tablecontrol-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
