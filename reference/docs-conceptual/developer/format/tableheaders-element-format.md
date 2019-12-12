---
title: Элемент Таблехеадерс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361823"
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

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `TableHeaders`. Должен существовать дочерний элемент для каждого свойства объекта, который должен быть отображен. Сведения о заголовке столбца отображаются в том порядке, в котором указаны дочерние элементы.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнхеадер (Format)](./tablecolumnheader-element-format.md)|Необязательный элемент.<br /><br /> Определяет метку, ширину и выравнивание данных для столбца табличного представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеконтрол (Format)](./tablecontrol-element-format.md)|Определяет формат таблицы для представления.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан элемент `TableHeaders`, определяющий два заголовка столбцов.

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

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Таблеколумнхеадер (Format)](./tablecolumnheader-element-format.md)

[Элемент Таблеконтрол (Format)](./tablecontrol-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
