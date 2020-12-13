---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента GroupBy (формат)
description: Элемент ScriptBlock для элемента GroupBy (формат)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665247"
---
# <a name="scriptblock-element-for-groupby-format"></a>Элемент ScriptBlock для элемента GroupBy (формат)

Задает скрипт, запускающий новую группу при изменении ее значения.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента ScriptBlock представления (Format) для GroupBy (Format)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)|Определяет, как отображается группа объектов .NET.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Комментарии

PowerShell запускает новую группу при каждом изменении значения этого сценария.

Если этот элемент указан, нельзя указать элемент [PropertyName](propertyname-element-for-groupby-format.md) для запуска новой группы.

## <a name="see-also"></a>См. также:

[Элемент PropertyName для элемента GroupBy (формат)](propertyname-element-for-groupby-format.md)

[Элемент GroupBy для элемента View (формат)](groupby-element-for-view-format.md)

[Написание файла форматирования PowerShell](writing-a-powershell-formatting-file.md)
