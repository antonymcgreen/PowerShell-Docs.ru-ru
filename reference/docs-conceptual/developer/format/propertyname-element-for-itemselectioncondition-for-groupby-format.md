---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)
description: Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)
ms.openlocfilehash: 9667a389ded33d0744f0f7f8d739635a8b21d98b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666116"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a>Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)

Указывает свойство .NET, которое запускает условие. При наличии этого свойства или при его вычислении `true` условие выполняется, и используется элемент управления. Этот элемент используется при определении того, как отображается новая группа объектов.

Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента GroupBy для элемента Ошибка customcontrol представления (Format) элемент Кустоментриес для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для ошибка customcontrol для элемента GroupBy (Format) Кустомитем для элемента Кустоментри для GroupBy (Format) ExpressionBinding для Кустомитем for GroupBy (формат) Итемселектионкондитион для ExpressionBinding для GroupBy (Format) элемент PropertyName для ItemSelectionCondition для GroupBy (Format)

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
|[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET, которое запускает условие.

## <a name="remarks"></a>Комментарии

Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также:

[Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
