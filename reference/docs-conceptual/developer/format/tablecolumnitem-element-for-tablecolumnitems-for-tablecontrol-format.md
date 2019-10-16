---
title: Элемент Таблеколумнитем для Таблеколумнитемс для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 9e6cffc7476ef01124d95ecbf287d9788b0324c9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368233"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)

Определяет свойство или скрипт, значение которого отображается в столбце строки.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format) Таблеровентри для Таблеровентриес в TableControl (Format) Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format) Таблеколумнитем элемента для Таблеколумнитемс для TableControl (Format)

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

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableColumnItem`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Alignment для Таблеколумнитем для Таблеконтрол (Format)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Определяет, как отображаются данные в столбце строки.|
|[Элемент FormatString для Таблеколумнитем для Таблеконтрол (Format)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|Задает шаблон формата, используемый для форматирования данных в столбце строки.|
|[Элемент PropertyName для Таблеколумнитем для Таблеконтрол (Format)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Указывает имя свойства, значение которого отображается.|
|[Элемент ScriptBlock для Таблеколумнитем для Таблеконтрол (Format)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|Необязательный элемент.<br /><br /> Задает скрипт, значение которого отображается в столбце строки.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|Определяет свойства или скрипты, значения которых отображаются в строке.|

## <a name="remarks"></a>Замечания

Можно указать свойство объекта или скрипта в каждом столбце строки. Если дочерние элементы не указаны, элемент является заполнителем и данные не отображаются.

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан элемент `TableColumnItem`, отображающий значение свойства `Status` объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>См. также:

[Создание табличного представления](./creating-a-table-view.md)

[Элемент Alignment для Таблеколумнитем для Таблеконтрол (Format)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент Таблеколумнитемс (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[Элемент FormatString для Таблеколумнитем для Таблеконтрол (Format)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент PropertyName для Таблеколумнитем для Таблеконтрол (Format)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Элемент ScriptBlock для Таблеколумнитем для Таблеконтрол (Format)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
