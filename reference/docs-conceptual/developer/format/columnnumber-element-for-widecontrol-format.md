---
title: Элемент ColumnNumber для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5f151bb0e629efcebe6295cdcae6cebcbbb1b39b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783863"
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

|Элемент|Description|
|-------------|-----------------|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Определяет для представления широкий формат списка (одно значение).|

## <a name="text-value"></a>Текстовое значение

Укажите положительное целое значение.

## <a name="remarks"></a>Remarks

При определении широкого представления можно добавить `AutoSize` элемент или `ColumnNumber` элемент, но нельзя добавить оба элемента.

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Элемент AutoSize для Видеконтрол (Format)](./autosize-element-for-widecontrol-format.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Широкое представление (базовое)](./wide-view-basic.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
