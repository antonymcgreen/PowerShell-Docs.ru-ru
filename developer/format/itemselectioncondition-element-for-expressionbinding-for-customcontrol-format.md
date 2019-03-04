---
title: Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858190"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a>Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)

Определяет условие, которое должен существовать для данного элемента управления для использования. Нет ограничений на число условий выборки, которые можно задать для элемента управления. Этот элемент используется при определении представления пользовательского элемента управления.

Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry для элемента представления (формат) ExpressionBinding для CustomItem для пользовательский элемент управления для элемента ItemSelectionCondition представления (формат) для привязки выражения для пользовательский элемент управления для представления (формат)

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
|[Элемент PropertyName для ItemSelectionCondition для пользовательский элемент управления для представления (в формате](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Задает свойство .NET, которое активирует условие.|
|[Элемент ScriptBlock для ItemSelectionCondition для пользовательский элемент управления для представления (формат)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|Необязательный элемент.<br /><br /> Указывает сценарий, который активирует условие.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|Определяет данные, отображаемые элементом управления.|

## <a name="remarks"></a>Замечания

Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)

[Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
