---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент AutoSize для WideControl (формат)
description: Элемент AutoSize для WideControl (формат)
ms.openlocfilehash: 42dfae337ba8805e1ddcff4269401afdb3e281f6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650007"
---
# <a name="autosize-element-for-widecontrol-format"></a>Элемент AutoSize для WideControl (формат)

Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) AutoSize для Видеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `AutoSize` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Нет

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент WideControl (формат)](./widecontrol-element-format.md)|Определяет для представления широкий формат списка (одно значение).|

## <a name="remarks"></a>Комментарии

При определении расширенного представления можно добавить `AutoSize` элемент или элемент [columnNumber](./columnnumber-element-for-widecontrol-format.md) , но нельзя добавить оба элемента.

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Элемент ColumnNumber для WideControl (формат)](./columnnumber-element-for-widecontrol-format.md)

[Создание широкого представления](./creating-a-wide-view.md)

[Элемент WideControl (формат)](./widecontrol-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
