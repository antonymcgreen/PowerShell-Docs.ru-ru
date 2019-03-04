---
title: Элемент TableColumnItems для TableRowEntry для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43684ce-7c3d-4d14-8dbd-061c111ee805
caps.latest.revision: 12
ms.openlocfilehash: faa9ba78397e713400f6072df9915f20d966bb37
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859450"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a>Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)

Определяет свойства или скрипты, значения которых отображаются в строке.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемента конфигурации для элемента TableRowEntry TableControl (формат) TableRowEntries для TableControl (формат) Элемент TableColumnItems для TableControlEntry для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `TableColumnItems` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnItem для TableColumnItems для TableControl (формат)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойство или скрипта, значение которого отображается в столбце строки.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableRowEntry для TableRowEntries для TableControl (формат)](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)|Определяет данные, которые отображаются в строке таблицы.|

## <a name="remarks"></a>Замечания

Объект `TableColumnItem` элемент является обязательным для каждого столбца, строки. Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableColumnItems` элемент, определяющий три свойства [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

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

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент TableColumnItem (формат)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Элемент TableRowEntry (формат)](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
