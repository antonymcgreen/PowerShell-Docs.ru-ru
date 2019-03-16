---
title: Элемент TableRowEntries для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: 88de19be02de4933f892e02093403a82ccdd5788
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055739"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a>Элемент TableRowEntries для элемента TableControl (формат)

Определяет строки таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемент конфигурации для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `TableRowEntries` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableRowEntry для TableRowEntries для TableControl (формат)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|Обязательный элемент.<br /><br /> Определяет данные, которые отображаются в строке таблицы.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[TableControl-элемент (формат)](./tablecontrol-element-format.md)|Определяет формат таблицы для представления.|

## <a name="remarks"></a>Замечания

Необходимо указать один или несколько `TableRowEntry` элементы для представления таблицы. Не ограничено максимальное число `TableRowEntry` элементы, которые могут быть добавлены и не важен их порядок.

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показан `TableRowEntries` элемент, который определяет строку, отображающую значения двух свойств [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

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

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[TableControl-элемент (формат)](./tablecontrol-element-format.md)

[Элемент TableRowEntry (формат)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
