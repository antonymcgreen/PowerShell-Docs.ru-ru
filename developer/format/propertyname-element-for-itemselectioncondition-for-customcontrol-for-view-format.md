---
title: Элемент PropertyName для ItemSelectionCondition для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b12006-8d52-486b-91a3-e6224ca80e56
caps.latest.revision: 6
ms.openlocfilehash: 52d0b0816eaef6752220e0c3b1249e5a0e44a3ee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854790"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>Элемент PropertyName для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)

Задает свойство .NET, которое активирует условие. Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется элемент управления. Этот элемент используется при определении представления пользовательского элемента управления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry для элемента представления (формат) ExpressionBinding для CustomItem для пользовательский элемент управления для элемента ItemSelectionCondition представления (формат) для привязки выражения для пользовательский элемент управления для элемента представления (формат) PropertyName для ItemSelectionCondition для Пользовательский элемент управления для представления (в формате

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
|[Элемент ItemSelectionCondition для привязки выражения для пользовательский элемент управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|Определяет условие, которое должен существовать для данного элемента управления для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET, которое активирует условие.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) элемент при определении условию выбора.

## <a name="see-also"></a>См. также

[Элемент ScriptBlock для ItemSelectionCondition для пользовательский элемент управления для представления (формат)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[Элемент ItemSelectionCondition для привязки выражения для пользовательский элемент управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
