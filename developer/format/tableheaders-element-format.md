---
title: Элемент TableHeaders (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856880"
---
# <a name="tableheaders-element-format"></a>Элемент TableHeaders (формат)

Определяет заголовков столбцов таблицы.

Элемент ViewDefinitions (формат) представления (формат) TableControl-элемент (формат) TableHeaders элемента для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительские элементы из `TableHeaders` элемент. Должен быть дочерним для каждого свойства объекта, который должен отображаться. Сведения о заголовке столбца отображается в том порядке, что указаны дочерних элементов.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnHeader (формат)](./tablecolumnheader-element-format.md)|Необязательный элемент.<br /><br /> Определяет метку, ширину и выравнивания данных для столбца таблицы представления.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[TableControl-элемент (формат)](./tablecontrol-element-format.md)|Определяет формат таблицы для представления.|

## <a name="remarks"></a>Замечания

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показано `TableHeaders` элемент, который определяет два заголовка столбцов.

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

[TableControl-элемент (формат)](./tablecontrol-element-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
