---
title: Элемент FormatString для WideItem для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860940"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a>Элемент FormatString для элемента WideItem для элемента WideControl (формат)

Задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент WideControl (формат) элемент WideEntries (формат) WideEntry элемент конфигурации для элемента WideItem WideControl (формат) элемент FormatString WideControl (формат) для WideItem для WideControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние элементы и родительский элемент `FormatString` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideItem для WideControl (формат)](./wideitem-element-for-widecontrol-format.md)|Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.|

## <a name="text-value"></a>Текстовое значение

Укажите шаблон, используемый для форматирования данных. Например, можно использовать этот шаблон для форматирования значения любого свойства, который относится к типу [System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0: mm}.

## <a name="remarks"></a>Замечания

Строки формата может использоваться при создании представления таблиц, представлений списков, широкие представления или представления. Дополнительные сведения о форматировании значения, отображаемого в представлении см. в разделе [форматирования отображаемых данных](./formatting-displayed-data.md).

Дополнительные сведения об использовании строки формата в широкие представления см. в разделе [Создание широкое представление](./creating-a-wide-view.md).

## <a name="example"></a>Пример

Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a>См. также

[Создание широкое представление](./creating-a-wide-view.md)

[Элемент WideItem для WideControl (формат)](./wideitem-element-for-widecontrol-format.md)

[Написание форматирования Windows PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
