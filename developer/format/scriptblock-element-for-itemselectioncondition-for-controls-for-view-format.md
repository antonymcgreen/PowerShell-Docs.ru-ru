---
title: Элемент ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4191157-bf01-4831-b221-6f8cc581cd53
caps.latest.revision: 6
ms.openlocfilehash: 0cbefbb48427b56d4ae2a5ae27c7726dcfad7b84
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856740"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a>Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)

Указывает сценарий, который активирует условие. При вычислении этого сценария для `true`условие выполняется, и используется элемент управления. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) ExpressionBinding для CustomItem для элементов управления для представления (формат) Элемент ItemSelectionCondition ExpressionBinding для элементов управления для элемента представления (формат) ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|Определяет условие, которое должен существовать для данного элемента управления для использования.|

## <a name="text-value"></a>Текстовое значение

Укажите сценарий, который вычисляется.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) элемент при определении условию выбора.

## <a name="see-also"></a>См. также

[Элемент PropertyName для ItemSelectionCondition для элементов управления для представления (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
