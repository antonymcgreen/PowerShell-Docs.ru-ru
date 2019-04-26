---
title: Элемент TableRowEntry для TableRowEntries для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18d86af7-7ff9-4968-81be-2caa61937d49
caps.latest.revision: 10
ms.openlocfilehash: 946ffb3fe857503c02b9000238a86775969abbd6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075330"
---
# <a name="tablerowentry-element-for-tablerowentries-for-tablecontrol-format"></a>Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)

Определяет данные, которые отображаются в строке таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемента конфигурации для элемента TableRowEntry TableControl (формат) TableRowEntries для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `TableRowEntry` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент EntrySelectedBy для TableRowEntry для TableControl (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет объекты, значения свойств которого отображаются в строке.|
|[Элемент TableColumnItems для TableRowEntry для TableControl (формат)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет свойства или скрипты, значения которых отображаются.|
|[Создать оболочку элемент для TableRowEntry TableControl (формат)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает, что текст, который превышает ширину столбца отображается на следующей строке.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableRowEntries для TableControl (формат)](./tablerowentries-element-for-tablecontrol-format.md)|Определяет строки таблицы.|

## <a name="remarks"></a>Замечания

Один `TableColumnItems` элемент и один `EntrySelectedBy` элемент должен быть указан.

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableRowEntry` элемент, который определяет строку, отображающую значения двух свойств [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

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

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент EntrySelectedBy для TableRowEntry для TableControl (формат)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент TableColumnItems для TableRowEntry для TableControl (формат)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент TableRowEntries для TableControl (формат)](./tablerowentries-element-for-tablecontrol-format.md)

[Создать оболочку элемент для TableRowEntry TableControl (формат)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
