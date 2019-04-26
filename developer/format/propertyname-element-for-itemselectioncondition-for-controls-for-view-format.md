---
title: Элемент PropertyName для ItemSelectionCondition для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3955bc-f3a1-4ef6-86ac-80ffc133ad1b
caps.latest.revision: 6
ms.openlocfilehash: 28ad31be4be7be20f1f43ea1b69ad5d294de86f6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075857"
---
# <a name="propertyname-element-for-itemselectioncondition-for-controls-for-view-format"></a>Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)

Задает свойство .NET, которое активирует условие. Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется элемент управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) ExpressionBinding для CustomItem для элементов управления для представления (формат) Элемент ItemSelectionCondition ExpressionBinding для элементов управления для элемента представления (формат) PropertyName для ItemSelectionCondition для элементов управления для представления (формат)

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
|[Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Определяет условие, которое должен существовать для данного элемента управления для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства .NET, которое активирует условие.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) элемент при определении условию выбора.

## <a name="see-also"></a>См. также

[Элемент ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
