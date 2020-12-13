---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)
description: Элемент PropertyName для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 860683eb54b2a3579767640c1d3f0937897b8f8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655128"
---
# <a name="propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Элемент PropertyName для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется элемент управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для элемента Ошибка customcontrol для элемента Configuration (формат) Кустоментри для ошибка customcontrol для элементов управления для Configuration (Format) Кустомитем элемент для Кустоментри для элементов управления элемента Configuration ExpressionBinding для Кустомитем элементов управления для элемента конфигурации (Format) Итемселектионкондитион для ExpressionBinding элементов управления для элемента конфигурации (Format) PropertyName для ItemSeclectionCondition для элементов управления конфигурации (Format)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET, которое запускает условие.

## <a name="remarks"></a>Комментарии

Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также:

[Элемент ScriptBlock для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
