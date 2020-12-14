---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)
description: Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665589"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a>Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)

Указывает свойство, значение которого отображается в столбце строки.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Таблеколумнитемс элемент (Format) Таблеколумнитем элемент (Format) PropertyName элемент для TableColumnItem (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнитем (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в столбце строки.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства, значение которого отображается.

## <a name="remarks"></a>Комментарии

Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).

## <a name="example"></a>Пример

В этом примере показан `TableColumnItem` элемент, указывающий `Status` свойство объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Элемент Таблеколумнитем (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
