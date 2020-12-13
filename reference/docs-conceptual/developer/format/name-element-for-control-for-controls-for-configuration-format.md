---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)
description: Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 0c1c83f827482886ca742f2c0174e8383f87fb52
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666507"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)

Задает имя элемента управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления (Format) Name для элемента Control (формат), для которого наследуется конфигурация (Format).

## <a name="syntax"></a>Синтаксис

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент Control для элемента Controls для элемента Configuration (формат)](./control-element-for-controls-for-configuration-format.md)|Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя, используемое для ссылки на этот элемент управления.

## <a name="remarks"></a>Комментарии

Указанное здесь имя можно использовать в следующих элементах для ссылки на этот элемент управления.

- При создании представления таблицы, списка, расширенного или пользовательского элемента управления элемент управления может быть задан следующим элементом: [GroupBy для представления (формат)](./groupby-element-for-view-format.md) .

- При создании другого общего элемента управления этот элемент управления может быть задан следующим элементом: [ExpressionBinding элемент для кустомитем для элементов управления конфигурации (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md) .

- При создании элемента управления, который может использоваться представлением, этот элемент управления может быть задан следующим элементом: [ExpressionBinding для кустомитем для элементов управления в представлении (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) .

## <a name="see-also"></a>См. также:

[Элемент Control для элемента Controls для элемента Configuration (формат)](./control-element-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Элемент GroupBy для элемента View (формат)](./groupby-element-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
