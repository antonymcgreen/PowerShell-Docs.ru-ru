---
title: Элемент PropertyName для ItemSelectionCondition для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e707ae-3c84-4ceb-ba31-56b3ffde6d6c
caps.latest.revision: 7
ms.openlocfilehash: b15e26e18126f69eee7c3a857f9a461d4bdf5848
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064753"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a>Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)

Задает свойство .NET, которое активирует условие. Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется представление. Этот элемент используется при определении представления списка.

Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) элемент ListEntries (формат) ListEntry элемента конфигурации для элемента ListControl (формат) ListItems ListEntry для ListItem ListControl (формат) Элемент для ListItems для элемента ListControl (формат) ItemSelectionCondition ListItem для элемента PropertyName объектов ListControls ItemSelectionCondition для ListControl (формат)

## <a name="syntax"></a>Синтаксис

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах атрибуты, дочерние и родительские элементы из `PropertyName` элемент.

### <a name="attributes"></a>Атрибуты

Нет.

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент ItemSelectionCondition для ListItem для ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a>Текстовое значение

Укажите имя свойства, значение которого отображается.

## <a name="remarks"></a>Замечания

Если этот элемент используется, нельзя указать [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) элемент при определении условию выбора.

## <a name="see-also"></a>См. также

[Элемент ScriptBlock для ItemSelectionCondition для ListIControl (формат)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[Элемент ItemSelectionCondition для ListItem для ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
