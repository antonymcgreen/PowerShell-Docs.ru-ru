---
title: Элемент TableColumnItem для TableColumnItems для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 5d80bdd736ad540f01c5ebc1f3d31dc9bd628ba5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862420"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)

Определяет свойство или скрипта, значение которого отображается в столбце строки.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемента конфигурации для элемента TableRowEntry TableControl (формат) TableRowEntries для TableControl (формат) Элемент TableColumnItems для TableControlEntry для элемента TableColumnItem TableControl (формат) TableColumnItems для TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <SciptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `TableColumnItem` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Выравнивание элемента для TableColumnItem для TableControl (формат)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет способ отображения данных в столбце строки.|
|[Элемент FormatString для TableColumnItem для TableControl (формат)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|Задает шаблон формата, который используется для форматирования данных в столбец строки.|
|[Элемент PropertyName для TableColumnItem для TableControl (формат)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает имя свойства, значение которого отображается.|
|[Элемент ScriptBlock для TableColumnItem для TableControl (формат)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, значение которого отображается в столбце строки.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnItems для TableControlEntry для TableControl (формат)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет свойства или скрипты, значения которых отображаются в строке.|

## <a name="remarks"></a>Замечания

В каждом столбце строки можно указать свойства объекта или скрипта. Если нет дочерних элементов не заданы, элемент — это заполнитель, а данные не отображаются.

Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показано `TableColumnItem` элемент, который отображает значение `Status` свойство [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Выравнивание элемента для TableColumnItem для TableControl (формат)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент TableColumnItems (формат)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент FormatString для TableColumnItem для TableControl (формат)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент PropertyName для TableColumnItem для TableControl (формат)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент ScriptBlock для TableColumnItem для TableControl (формат)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
