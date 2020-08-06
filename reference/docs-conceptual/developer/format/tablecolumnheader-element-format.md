---
title: Элемент Таблеколумнхеадер (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6296aea5c567663b1c3c0a2cf0a57b21aa5394de
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785189"
---
# <a name="tablecolumnheader-element-format"></a>Элемент TableColumnHeader (формат)

Определяет метку, ширину столбца, а также выравнивание метки для столбца таблицы.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер для Таблехеадерс в TableControl (Format)

## <a name="syntax"></a>Синтаксис

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnHeader` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Label для Таблеколумнхеадер для Таблеконтрол (Format)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет метку, отображаемую в верхней части столбца. Если метка не указана, то используется имя свойства, значение которого отображается в строках.|
|[Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Задает ширину (в символах) столбца.|
|[Элемент Alignment для TableColumnHeader для TableControl (формат)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Задает способ отображения метки столбца. Если выравнивание не задано, то метка выравнивается слева.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableHeaders (формат)](./tableheaders-element-format.md)|Определяет столбцы табличного представления.|

## <a name="remarks"></a>Примечания

Укажите заголовок для каждого столбца таблицы. Столбцы отображаются в том порядке, в котором `TableColumnHeader` определены элементы.

Таблица должна иметь то же количество элементов, `TableColumnHeader` что и `TableRowEntry` элементы. Заголовок столбца определяет, как будет отображаться текст в верхней части таблицы. Записи строки определяют, какие данные отображаются в строках таблицы.

Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показаны два `TableColumnHeader` элемента. Первый элемент определяет столбец, метка которого равна "Column 1", имеет ширину 16 символов, а метка — слева. Второй элемент определяет столбец, метка которого равна «Column 2», имеет ширину 10 символов, а метка — по центру столбца.

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

[Элемент Alignment для TableColumnHeader для TableControl (формат)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Элемент Таблехеадерс для Таблеконтрол (Format)](./tableheaders-element-format.md)

[Ширина для Таблеколумнхеадер элемента Таблеконтрол (Format)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
