---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ColumnNumber для WideControl (формат)
description: Элемент ColumnNumber для WideControl (формат)
ms.openlocfilehash: 1ddbbfbd5b53065afcc6c1326d6abf1fadedc67b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648402"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>Элемент ColumnNumber для WideControl (формат)

Указывает число столбцов, отображаемых в расширенном представлении.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) ColumnNumber для Видеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ColumnNumber` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Определяет для представления широкий формат списка (одно значение).|

## <a name="text-value"></a>Текстовое значение

Укажите положительное целое значение.

## <a name="remarks"></a>Комментарии

При определении широкого представления можно добавить `AutoSize` элемент или `ColumnNumber` элемент, но нельзя добавить оба элемента.

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Элемент AutoSize для Видеконтрол (Format)](./autosize-element-for-widecontrol-format.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Широкое представление (базовое)](./wide-view-basic.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
