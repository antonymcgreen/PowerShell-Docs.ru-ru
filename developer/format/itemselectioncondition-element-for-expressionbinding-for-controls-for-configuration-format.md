---
title: Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861690"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)

Определяет условие, которое должен существовать для данного элемента управления для использования. Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.

Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для элемента конфигурации ExpressionBinding для CustomItem для элементов управления для конфигурации (формат) Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)

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
|[Элемент PropertyName для ItemSelectionCondition для элементов управления для конфигурации (формат)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для ItemSelectionCondition для элементов управления для конфигурации (формат)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.

## <a name="see-also"></a>См. также

[Элемент PropertyName для ItemSelectionCondition для элементов управления для конфигурации (формат)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ScriptBlock для ItemSelectionCondition для элементов управления для конфигурации (формат)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
