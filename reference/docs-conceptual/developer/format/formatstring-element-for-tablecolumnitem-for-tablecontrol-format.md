---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)
description: Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)
ms.openlocfilehash: 3d386e61ac321c05e0b298019c2298f76b391b21
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667901"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a>Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)

Задает шаблон формата, определяющий способ отображения значения свойства или скрипта таблицы.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Таблеколумнитемс элемент (Format) Таблеколумнитем элемент (формат) элемент FormatString для TableColumnItem (Format)

## <a name="syntax"></a>Синтаксис

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FormatString` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Таблеколумнитем (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Определяет свойство или скрипт, значение которого отображается в столбце строки.|

## <a name="text-value"></a>Текстовое значение

Укажите шаблон, используемый для форматирования данных. Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.

## <a name="remarks"></a>Комментарии

Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений. Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).

Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).

## <a name="example"></a>Пример

В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a>См. также:

[Создание представления таблицы](./creating-a-table-view.md)

[Форматирование отображаемых данных](./formatting-displayed-data.md)

[Элемент Таблеколумнитем (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
