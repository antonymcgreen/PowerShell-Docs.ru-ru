---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)
description: Элемент ScriptBlock для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 853130da4489e571d7f4026a8d65d029d1889f9b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665228"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a>Элемент ScriptBlock для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется элемент управления. Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.

Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для элемента Ошибка customcontrol для элемента Configuration (формат) Кустоментри для ошибка customcontrol для элементов управления для Configuration (Format) Кустомитем элемент для Кустоментри для элементов управления элемента Configuration ExpressionBinding для Кустомитем элементов управления для элемента конфигурации (Format) Итемселектионкондитион для ExpressionBinding для элементов управления в конфигурации (Format) элемент ScriptBlock для ItemSelectionCondition для элементов управления конфигурации (Format)

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
|[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Комментарии

Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также:

[Элемент PropertyName для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
