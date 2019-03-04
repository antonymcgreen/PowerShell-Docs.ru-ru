---
title: Элемент FormatString для TableColumnItem для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a150731-d4b4-4d63-8db5-f14d463c8c37
caps.latest.revision: 13
ms.openlocfilehash: b7e1d0adc43254141056a729e1c1cc9699b6ac9b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854330"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a>Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)

Задает шаблон формата, который определяет способ отображения значения свойства или скрипт таблицы.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) элемент TableColumnItems (формат) TableColumnItem элемент конфигурации (формат) Элемент FormatString для TableColumnItem (формат)

## <a name="syntax"></a>Синтаксис

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `FormatString` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент TableColumnItem (формат)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|Определяет свойство или скрипта, значение которого отображается в столбце строки.|

## <a name="text-value"></a>Текстовое значение

Укажите шаблон, используемый для форматирования данных. Например, этот шаблон можно использовать для форматирования значения любого свойства, который относится к типу [System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0: mm}.

## <a name="remarks"></a>Замечания

Строки формата может использоваться при создании представления таблиц, представлений списков, широкие представления или представления. Дополнительные сведения о форматировании значения, отображаемого в представлении см. в разделе [форматирования отображаемых данных](./formatting-displayed-data.md).

Дополнительные сведения о компонентах в табличное представление, см. в разделе [табличное представление](./creating-a-table-view.md).

## <a name="example"></a>Пример

Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a>См. также

[Создание представления таблицы](./creating-a-table-view.md)

[Форматирование отображаемых данных](./formatting-displayed-data.md)

[Элемент TableColumnItem (формат)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
