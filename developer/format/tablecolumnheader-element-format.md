---
title: Элемент TableColumnHeader (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057881"
---
# <a name="tablecolumnheader-element-format"></a>Элемент TableColumnHeader (формат)

Определяет метку, ширину столбца и выравнивание метки для столбца таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableHeaders элемента конфигурации для элемента TableColumnHeader TableControl (формат) TableHeaders для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `TableColumnHeader` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Label для TableColumnHeader для TableControl (формат)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет метку, которая отображается в верхней части столбца. Если метка не указана, используется имя свойства, значение которого отображается в строках.|
|[Ширина элемента для TableColumnHeader для TableControl (формат)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Ширина столбца (в символах).|
|[Выравнивание элемента для TableColumnHeader для TableControl (формат)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает способ отображения метки столбца. Если выравнивание не указано, подпись выравнивается в левой части.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableHeaders (формат)](./tableheaders-element-format.md)|Определяет столбцы в табличное представление.|

## <a name="remarks"></a>Замечания

Укажите заголовок для каждого столбца таблицы. Столбцы отображаются в порядке, в котором `TableColumnHeader` определенные элементы.

Таблица должна иметь одинаковое число `TableColumnHeader` элементы, что `TableRowEntry` элементы. Заголовок столбца определяет, как отображается текст в верхней части таблицы. Строки определяют, какие данные отображаются в строках таблицы.

Дополнительные сведения о компонентах в табличное представление, см. в разделе [табличное представление](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показаны два `TableColumnHeader` элементов. Первый элемент определяет столбец, метка которого указано «Столбец 1», имеет ширину 16 символов и метка которого по левому краю. Второй элемент определяет столбец, метка которого указано «Столбец 2», шириной 10 символов и которого метка размещается по центру в столбце.

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

[Выравнивание элемента для TableColumnHeader для TableControl (формат)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Label для TableColumnHeader для TableControl (формат)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Элемент TableHeaders для TableControl (формат)](./tableheaders-element-format.md)

[Ширина для TableColumnHeader для элемента TableControl (формат)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
