---
title: Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c15014-2440-410d-b02d-b7f1a49240a0
caps.latest.revision: 7
ms.openlocfilehash: 80f375c53c205c793600655fa6031d114871618e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861850"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)

Определяет условие, которое должен существовать для данного элемента управления для использования. Этот элемент используется при определении элементов управления, которые могут использоваться представлением.

Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) ExpressionBinding для CustomItem для элементов управления для представления (формат) Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)

## <a name="syntax"></a>Синтаксис

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Ниже описаны атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент PropertyName для ItemSelectionCondition для элементов управления для представления (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.

## <a name="see-also"></a>См. также

[Элемент PropertyName для ItemSelectionCondition для элементов управления для представления (формат)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
