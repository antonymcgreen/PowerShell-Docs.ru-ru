---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Controls для элемента Configuration (формат)
description: Элемент Controls для элемента Configuration (формат)
ms.openlocfilehash: 53f874ddccf3b4f1f0a23aad608e786524bde830
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668105"
---
# <a name="controls-element-for-configuration-format"></a>Элемент Controls для элемента Configuration (формат)

Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.

Элемент Configuration (Format) управляет элементом конфигурации (Format)

## <a name="syntax"></a>Синтаксис

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Controls` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Control для элемента Controls для элемента Configuration (формат)](./control-element-for-controls-for-configuration-format.md)|Обязательный элемент.<br /><br /> Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Configuration (формат)](./configuration-element-format.md)|Представляет элемент верхнего уровня файла форматирования.|

## <a name="remarks"></a>Комментарии

Можно создать любое количество стандартных элементов управления. Для каждого элемента управления необходимо указать имя, которое используется для ссылки на элемент управления и компоненты элемента управления.

## <a name="see-also"></a>См. также:

[Элемент Configuration (формат)](./configuration-element-format.md)

[Элемент Control для элемента Controls для элемента Configuration (формат)](./control-element-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
