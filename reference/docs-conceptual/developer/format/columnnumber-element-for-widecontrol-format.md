---
title: Элемент ColumnNumber для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe9eb5f9-a193-41a4-ad47-a96ba3f8d7e3
caps.latest.revision: 8
ms.openlocfilehash: 49f501538b8f72777984a5e575b999866abcdebf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364223"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>Элемент ColumnNumber для WideControl (формат)

Указывает число столбцов, отображаемых в расширенном представлении.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) ColumnNumber для Видеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ColumnNumber`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видеконтрол (Format)](./widecontrol-element-format.md)|Определяет для представления широкий формат списка (одно значение).|

## <a name="text-value"></a>Текстовое значение

Укажите положительное целое значение.

## <a name="remarks"></a>Замечания

При определении расширенного представления можно добавить элемент `AutoSize` или элемент `ColumnNumber`, но нельзя добавить и то, и другое.

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Элемент AutoSize для Видеконтрол (Format)](./autosize-element-for-widecontrol-format.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Широкой вид (базовый)](./wide-view-basic.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
