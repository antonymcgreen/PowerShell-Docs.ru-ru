---
title: Элемент PropertyName для ItemSelectionCondition для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 221cbdc2-f794-4f3a-9d40-bfdd8cba1013
caps.latest.revision: 6
ms.openlocfilehash: aae65789cf5572cbcc9251eca802a2d43065e49f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858270"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a>Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)

Задает свойство .NET, которое активирует условие. Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется элемент управления. Этот элемент используется при определении того, как отображается группу объектов.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента ExpressionBinding GroupBy (формат) для CustomItem элемента ItemSelectionCondition GroupBy (формат) для ExpressionBinding для элемента PropertyName GroupBy (формат) ItemSelectionCondition для GroupBy (формат)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|Определяет условие, которое должен существовать для данного элемента управления для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET, которое активирует условие.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) элемент при определении условию выбора.

## <a name="see-also"></a>См. также

[Элемент ScriptBlock для ItemSelectionCondition для GroupBy (формат)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
