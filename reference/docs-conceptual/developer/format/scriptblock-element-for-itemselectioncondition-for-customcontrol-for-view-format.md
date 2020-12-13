---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)
description: Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: d762f400f5bb52af314093079fe94223c56d3f31
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665122"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)

Указывает скрипт, который запускает условие. При вычислении этого скрипта `true` выполняется условие, и используется элемент управления. Этот элемент используется при определении пользовательского представления элемента управления.

Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ошибка customcontrol (Format) элемент Кустоментриес для ошибка customcontrol для элемента View (формат) Кустоментри для Кустоментриес для представления (Format) Кустомитем для Кустоментри для элемента ExpressionBinding представления (Format) для Кустомитем для ошибка customcontrol для элемента "View" ItemSelectionCondition в качестве привязывания выражения для ошибка customcontrol для представления (Format) элемент ScriptBlock для ItemSelectionCondition для ошибка customcontrol для представления (Format)

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
|[Элемент Итемселектионкондитион для привязки выражения ошибка customcontrol для представления (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Определяет условие, которое должно существовать для использования этого элемента управления.|

## <a name="text-value"></a>Текстовое значение

Укажите оцениваемый скрипт.

## <a name="remarks"></a>Комментарии

Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) при определении условия выбора.

## <a name="see-also"></a>См. также:

[Элемент PropertyName для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[Элемент Итемселектионкондитион для привязки выражения ошибка customcontrol для представления (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
