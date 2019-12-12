---
title: Элемент AutoSize для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369053"
---
# <a name="autosize-element-for-widecontrol-format"></a>Элемент AutoSize для WideControl (формат)

Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) AutoSize для Видеконтрол (Format)

## <a name="syntax"></a>Синтаксис

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `AutoSize`.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Видеконтрол (Format)](./widecontrol-element-format.md)|Определяет для представления широкий формат списка (одно значение).|

## <a name="remarks"></a>Замечания

При определении расширенного представления можно добавить элемент `AutoSize` или элемент [columnNumber](./columnnumber-element-for-widecontrol-format.md) , но нельзя добавить и то, и другое.

Дополнительные сведения о компонентах широкого представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).

Пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).

## <a name="see-also"></a>См. также:

[Элемент ColumnNumber для Видеконтрол (Format)](./columnnumber-element-for-widecontrol-format.md)

[Создание расширенного представления](./creating-a-wide-view.md)

[Элемент Видеконтрол (Format)](./widecontrol-element-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
