---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)
description: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)
ms.openlocfilehash: 92120ace5ed316fbfbf1d51422071c27d5a604cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651990"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Количество условий выбора, которое можно указать для элемента управления, не ограничено. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри for GroupBy, ExpressionBinding для кустомитем для элемента GroupBy (Format) итемселектионкондитион для ExpressionBinding for GroupBy (формат)

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
|[Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Комментарии

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)](./expressionbinding-element-for-customitem-for-groupby-format.md)
