---
title: Элемент Таблеколумнитем для Таблеколумнитемс для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: beadf771f02519394d799a03db374050e3302321
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785172"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)

Определяет свойство или скрипт, значение которого отображается в столбце строки.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблеровентриес для Таблеконтрол (Format) Таблеровентри для таблеровентриес для TableControl (Format) TableColumnItems для TableControlEntry для TableControl (Format) TableColumnItem для TableColumnItems в TableControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnItem` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Alignment для TableColumnItem для TableControl (формат)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет, как отображаются данные в столбце строки.|
|[Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|Задает шаблон формата, используемый для форматирования данных в столбце строки.|
|[Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает имя свойства, значение которого отображается.|
|[Элемент ScriptBlock для TableColumnItem для TableControl (формат)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается в столбце строки.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет свойства или скрипты, значения которых отображаются в строке.|

## <a name="remarks"></a>Примечания

Можно указать свойство объекта или скрипта в каждом столбце строки. Если дочерние элементы не указаны, элемент является заполнителем и данные не отображаются.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан `TableColumnItem` элемент, отображающий значение `Status` свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Alignment для TableColumnItem для TableControl (формат)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент Таблеколумнитемс (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент ScriptBlock для TableColumnItem для TableControl (формат)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
