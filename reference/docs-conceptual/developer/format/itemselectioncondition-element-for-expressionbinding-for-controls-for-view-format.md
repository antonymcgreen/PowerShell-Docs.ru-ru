---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)
description: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)
ms.openlocfilehash: adbe747bdb4f6c1d180e5b630247de0fd3d72b85
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648054"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления в элементе "View" (Format) ошибка customcontrol для элемента управления элементов формат). элемент Кустоментри для Кустоментриес для элементов управления для элемента Кустомитем представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) ExpressionBinding для Кустомитем для элементов управления для представления (Format) ItemSelectionCondition элемента ExpressionBinding для элементов управления представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Комментарии

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
