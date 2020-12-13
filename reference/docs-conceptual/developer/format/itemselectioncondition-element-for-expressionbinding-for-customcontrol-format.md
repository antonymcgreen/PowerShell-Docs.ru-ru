---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)
description: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648043"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)

Определяет условие, которое должно существовать для использования этого элемента управления. Количество условий выбора, которое можно указать для элемента управления, не ограничено. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления (Format) кустоментриес для кустомитем для представления (Format) в кустоментри для ExpressionBinding для кустомитем для представления (формат) ошибка customcontrol для элемента for View (формат) ItemSelectionCondition.

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
|[Элемент PropertyName для Итемселектионкондитион для ошибка customcontrol в представлении (Format](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает свойство .NET, которое запускает условие.|
|[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает скрипт, который запускает условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Комментарии

Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)

[Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
